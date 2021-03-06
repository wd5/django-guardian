.. _testing:

Testing
=======

Introduction
------------

``django-guardian`` is extending capabilities of Django's authorization
facilities and as so, it changes it's security somehow. It is extremaly
important to provide as simplest :ref:`api` as possible. 

According to OWASP_, `broken authentication
<http://www.owasp.org/index.php/Top_10_2010-A3>`_ is one of most commonly
security issue exposed in web applications.

Having this on mind we tried to build small set of necessary functions and
created a lot of testing scenarios. Neverteless, if anyone would found a bug in
this application, please take a minute and file it at `issue-tracker`_.

Running tests
-------------

Tests are run by Django's buildin test runner. To call it simply run::

    $ python setup.py test

or inside a project with ``guardian`` set at ``INSTALLED_APPS``::

    $ python manage.py test guardian

Coverage support
----------------

Coverage_ is a tool for measuring code coverage of Python programs. It is great
for tests and we use it as a backup - we try to cover 100% of the code used by
``django-guardian``. This of course does *NOT* mean that if all of the codebase
is covered by tests we can be sure there is no bug (as specification of almost
all applications requries some unique scenarios to be tested). On the other hand
it definitely helps to track missing parts.

To run tests with coverage_ support and show the report after we have provided
simple bash script which can by called by running::

    $ ./run_test_and_report.sh


Result should be somehow similar to following::

    (...)
    ................................................
    ----------------------------------------------------------------------
    Ran 48 tests in 2.516s

    OK
    Destroying test database 'default'...
    Name                                  Stmts   Exec  Cover   Missing
    -------------------------------------------------------------------
    guardian/__init__                         4      4   100%   
    guardian/backends                        20     20   100%   
    guardian/conf/__init__                    1      1   100%   
    guardian/core                            29     29   100%   
    guardian/exceptions                       8      8   100%   
    guardian/management/__init__             10     10   100%   
    guardian/managers                        40     40   100%   
    guardian/models                          36     36   100%   
    guardian/shortcuts                       30     30   100%   
    guardian/templatetags/__init__            1      1   100%   
    guardian/templatetags/guardian_tags      39     39   100%   
    guardian/utils                           13     13   100%   
    -------------------------------------------------------------------
    TOTAL                                   231    231   100% 

.. _owasp: http://www.owasp.org/
.. _issue-tracker: http://github.com/lukaszb/django-guardian
.. _coverage: http://nedbatchelder.com/code/coverage/

