.. The contents of this file may be included in multiple topics (using the includes directive).
.. The contents of this file should be modified in a way that preserves its ability to appear in multiple topics.

This resource has the following properties:
   
``default_release``
   **Ruby Type:** String

   The default release. For example: ``stable``.
   
``ignore_failure``
   **Ruby Types:** TrueClass, FalseClass

   Continue running a recipe if a resource fails for any reason. Default value: ``false``.
   
``notifies``
   **Ruby Type:** Symbol, 'Chef::Resource[String]'

   .. include:: ../../includes_resources_common/includes_resources_common_notification_notifies.rst

   .. include:: ../../includes_resources_common/includes_resources_common_notification_timers.rst

   .. include:: ../../includes_resources_common/includes_resources_common_notification_notifies_syntax.rst
   
``options``
   **Ruby Type:** String

   One (or more) additional options that are passed to the command. For example, common apt-get directives, such as ``--no-install-recommends``. See the `apt-get man page <http://manpages.debian.net/cgi-bin/man.cgi?query=apt-get>`_ for the full list.
   
``package_name``
   **Ruby Types:** String, Array

   The name of the package. Default value: the ``name`` of the resource block See "Syntax" section above for more information.
   
``provider``
   **Ruby Type:** Chef Class

   Optional. Explicitly specifies a provider. See "Providers" section below for more information.
   
``retries``
   **Ruby Type:** Integer

   The number of times to catch exceptions and retry the resource. Default value: ``0``.
   
``retry_delay``
   **Ruby Type:** Integer

   The retry delay (in seconds). Default value: ``2``.
   
``source``
   **Ruby Type:** String

   Optional. The direct path to a dpkg or deb package.
   
``subscribes``
   **Ruby Type:** Symbol, 'Chef::Resource[String]'

   .. include:: ../../includes_resources_common/includes_resources_common_notification_subscribes.rst

   .. include:: ../../includes_resources_common/includes_resources_common_notification_timers.rst

   .. include:: ../../includes_resources_common/includes_resources_common_notification_subscribes_syntax.rst
   
``timeout``
   **Ruby Types:** String, Integer

   The amount of time (in seconds) to wait before timing out.
   
``version``
   **Ruby Types:** String, Array

   The version of a package to be installed or upgraded.
