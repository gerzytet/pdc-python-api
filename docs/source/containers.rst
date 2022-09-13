Containers
==========
Example of creating a container:

.. code-block:: python
   :linenos:

   import pdc

   with pdc.ServerContext() as _:
      #make a container.  The container is persistent by default.
      cont = pdc.Container('persistent_cont')

      #make a transient container, it will be deleted when the pdc server is closed
      cont2 = pdc.Container('transient_cont', lifetime=pdc.Container.Lifetime.TRANSIENT)

.. automodule:: pdc
   :noindex:
   :imported-members:
   :exclude-members: containers_by_id, Container
   :members: all_local_containers

   .. autoclass:: Container
      :members:
      :exclude-members: Lifetime
      
      .. autoclass:: pdc.Container.Lifetime
         :show-inheritance:

         .. autoattribute:: pdc.Container.Lifetime.PERSISTENT
            :annotation:

            The container and all objects in it will persist across server restarts.
         
         .. autoattribute:: pdc.Container.Lifetime.TRANSIENT
            :annotation:

            The container and all objects in it will be deleted when the server restarts.
