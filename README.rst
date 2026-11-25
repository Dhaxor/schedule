`schedule <https://schedule.readthedocs.io/>`__
===============================================


.. image:: https://github.com/Dhaxor/schedule/actions/workflows/ci.yml/badge.svg
        :target: https://github.com/Dhaxor/schedule/actions/workflows/ci.yml

Python job scheduling for humans. Run Python functions (or any other callable) periodically using a friendly syntax.

- A simple to use API for scheduling jobs, made for humans.
- In-process scheduler for periodic jobs. No extra processes needed!
- Very lightweight and no external dependencies.
- Excellent test coverage.
- Tested on Python 3.9, 3.10, 3.11, 3.12, 3.13 and 3.14 on Linux, Windows and macOS

Project status
--------------

This is the community-maintained continuation of
`dbader/schedule <https://github.com/dbader/schedule>`_, the Python job
scheduling library created by Daniel Bader. The upstream repository has
seen no maintenance activity since May 2024 (v1.2.2), so this fork
continues the project: bug fixes, support for new Python versions and an
active issue tracker. The 1.x API is unchanged and fully compatible with
schedule 1.2.x — existing code keeps working as-is.

Usage
-----

.. code-block:: bash

    $ pip install schedule

To install this maintained fork instead (not on PyPI):

.. code-block:: bash

    $ pip install git+https://github.com/Dhaxor/schedule.git@v1.3.0

.. code-block:: python

    import schedule
    import time

    def job():
        print("I'm working...")

    schedule.every(10).seconds.do(job)
    schedule.every(10).minutes.do(job)
    schedule.every().hour.do(job)
    schedule.every().day.at("10:30").do(job)
    schedule.every(5).to(10).minutes.do(job)
    schedule.every().monday.do(job)
    schedule.every().wednesday.at("13:15").do(job)
    schedule.every().day.at("12:42", "Europe/Amsterdam").do(job)
    schedule.every().minute.at(":17").do(job)

    def job_with_argument(name):
        print(f"I am {name}")

    schedule.every(10).seconds.do(job_with_argument, name="Peter")

    while True:
        schedule.run_pending()
        time.sleep(1)

Documentation
-------------

Schedule's documentation lives at `schedule.readthedocs.io <https://schedule.readthedocs.io/>`_.


Meta
----

Community-maintained fork of `dbader/schedule <https://github.com/dbader/schedule>`__.

Original author: Daniel Bader - `@dbader_org <https://twitter.com/dbader_org>`_ - mail@dbader.org

Inspired by `Adam Wiggins' <https://github.com/adamwiggins>`_ article `"Rethinking Cron" <https://adam.herokuapp.com/past/2010/4/13/rethinking_cron/>`_ and the `clockwork <https://github.com/Rykian/clockwork>`_ Ruby module.

Distributed under the MIT license. See `LICENSE.txt <https://github.com/Dhaxor/schedule/blob/master/LICENSE.txt>`_ for more information.

https://github.com/Dhaxor/schedule
