.. THIS PAGE IS IDENTICAL TO docs.chef.io/supermarket_logs.html BY DESIGN
.. THIS PAGE IS LOCATED AT THE /release/supermarket/ PATH.

=====================================================
Supermarket Logs
=====================================================

The Chef Supermarket omnibus package does not log Ruby on Rails messages by default. To enable debug logging, edit the ``/opt/supermarket/embedded/service/supermarket/config/environments/production.rb`` file and set the ``config.log_level`` setting to ``:debug``:

.. code-block:: ruby

   config.logger = Logger.new('/var/log/supermarket/rails/rails.log')
   config.logger.level = 'DEBUG'
   config.log_level = :debug

Save the file, and then restart the Ruby on Rails service:

.. code-block:: bash

   $ supermarket-ctl restart rails
