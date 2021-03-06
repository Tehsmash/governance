============================
Consistent Testing Interface
============================

OpenStack has a lot of projects. For each project, the OpenStack CI system
needs to be able to perform a lot of tasks. If each project has a slightly
different way to accomplish those tasks, it makes the management of a
consistent testing infrastructure very difficult to deal with. Additionally,
because of the high volume of development changes and testing, the testing
infrastructure has to be able to pre-cache artifacts that are normally fetched
over the internet. To that end, each project should support a consistent
interface for driving tests and other necessary tasks.

The following tasks are required for every project. Every project must:

- Execute tests
- Enforce code style
- Generate a code coverage report
- Generate a source tarball
- Generate documentation

The following are other common tasks, which may not be relevant for every
project:

- Enforce code coverage
- Generate a release artifact
- Publish a release artifact
- Import translation strings
- Export translation strings

Tools and approaches vary by language, please choose which language is
relevant to you.

The following operating systems are the most popular when deploying OpenStack:

- Ubuntu (`latest LTS`_)
- CentOS (`latest stable`_)

  .. note::

    The CentOS distribution is derived from the sources of Red Hat Enterprise Linux (RHEL).
    In reality, RHEL is more popular than CentOS but we can't use this platform
    on upstream gates, so we rely on CentOS.

Each project should run some functional tests on these platforms so we make sure
OpenStack works with distros used in production. The scope of these functional tests
are discussed for every project, and may adjust their coverage depending of resources
and support investment.
These tests are run by using existing tooling, which comes with a reasonable
expectation that it's viable on the indicated distributions.

Sometimes, these distributions might not support all dependencies required
by new features in OpenStack. Development of these features should not be
blocked, though it has to be documented in project release notes, and some
tests might have to be skipped on these distributions.

.. _latest LTS: https://wiki.ubuntu.com/Releases
.. _latest stable: https://www.centos.org/download/

.. toctree::
   :maxdepth: 1
   :glob:

   cti/*
