=========================
kids.txt
=========================

.. image:: http://img.shields.io/pypi/v/kids.txt.svg?style=flat
   :target: https://pypi.python.org/pypi/kids.txt/
   :alt: Latest PyPI version

.. image:: http://img.shields.io/pypi/dm/kids.txt.svg?style=flat
   :target: https://pypi.python.org/pypi/kids.txt/
   :alt: Number of PyPI downloads

.. image:: http://img.shields.io/travis/0k/kids.txt/master.svg?style=flat
   :target: https://travis-ci.org/0k/kids.txt/
   :alt: Travis CI build status

.. image:: http://img.shields.io/coveralls/0k/kids.txt/master.svg?style=flat
   :target: https://coveralls.io/r/0k/kids.txt
   :alt: Test coverage


``kids.txt`` is a Python library providing helpers to manage text.
It's part of 'Kids' (for Keep It Dead Simple) library.

It is, for now, a very humble package.


Features
========

using ``kids.txt``:

- You'll have a ``indent`` / ``dedent`` command also in python 2.
- You'll be able to ``wrap`` text keeping the paragraph separated.


Installation
============

You don't need to download the GIT version of the code as ``kids.txt`` is
available on the PyPI. So you should be able to run::

    pip install kids.txt

If you have downloaded the GIT sources, then you could add install
the current version via traditional::

    python setup.py install

And if you don't have the GIT sources but would like to get the latest
master or branch from github, you could also::

    pip install git+https://github.com/0k/kids.txt

Or even select a specific revision (branch/tag/commit)::

    pip install git+https://github.com/0k/kids.txt@master


Usage
=====


indent
------

You can easily indent text with::

    >>> from __future__ import print_function
    >>> from kids import txt

    >>> string = 'This is first line.\nThis is second line\n'

    >>> print(txt.indent(string, prefix="| "))
    | This is first line.
    | This is second line
    |


dedent
------

You can also dedent text::

    >>> print(txt.dedent(
    ...    '''This is a doc
    ...
    ...       with fancy indentation, that should just work also.
    ...       Without removing too much neither as:
    ...          - more space.'''))
    This is a doc
    <BLANKLINE>
    with fancy indentation, that should just work also.
    Without removing too much neither as:
       - more space.


paragrap_wrap
-------------

Wrap paragraph separately::

    >>> string = 'This is first paragraph which is quite long don\'t you \
    ... think ? Well, I think so.\n\nThis is second paragraph\n'

    >>> print(txt.paragraph_wrap(string))
    This is first paragraph which is quite long don't you think ? Well, I
    think so.
    This is second paragraph

    Notice that that each paragraph has been wrapped separately.


Contributing
============

Any suggestion or issue is welcome. Push request are very welcome,
please check out the guidelines.


Push Request Guidelines
-----------------------

You can send any code. I'll look at it and will integrate it myself in
the code base and leave you as the author. This process can take time and
it'll take less time if you follow the following guidelines:

- check your code with PEP8 or pylint. Try to stick to 80 columns wide.
- separate your commits per smallest concern.
- each commit should pass the tests (to allow easy bisect)
- each functionality/bugfix commit should contain the code, tests,
  and doc.
- prior minor commit with typographic or code cosmetic changes are
  very welcome. These should be tagged in their commit summary with
  ``!minor``.
- the commit message should follow gitchangelog rules (check the git
  log to get examples)
- if the commit fixes an issue or finished the implementation of a
  feature, please mention it in the summary.

If you have some questions about guidelines which is not answered here,
please check the current ``git log``, you might find previous commit that
would show you how to deal with your issue.


License
=======

Copyright (c) 2015 Valentin Lab.

Licensed under the `BSD License`_.

.. _BSD License: http://raw.github.com/0k/kids.txt/master/LICENSE
