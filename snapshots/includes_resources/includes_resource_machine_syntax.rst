.. The contents of this file may be included in multiple topics (using the includes directive).
.. The contents of this file should be modified in a way that preserves its ability to appear in multiple topics.

The syntax for using the **machine** resource in a recipe is as follows:

.. code-block:: ruby

   machine 'name' do
     attribute 'value' # see properties section below
     ...
     action :action # see actions section below
   end

where 

* ``machine`` tells the chef-client to use the ``Chef::Provider::Machine`` provider during the chef-client run
* ``name`` is the name of the resource block and also the name of the machine
* ``attribute`` is zero (or more) of the properties that are available for this resource
* ``:action`` identifies which steps the chef-client will take to bring the node into the desired state
