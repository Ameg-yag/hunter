.. Copyright (c) 2016, Ruslan Baratov
.. All rights reserved.

Hunter-ID
---------

First level of customization. Hunter archive.

``Hunter-ID`` is the first 7 digits of ``SHA1``
of Hunter archive.  This level defines list of available packages and mapping
``version -> URL/SHA1``. Several ``Hunter-ID`` can coexist in the same
``HUNTER_ROOT`` directory.  ``HunterGate`` command will control your choice:

+-------------+----------------------------------------------------------------------------------------+
| Hunter-ID   |                                                                                        |
+=============+===================+====================================================================+
| ``1eae623`` | Hunter version    | ``0.8.3``                                                          |
|             +-------------------+--------------------------------------------------------------------+
|             | SHA1 of archive   | ``1eae623cb5ce9da39c8c3e1b0f6e452f244ddc17``                       |
|             +-------------------+--------------------------------------------------------------------+
|             | Working directory | ``${HUNTER_ROOT}/_Base/1eae623/...``                               |
|             +-------------------+--------------+-------------+---------------------------------------+
|             | Packages          | ``Foo`` [1]_ | ``1.0.0``   | ``mysite.xyz/Foo-1.0.0.tar.gz``       |
|             |                   +--------------+-------------+---------------------------------------+
|             |                   | ``Boo``      | ``2.0.0``   | ``mysite.xyz/Boo-2.0.0.tar.gz``       |
|             |                   |              +-------------+---------------------------------------+
|             |                   |              | ``2.1.0``   | ``mysite.xyz/Boo-2.1.0.tar.gz``       |
|             |                   +--------------+-------------+---------------------------------------+
|             |                   | ``Roo``      | ``1.2.3``   | ``mysite.xyz/Roo-1.2.3.tar.gz``       |
|             |                   |              +-------------+---------------------------------------+
|             |                   |              | ``1.2.4``   | ``mysite.xyz/Roo-1.2.4.tar.gz``       |
+-------------+-------------------+--------------+-------------+---------------------------------------+
| ``e07a124`` | Hunter version    | ``0.8.4``                                                          |
|             +-------------------+--------------------------------------------------------------------+
|             | SHA1 of archive   | ``e07a124192b0a47b0b60ade40fa873a42ec27822``                       |
|             +-------------------+--------------------------------------------------------------------+
|             | Working directory | ``${HUNTER_ROOT}/_Base/e07a124/...``                               |
|             +-------------------+--------------+----------+------------------------------------------+
|             | Packages          | ``Awesome``  | ``1.0.0``| ``example.com/Awesome-1.0.0.tar.gz``     |
|             |                   +--------------+----------+------------------------------------------+
|             |                   | ``Best``     | ``2.0.0``| ``example.com/Best-2.0.0.tar.gz``        |
|             |                   |              +----------+------------------------------------------+
|             |                   |              | ``2.0.1``| ``example.com/Best-2.0.1.tar.gz``        |
|             |                   +--------------+----------+------------------------------------------+
|             |                   | ``Foo`` [1]_ | ``1.0.0``| ``example.com/Foo-1.0.0-patch-1.tar.gz`` |
+-------------+-------------------+--------------+----------+------------------------------------------+


.. [1] Yep, same version but different URL/SHA1. No conflicts.

Message in logs:

.. code-block:: none

  -- [hunter] [ Hunter-ID: 1eae623 | Toolchain-ID: ... | Config-ID: ... ]
  -- [hunter] [ Hunter-ID: e07a124 | Toolchain-ID: ... | Config-ID: ... ]

.. admonition:: Hunter

  * `Releases <https://github.com/cpp-pm/hunter/releases>`__
  * `Atom feed <https://github.com/cpp-pm/hunter/releases.atom>`__
