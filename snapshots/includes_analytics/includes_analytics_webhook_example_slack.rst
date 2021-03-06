.. The contents of this file may be included in multiple topics (using the includes directive).
.. The contents of this file should be modified in a way that preserves its ability to appear in multiple topics.


A webhook for Chef Analytics enables real-time event streams to be sent to arbitrary locations that support webhooks integrations. For example, channels in Slack may be configured to receive notifications from Chef Analytics by integrating with the incoming webhooks functionality in Slack.

#. Create an incoming webhook in Slack. Choose the channel that will receive the incoming notification:

   .. image:: ../../images/analytics_slack_incoming_webhooks.png

   and then click **Add Incoming Webhooks Integration**. Copy the URL that is generated by Slack. This will be needed by Chef Analytics.

#. Log into Chef Analytics and create a **Webhook** notification:

   .. image:: ../../images/analytics_slack_notification.png

#. Name the webhook---``slack``, for example---and then paste the URL that was provided by Slack:

   .. image:: ../../images/analytics_slack_http_configure.png

   Click **Save**.

#. Create a rule that uses this integration and test it. For example, configuring Chef Analytics to send a notification to Slack when a audit-mode run fails. First, create a simple rule to test the Slack integration. Configure a message to be sent to Slack for any action event that comes into Chef Analytics:

   .. code-block:: ruby

      rules 'org notifier'
        rule on action
        when
          true
        then
          notify('slack', '{
            "text": "test from the blog post"
          }')
        end
      end

   Slack expects a JSON document to be sent to the incoming webook integration from Chef Analytics. Chef Analytics supports multi-line notifications to be written. Use the ``'text'`` property in the rule to send the data as a JSON document.

#. Finally, create a rule that is more specific to the Chef Analytics data, such as assigning an emoji and a name for the notification:

   .. code-block:: ruby

      rules 'failed-audit'
        rule on run_control_group
        when
          status != 'success'
        then
          notify('slack', '{
            "username": "Audit Alarm",
            "icon_emoji": ":rotating_light:",
            "text": "{{message.name}} (cookbook {{message.cookbook_name}})\n
              had \'{{message.number_failed}}\' failed audit test(s)\n
              on node \'{{message.run.node_name}}\'\n
              in organization \'{{message.organization_name}}\'"
          }')
        end
      end

   This will generate a message similar to:

   .. image:: ../../images/analytics_slack_message.png
