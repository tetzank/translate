
.. _pages/toolkit/poclean#poclean:

poclean
*******

This is a rudimentary tool to produce a clean file from an unclean file (Trados/Wordfast) by stripping out the tw4win indicators.

.. _pages/toolkit/poclean#usage:

Usage
=====

::

  poclean <input> <output>

Where:

| <input> | is the text versions of the unclean RTF files |
| <output>  | is the intended output file / directory |

Options:

| --version            | show program's version number and exit  |
| -h, --help           | show this help message and exit   |
| --manpage            | output a manpage based on the help  |
| :doc:`--progress=progress <option_progress>`  | show progress as: dots, none, bar, names, verbose  |
| :doc:`--errorlevel=errorlevel <option_errorlevel>`  | show errorlevel as: none, message, exception, traceback  |
| -iINPUT, --input=INPUT   | read from INPUT in pot format  |
| -xEXCLUDE, --exclude=EXCLUDE  | exclude names matching EXCLUDE from input paths  |
| -oOUTPUT, --output=OUTPUT     | write to OUTPUT in po, pot formats  |
| -tTEMPLATE, --template=TEMPLATE   | read from TEMPLATE in po, pot formats  |
| :doc:`--psyco=MODE <option_psyco>`         | use psyco to speed up the operation, modes: none, full, profile  |

.. _pages/toolkit/poclean#examples:

Examples
========

To create a text version of the unclean RTF file, you need UnRTF, available here: `project site <http://www.gnu.org/software/unrtf/unrtf.html>`_ or `here (windows) <http://gnuwin32.sourceforge.net/packages/unrtf.htm>`_. ::

  unrtf translation.rtf  --text > translation.po

You might need to convert the encoding of the file, with iconv, for example::

  iconv -f latin1 -t utf-8 translation.po > new_translation.po

Now you can clean the file with poclean ::

  poclean new_translation.po clean_translation.po
