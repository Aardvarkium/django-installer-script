===============
Release History
===============

2.6.1

  - Fixed virtualenvwrapper_get_python_version (:bbissue:`73`).

2.6

  - Fixed a problem with hook script line endings under Cygwin
    (:bbissue:`68`).
  - Updated documentation to include a list of the compatible shells
    (:ref:`supported-shells`) and Python versions
    (:ref:`supported-versions`) (:bbissue:`70`).
  - Fixed installation dependency on virtualenv (:bbissue:`60`).
  - Fixed the method for determining the Python version so it works
    under Python 2.4 (:bbissue:`61`).
  - Converted the test infrastructure to use `tox
    <http://codespeak.net/tox/index.html>`_ instead of home-grown
    scripts in the Makefile.

2.5.3

  - Point release uploaded to PyPI during outage on doughellmann.com.

2.5.2

  - Apply patch from Zach Voase to fix :ref:`command-lsvirtualenv`
    under zsh. Resolves :bbissue:`64`.

2.5.1

  - Make :ref:`command-workon` list brief environment details when run
    without argument, instead of full details.

2.5

  - Add :ref:`command-showvirtualenv` command.  Modify
    :ref:`command-lsvirtualenv` to make verbose output the default.

2.4

  - Add :ref:`command-lsvirtualenv` command with ``-l`` option to run
    :ref:`scripts-get_env_details` hook instead of always running it
    when :ref:`command-workon` has no arguments.

2.3

  - Added ``get_env_details`` hook.

2.2.2

  - Integrate Fred Palmer's patch to escape more shell commands to
    avoid aliases.  Resolves :bbissue:`57`.
  - Fix a problem with egrep argument escaping (:bbissue:`55`).
  - Fix a problem with running mkvirtualenv without arguments (:bbissue:`56`).

2.2.1

  - Escape ``which`` calls to avoid aliases. Resolves :bbissue:`46`.
  - Integrate Manuel Kaufmann's patch to unset GREP_OPTIONS before
    calling grep.  Resolves :bbissue:`51`.
  - Escape ``$`` in regex to resolve :bbissue:`53`.
  - Escape ``rm`` to avoid issues with aliases and resolve
    :bbissue:`50`.

2.2

  - Switched hook loader execution to a form that works with Python
    2.4 to resolve :bbissue:`43`.
  - Tested under Python 2.7b1.  See :bbissue:`44`.
  - Incorporated performance improvements from David Wolever.  See
    :bbissue:`38`.
  - Added some debug instrumentation for :bbissue:`35`.

2.1.1

  - Added `Spanish translation for the documentation
    <http://www.doughellmann.com/docs/virtualenvwrapper/es/>`__ via
    Manuel Kaufmann's fork at
    http://bitbucket.org/humitos/virtualenvwrapper-es-translation/
  - Fixed improper use of python from ``$PATH`` instead of the
    location where the wrappers are installed.  See :bbissue:`41`.
  - Quiet spurrious error/warning messages when deactivating a
    virtualenv under zsh.  See :bbissue:`42`.

2.1

  - Add support for ksh.  Thanks to Doug Latornell for doing the
    research on what needed to be changed.
  - Test import of virtualenvwrapper.hook_loader on startup and report
    the error in a way that should help the user figure out how to fix
    it (:bbissue:`33`).
  - Update :ref:`command-mkvirtualenv` documentation to include the
    fact that a new environment is activated immediately after it is
    created (:bbissue:`30`).
  - Added hooks around :ref:`command-cpvirtualenv`.
  - Made deactivation more robust, especially under ksh.
  - Use Python's ``tempfile`` module for creating temporary filenames
    safely and portably.
  - Fix a problem with ``virtualenvwrapper_show_workon_options`` that
    caused it to show ``*`` as the name of a virtualenv when no
    environments had yet been created.
  - Change the hook loader so it can be told to run only a set of
    named hooks.
  - Add support for listing the available hooks, to be used in help
    output of commands like virtualenvwrapper.project's mkproject.
  - Fix mkvirtualenv -h option behavior.
  - Change logging so the $WORKON_HOME/hook.log file rotates after
    10KiB.

2.0.2

  - Fixed :bbissue:`32`, making virtualenvwrapper.user_scripts compatible
    with Python 2.5 again.

2.0.1

  - Fixed :bbissue:`29`, to use a default value for ``TMPDIR`` if it
    is not set in the user's shell environment.

