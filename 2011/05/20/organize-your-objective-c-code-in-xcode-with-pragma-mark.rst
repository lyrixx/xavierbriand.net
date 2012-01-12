public: yes
tags: [cocoa, xcode]

Organize your Objective-C code in Xcode with #pragma mark
=========================================================

As I didn't know it, ``CTRL+MAJ+2`` command opens a contextual popin listing your file's methods.

While coding, it can be a mess quickly in this list. This is where mark saves your life.

Xcode gives you a **pragma mark** metatag you can use in two ways:

First:

.. code-block:: objective-c

  #pragma mark -

adds a separator (as ``<hr/>`` html tag) in the contextual list.

Second:

.. code-block:: objective-c

    #pragma mark Your great not to long description

gathers methods in a group named *Your great not to long description*.

This two uses of Pragma mark allow you to visualy organise your code.
