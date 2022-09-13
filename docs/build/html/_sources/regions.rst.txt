Regions
=======

A region describes a piece of an object's data.
Regions can be used to restrict the area of a tranfer request.
Example:

.. code-block:: python
   :linenos:

   import pdc
   import numpy as np

   with pdc.ServerContext():
      pdc.init()
      cont = pdc.Container('region_example_cont', lifetime=pdc.Container.Lifetime.TRANSIENT)

      data = [
         [2, 7, 6],
         [9, 5, 1],
         [4, 3, 8]
      ]

      obj = cont.object_from_array('region_example_obj', data)

      data1 = obj.get_data(pdc.region[:2]).wait() # [[2, 7, 6], [9, 5, 1]]
      data2 = obj.get_data(pdc.region[0, :2]).wait() # [[2, 7]]


.. automodule:: pdc
   :noindex:
   :undoc-members:
   :members: Region

   .. property:: region
   
   	An object used to create regions.
   	See :class:`Region` for details.