.. _queries:

Queries
=======

Queries search for elements in an object.  They can also search for elements in multiple objects, in which case each object will be treated as a column of data, and matching rows are returned.

A query consists of one or more clauses where one object's data is compared, combined with AND (&) or OR (|)

For example, with 2 objects with these contents:

= =
a b
= =
1 2
3 3
5 8
7 0
= =

The query ``a.data > 3 | b.data > 4`` would return:

= =
a b
= =
5 8
7 0
= =

Queries can also be restricted to a specific region.

Here is a full program that performs the previous query:

.. code-block:: python
   :linenos:
   
   import pdc
   import numpy as np

   with pdc.ServerContext():
      pdc.init()
      cont = pdc.Container('test')
      a = cont.object_from_array('a', [1, 3, 5, 7])
      b = cont.object_from_array('b', [2, 3, 8, 0])
      
      query = (a.data > 3) | (b.data > 4)
      result = query.get_result()
      a_data = result[a] #5 7
      b_data = result[b] #8 0

.. automodule:: pdc
   :undoc-members:
   :members: Query
   :noindex:
   :exclude-members: Query

   .. autoclass:: pdc.Query
      :members:
      :undoc-members:
      :exclude-members: Result

      .. autoclass:: pdc.Query.Result
         :members:
         :undoc-members:

         .. property:: hits

            Number of hits in the result.
            If you *only* want the number of hits, use :func:`query.get_num_hits`
