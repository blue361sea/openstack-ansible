`Home <index.html>`_ OpenStack-Ansible Installation Guide

Configuring RabbitMQ (optional)
===============================

RabbitMQ provides the messaging broker for various OpenStack services. The
OpenStack-Ansible project configures a plaintext listener on port 5672 and
a SSL/TLS encrypted listener on port 5671.

Customize your RabbitMQ deployment in
``/etc/openstack_deploy/user_variables.yml``.

Add a TLS encrypted listener to RabbitMQ
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The OpenStack-Ansible project provides the ability to secure RabbitMQ
communications with self-signed or user-provided SSL certificates. Refer to
`Securing services with SSL certificates`_ for available configuration
options.

.. _Securing services with SSL certificates: configure-sslcertificates.html

Enable encrypted connections to RabbitMQ
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The control of SSL communication between various OpenStack services and
RabbitMQ is via the Ansible variable ``rabbitmq_use_ssl``:

.. code-block:: yaml

    rabbitmq_use_ssl: true

Setting this variable to ``true`` adjusts the RabbitMQ port to 5671 (the
default SSL/TLS listener port) and enables SSL connectivity between each
OpenStack service and RabbitMQ.

Setting this variable to ``false`` disables SSL encryption between
OpenStack services and RabbitMQ. Use the plaintext port for RabbitMQ, 5672,
for all services.

--------------

.. include:: navigation.txt