2.0

  - Rewrote hook management using Distribute_ entry points to make it
    easier to share extensions.

.. _Distribute: http://packages.python.org/distribute/

1.27
  
  - Added cpvirtualenv command [Thomas Desvenain]

1.26

  - Fix a problem with error messages showing up during init for users
    with the wrappers installed site-wide but who are not actually
    using them.  See :bbissue:`26`.
  - Split up the tests into multiple files.
  - Run all tests with all supported shells.

1.25

  - Merged in changes to cdsitepackages from William McVey.  It now
    takes an argument and supports tab-completion for directories
    within site-packages.

1.24.2

  - Add user provided :ref:`tips-and-tricks` section.
  - Add link to Rich Leland's screencast to :ref:`references` section.

1.24.1

  - Add license text to the header of the script.

1.24

  - Resolve a bug with the preactivate hook not being run properly.
    Refer to :bbissue:`21` for complete details.

1.23

  - Resolve a bug with the postmkvirtualenv hook not being run
    properly.  Refer to :bbissue:`19` and :bbissue:`20` for complete
    details.

1.22

  - Automatically create any missing hook scripts as stubs with
    comments to expose the feature in case users are not aware of it.

1.21

  - Better protection of ``$WORKON_HOME`` does not exist when the
    wrapper script is sourced.

1.20

  - Incorporate lssitepackages feature from Sander Smits.
  - Refactor some of the functions that were using copy-and-paste code
    to build path names.
  - Add a few tests.

1.19

  - Fix problem with add2virtualenv and relative paths. Thanks to Doug
    Latornell for the bug report James Bennett for the suggested fix.

1.18.1

  - Incorporate patch from Sascha Brossmann to fix a
    :bbissue:`15`. Directory normalization was causing ``WORKON_HOME``
    to appear to be a missing directory if there were control
    characters in the output of ``pwd``.

1.18

  - Remove warning during installation if sphinxcontrib.paverutils is
    not installed. (:bbissue:`10`)
  - Added some basic developer information to the documentation.
  - Added documentation for deactivate command.

1.17

  - Added documentation updates provided by Steve Steiner.

1.16

  - Merged in changes to ``cdvirtualenv`` from wam and added tests and
    docs.
  - Merged in changes to make error messages go to stderr, also
    provided by wam.

1.15
  - Better error handling in mkvirtualenv.
  - Remove bogus VIRTUALENV_WRAPPER_BIN variable.

1.14
  - Wrap the virtualenv version of deactivate() with one that lets us
    invoke the predeactivate hooks.
  - Fix virtualenvwrapper_show_workon_options for colorized versions
    of ls and write myself a note so I don't break it again later.
  - Convert test.sh to use true tests with `shunit2
    <http://shunit2.googlecode.com/>`_

1.13

  - Fix :bbissue:`5` by correctly handling symlinks and limiting the
    list of envs to things that look like they can be activated.

1.12

  - Check return value of virtualenvwrapper_verify_workon_home
    everywhere, thanks to Jeff Forcier for pointing out the errors.
  - Fix instructions at top of README, pointed out by Matthew Scott.
  - Add cdvirtualenv and cdsitepackages, contributed by James Bennett.
  - Enhance test.sh.

1.11

  - Optimize virtualenvwrapper_show_workon_options.
  - Add global postactivate hook.

1.10

  - Pull in fix for colorized ls from Jeff Forcier
    (:bbchangeset:`b42a25f7b74a`).

1.9

  - Add more hooks for operations to run before and after creating or
    deleting environments based on changes from Chris Hasenpflug.

1.8.1

  - Corrected a problem with change to mkvirtualenv that lead to
    release 1.8 by using an alternate fix proposed by James in
    comments on release 1.4.

1.8

  - Fix for processing the argument list in mkvirtualenv from
    jorgevargas (:bbissue:`1`)

1.7

  - Move to bitbucket.org for hosting
  - clean up TODO list and svn keywords
  - add license section below

1.6.1

  - More zsh support (fixes to rmvirtualenv) from Byron Clark.

1.6

  - Add completion support for zsh, courtesy of Ted Leung.

1.5

  - Fix some issues with spaces in directory or env names.  They still
    don't really work with virtualenv, though.
  - Added documentation for the postactivate and predeactivate scripts.

1.4

  - Includes a new .pth management function based on work contributed
    by James Bennett and Jannis Leidel.

1.3.x

  - Includes a fix for a nasty bug in rmvirtualenv identified by John Shimek.
