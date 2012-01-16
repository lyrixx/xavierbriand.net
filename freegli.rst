public: no

Freegli.com
===========

Check `our website`_ to get, every day at 10:10 am, an iPhone/iPad game for free.

*Only available in french, but games are often in english.*

This site has been written in PHP with symfony 1.4 [#sf1.4]_ framework and doctrine 1.2 ORM [#doctrine]_ with MySQL.

It's basically a catalogue website with private pages. The hard part is, what you will never see, the back office. 
It allows freegli team to track apps from iTunes store, handle users' subscriptions and push notification (and much more indeed).

But the major part of traffic comes from the iPhone app via Rest webservices. To speed up this webservices, pages are served through
a reverse proxy called Varnish [#varnish]_.

The v2 is currently under development. It will be powered by Symfony2 [#sf2]_ PHP framework and PostgreSQL database (with Pomm [#pomm]_ component).
This new version will be able to scale up with the constant increase of success of our service.

You can find some of my work under MIT licence on Github:

* `APNs`_ component
* `FreegliAPNSBundle`_ for Symfony2
* `iTunesStoreWSSearch`_ component
* `FreegliITunesStoreWSSearchBundle`_ for Symfony2

.. _our website: http://www.freegli.com/
.. _symfony project website: http://symfony-project.org/
.. _Doctrine website: http://doctrine-orm.com/
.. _Varnish website: http://.com/
.. _Symfony website: http://symfony.com/
.. _Pomm website: http://pomm.com/
.. _APNs: https://github.com/Freegli/APNs
.. _FreegliAPNSBundle: https://github.com/Freegli/FreegliAPNSBundle
.. _iTunesStoreWSSearch: https://github.com/Freegli/iTunesStoreWSSearch
.. _FreegliITunesStoreWSSearchBundle: https://github.com/Freegli/FreegliITunesStoreWSSearchBundle

.. [#sf1.4] symfony is a full stack framework written in PHP 5.2. See `symfony project website`_ 
.. [#doctrine] Doctrine is a ORM base on the Active Record design pattern. See `doctrine website`_ 
.. [#varnish] Varnish is a reverse proxy able to improve your website performances. See `Varnish website`_ 
.. [#sf2] Symfony2 is a full stack framework written in PHP 5.3. See `Symfony website`_ 
.. [#pomm] Pomm PHP library is a PostgreSQL connection object wrapper. See `Pomm website`_ 

.. TODO:
   check links
