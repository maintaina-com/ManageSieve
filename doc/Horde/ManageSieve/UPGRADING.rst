=============================
 Upgrading Horde_ManageSieve
=============================

:Contact: dev@lists.horde.org

.. contents:: Contents
.. section-numbering::


This lists the API changes between releases of the package.

Upgrading from ManageSieve H5-master
====================================

  - The code moved from lib/ to src/
  - The Horde\ManageSieve class is now Horde\ManageSieve\Client to ease PSR-4 autoloading


Upgrading from Net_Sieve
========================

  - The class name has been changed from Net_Sieve to \Horde\ManageSieve.

  - Constants

    - NET_SIEVE_STATE_DISCONNECTED been renamed to
      \Horde\ManageSieve\STATE_DISCONNECTED.

    - NET_SIEVE_STATE_AUTHORISATION been renamed to
      \Horde\ManageSieve\STATE_NON_AUTHENTICATED.

    - NET_SIEVE_STATE_TRANSACTION been renamed to
      \Horde\ManageSieve\STATE_AUTHENTICATED.

  - Constructor

    - The connection parameters are passed as a hash now, instead of individual
      arguments.

    - The default port has been changed to 4190.

    - A timeout parameter has been added.

  - Authentication methods

    The authentication methods are now specified as one of the
    \Horde\ManageSieve\AUTH_* class constants.

  - Methods

    - haveSpace() has been renamed to hasSpace().

  - Error handling

    - Error handling has been converted to
      exceptions. \Horde\ManageSieve\Exception objects are thrown instead of
      PEAR_Error objects returned.

    - getError() has been removed.

  - Logging

    - The debug handler, the debug constructor parameters and the setDebug()
      method have been removed. Use the 'logger' constructor parameter, or
      setLogger() instead.
