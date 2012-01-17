public: yes
tags: [solr]

How to run Apache SolR in debian?
=================================

First, install JDK 6/7 (let install version 6):

.. code-block:: bash

  apt-get install openjdk-6-jdk

Then get Apache `SolR source`_:

.. code-block:: bash

    wget http://apache.crihan.fr/dist//lucene/solr/3.5.0/apache-solr-3.5.0.tgz
    tar -xvzf apache-solr-3.5.0.tgz

Now, launch the built-in Jetty servlet container with example config:

.. code-block:: bash

    cd apache-solr-3.5.0/example
    java -jar start.jar

Check your new SolR instance web admin at 
``http://localhost:8983/solr/admin``

.. _`SolR source`: http://apache.crihan.fr/dist//lucene/solr/
