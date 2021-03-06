.. _zend.validator.timezone:

Timezone Validator
==================

``Zend\Validator\Timezone`` allows validating if an input string
represents a timezone.

Supported validation types
--------------------------

The ``Zend\Validator\Timezone`` validator is capable of validating the
abbreviation (e.g. "ewt") as well as the location string (e.g.
"America/Los\_Angeles"). These options are stored in the validator as
``LOCATION``, ``ABBREVIATION``, and ``ALL`` class constants.

Basic Usage
-----------

The default validation type will check again abbreviations as well as
the location string.

.. code-block:: php
   :linenos:

    $validator = new Zend\Validator\Timezone();

    $validator->isValid('America/Los_Angeles'); // returns true
    $validator->isValid('ewt'); // returns true
    $validator->isValid('Foobar');  // returns false

To validate against only the location string you can set the type:

.. code-block:: php
   :linenos:

    $validator = new Zend\Validator\Timezone();
    $validator->setType(Zend\Validator\Timezone::LOCATION);

    $validator->isValid('America/Los_Angeles'); // returns true
    $validator->isValid('ewt'); // returns false
    $validator->isValid('Foobar');  // returns false

