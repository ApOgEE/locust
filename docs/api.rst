###
API
###


Locust class
============

.. autoclass:: locust.core.Locust
    :members: wait_time, task_set, weight

HttpLocust class
================

.. autoclass:: locust.core.HttpLocust
    :members: wait_time, task_set, client


TaskSet class
=============

.. autoclass:: locust.core.TaskSet
    :members: locust, parent, wait_time, client, tasks, interrupt, schedule_task

task decorator
==============

.. autofunction:: locust.core.task

TaskSequence class
==================

.. autoclass:: locust.core.TaskSequence
    :members: locust, parent, wait_time, client, tasks, interrupt, schedule_task

seq_task decorator
==================

.. autofunction:: locust.core.seq_task

Built in wait_time functions
============================

.. automodule:: locust.wait_time
    :members: between, constant, constant_pacing

HttpSession class
=================

.. autoclass:: locust.clients.HttpSession
    :members: __init__, request, get, post, delete, put, head, options, patch

Response class
==============

This class actually resides in the `python-requests <http://python-requests.org>`_ library, 
since that's what Locust is using to make HTTP requests, but it's included in the API docs 
for locust since it's so central when writing locust load tests. You can also look at the 
:py:class:`Response <requests.Response>` class at the 
`requests documentation <http://python-requests.org>`_.

.. autoclass:: requests.Response
    :inherited-members:
    :noindex:

ResponseContextManager class
============================

.. autoclass:: locust.clients.ResponseContextManager
    :members: success, failure


InterruptTaskSet Exception
==========================
.. autoexception:: locust.exception.InterruptTaskSet


.. _events:

Event hooks
===========

The event hooks are instances of the **locust.events.EventHook** class:

.. autoclass:: locust.events.EventHook

.. note::

    It's highly recommended that you add a wildcard keyword argument in your event listeners
    to prevent your code from breaking if new arguments are added in a future version.

Available hooks
---------------

The following event hooks are available under the **locust.events** module:

.. automodule:: locust.events
    :members: request_success, request_failure, locust_error, report_to_master, slave_report, hatch_complete, quitting

