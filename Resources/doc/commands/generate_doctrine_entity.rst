Generating a New Doctrine Entity Stub
=====================================

Usage
-----

The ``generate:doctrine:entity`` command generates a new Doctrine entity stub
including the mapping definition and the class properties, getters and setters.

By default the command is run in the interactive mode and asks questions to
determine the bundle name, location, configuration format and default
structure:

.. code-block:: bash

    php app/console generate:doctrine:entity

The command can be run in a non interactive mode by using the
``--no-interaction`` option without forgetting all needed options:

.. code-block:: bash

    php app/console generate:doctrine:entity --no-interaction --entity=AcmeBlogBundle:Post --fields="title:string(100) body:text" --format=xml

Available Options
-----------------

* ``--entity``: The entity name given as a shortcut notation containing the
  bundle name in which the entity is located and the name of the entity. For
  example: ``AcmeBlogBundle:Post``:

    .. code-block:: bash

        php app/console generate:doctrine:entity --entity=AcmeBlogBundle:Post

* ``--fields``: The list of fields to generate in the entity class:

    .. code-block:: bash

        php app/console generate:doctrine:entity --fields="title:string(length=100 nullable=true unique=false) body:text ranking:decimal(precision:10 scale:0)"

.. versionadded:: 3.0
    Ability to pass named options to fields was added in version 3.0. Previously,
    only ``string`` type was allowed to receive the length value as argument.
    Available options are ``length``, ``nullable``, ``unique``, ``precision`` and
    ``scale``.

* ``--format``: (**annotation**) [values: yml, xml, php or annotation] This
  option determines the format to use for the generated configuration files
  for doctrine entity mapping. By default, the command uses the ``annotation`` format:

    .. code-block:: bash

        php app/console generate:doctrine:entity --format=annotation

* ``--id-generator-strategy``: (**AUTO**) [values: AUTO, SEQUENCE, IDENTITY, UUID, TABLE or NONE] This
  option determines the identifier generator strategy to use for the generated
  doctrine entity. By default, the command uses the ``AUTO`` identifier generator
  strategy:

    .. code-block:: bash

        php app/console generate:doctrine:entity --id-generator-strategy=AUTO

.. versionadded:: 3.0
    The ``id-generator-strategy`` option was added in version 3.0. Previously,
    the default value was always used.
