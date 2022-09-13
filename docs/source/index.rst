Welcome to PDCpy's documentation!
==========================================

Proactive Data Containers (PDC) software provides an object-centric API and a runtime system with a set of data object management services. These services allow placing data in the memory and storage hierarchy, performing data movement asynchronously, and providing scalable metadata operations to find data objects.
More information and publications of PDC is available at https://sdm.lbl.gov/pdc

.. toctree::
   :maxdepth: 1
   :caption: Contents:

   Home <index>
   containers
   objects
   regions
   queries

Main APIs
=========

Thoughout the documentation, you may see the following types used when an integer must be in a certain range:

===========  =================
type name    range
===========  =================
int32        -2**31 to 2**31-1
uint32       0 to 2**32-1
uint64       0 to 2**64-1
===========  =================

These bounds are checked at runtime and will result in an OverflowError if they are exceeded.

.. automodule:: pdc
   :imported-members:
   :members: KVTags, PDCError, init, ready, ServerContext
   :undoc-members:
   :exclude-members: tag_types, tag_types_union

   .. autoclass:: Type
      :members: as_numpy_type, from_numpy_type
      :show-inheritance:

      .. autoattribute:: INT32
         :annotation: 
         
         A 32-bit signed integer.

      .. autoattribute:: UINT32
         :annotation: 
         
         A 32-bit unsigned integer.
      
      .. autoattribute:: FLOAT
         :annotation: 
         
         A 32-bit floating point number.
      
      .. autoattribute:: DOUBLE
         :annotation: 
         
         A 64-bit floating point number.
            
      .. autoattribute:: INT64
         :annotation: 
         
         A 64-bit signed integer.
      
      .. autoattribute:: UINT64
         :annotation: 
         
         A 64-bit unsigned integer.
      
      .. autoattribute:: INT16
         :annotation: 
         
         A 16-bit signed integer.
      
      .. autoattribute:: INT8
         :annotation: 
         
         An 8-bit signed integer.


* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
