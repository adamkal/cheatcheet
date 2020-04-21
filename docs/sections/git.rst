Git VCS
=======================================

Show all changed files
---------------------------------------

.. code-block:: bash

   git diff --stat | head -n -1 | awk '{ print $1 }'


Show all files change since master branch
*****************************************

.. code-block:: bash

   git diff --stat origin/master | head -n -1 | awk '{ print $1 }'


Copy to clipboard diff of black of changed files
************************************************

.. code-block:: bash

   git diff --stat | head -n -1 | awk '{ print $1}' | xargs black --diff | clipcopy

`clipcopy` might differ on distros and shells but basically copies stdout to
cliboard.

This works nice with PyCharm. You can use "Apply Patch from Clipboard" to see
diff and apply only the lines you changed/want.