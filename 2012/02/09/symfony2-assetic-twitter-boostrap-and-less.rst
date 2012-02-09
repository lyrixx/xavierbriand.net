public: yes
tags: [Symfony2, assetic, bootstrap, less, mac]

Symfony2, Assetic, Twitter bootstrap and less on Mac
====================================================

Wanna use the new `Twitter bootstrap css framework`_ on Symfony2? Follow this:

To compile less files, we need to install ``node js`` and ``less`` module.

If you don't know `Brew`_  you really should:

.. code-block:: bash

    Xavier@MacBook:~$ brew info node
    node 0.6.10
    http://nodejs.org/
    Not installed

    Homebrew has NOT installed npm. We recommend the following method of
    installation:
        curl http://npmjs.org/install.sh | sh

.. code-block:: bash

    brew install node

And check ``node -v``:

.. code-block:: bash

    xavier@MacBook:~$ node -v
    v0.6.10

Node less module via npm installer:

.. code-block:: bash

    curl http://npmjs.org/install.sh | sh

or

.. code-block:: bash

    cd ~/source
    git clone https://github.com/isaacs/npm.git
    cd npm
    make
    make install

Again check ``npm`` command answer:

.. code-block:: bash

    xavier@MacBook:~/source/npm[master]$ npm

    Usage: npm <command>

    ...

Now, we ask ``npm`` to install less node module:

.. code-block:: bash

    npm install -g less

Check ``npm list -g``:

.. code-block:: bash

    xavier@MacBook:~/source/npm[master]$ npm list -g
    /usr/local/lib
    ├── less@1.2.1
    ├─┬ npm@1.1.0-3
    ...

Now get back to our Symfony2 project.

For mine, I had **Twitter boostrap** as vendor (via ``deps`` file) and symlinked what I need to the
``Resource/public`` folder of my bundle.

However we need to setup assetic's less filter in our app:

.. code-block:: yaml

    #in app/config/config.yml

    assetic:
        debug:          %kernel.debug%
        use_controller: false
        bundles:        ['MyBundle']
        filters:
            cssrewrite: ~
            less:
                node:       /usr/local/bin/node
                node_paths: [/usr/local/lib/node, /usr/local/lib/node_modules]

Now update your twig layout:

.. code-block:: jinja

    {% stylesheets
        '@XavierMyBundle/Resources/public/less/bootstrap.less'
        filter='less'
        output='css/main.css'
    %}
    <link rel="stylesheet" href="{{ asset_url }}">
    {% endstylesheets %}

and refresh your page!

PS: If your have an error on less compilation related to ``sys`` and ``util``
module, update your assetic version.

.. _`Twitter bootstrap css framework`: http://twitter.github.com/bootstrap/
.. _`Brew`: http://mxcl.github.com/homebrew/
