.. The contents of this file may be included in multiple topics (using the includes directive).
.. The contents of this file should be modified in a way that preserves its ability to appear in multiple topics.

This resource has the following properties:
   
``easy_install_binary``
   **Ruby Type:** String

   The location of the Easy Install binary.
   
``ignore_failure``
   **Ruby Types:** TrueClass, FalseClass

   Continue running a recipe if a resource fails for any reason. Default value: ``false``.
   
``module_name``
   **Ruby Type:** String

   The name of the module.
   
``notifies``
   **Ruby Type:** Symbol, 'Chef::Resource[String]'

   .. include:: ../../includes_resources_common/includes_resources_common_notification_notifies.rst

   .. include:: ../../includes_resources_common/includes_resources_common_notification_timers.rst

   .. include:: ../../includes_resources_common/includes_resources_common_notification_notifies_syntax.rst
   
``options``
   **Ruby Type:** String

   One (or more) additional options that are passed to the command.
   
``package_name``
   **Ruby Types:** String, Array

   The name of the package. Default value: the ``name`` of the resource block See "Syntax" section above for more information.
   
``provider``
   **Ruby Type:** Chef Class

   Optional. Explicitly specifies a provider. See "Providers" section below for more information.
   
``python_binary``
   **Ruby Type:** String

   The location of the Python binary.
   
``retries``
   **Ruby Type:** Integer

   The number of times to catch exceptions and retry the resource. Default value: ``0``.
   
``retry_delay``
   **Ruby Type:** Integer

   The retry delay (in seconds). Default value: ``2``.
   
``subscribes``
   **Ruby Type:** Symbol, 'Chef::Resource[String]'

   .. include:: ../../includes_resources_common/includes_resources_common_notification_subscribes.rst

   .. include:: ../../includes_resources_common/includes_resources_common_notification_timers.rst

   .. include:: ../../includes_resources_common/includes_resources_common_notification_subscribes_syntax.rst
   
``source``
   **Ruby Type:** String

   Optional. The path to a package in the local file system.
   
``timeout``
   **Ruby Types:** String, Integer

   The amount of time (in seconds) to wait before timing out.
   
``version``
   **Ruby Types:** String, Array

   The version of a package to be installed or upgraded.
