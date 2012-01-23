public: no
tags: [debian, scalability, load, slow query, mysql]

Feedback about managing a sudden traffic peak on a web application
==================================================================

Last Friday, freegli's team launching a media campaign. A 7pm, the freegli.com
website went down: no web server, so ssh access.

This article is about managing this kind of (stressful) situation in live and
prevent it occurs again.

The monitoring of server shows CPU and RAM used at 100%. After a hard reboot, I
check the system load. System load can be seen using ``uptime`` or
``cat /proc/loadavg``.

According to ``uptime`` man page:

  **System load averages is the average number of processes** that are either in
  a runnable or uninterruptable state. A process in a runnable state is either
  **using the CPU or waiting to use the CPU.** A process in uninterruptable
  state is waiting for some I/O access, eg waiting for disk. The averages are
  taken over the three time intervals.

  Load averages are not normalized for the number of CPUs in a system, so a load
  average  of 1 means a single CPU system is loaded all the time while on a 4
  CPU system it means it was idle 75% of the time.

With 1 CPU and a load of between 7 and 11, one might say the server was a bit
busy.

``top`` command shows `mysqld` was the greediest process. I thought first it was
the download logging mechanism fault (one select and one insert per download,
and a lot of download). But it was not.

Then I thought about a very expensive query to compute our *top downloaded apps*
list. A week before, I installed a reverse proxy called Varnish to cache this
expensive page. So even if the request was expensive, it was done only every
15mn.

Checking the resource, varnish get me a 503 error... The application was to
busy to compute the list. Damn it.

The server's load remains of between 9 and 11, the *Top list* was broken.
So we decided to cut this service, to the benefit of the rest of the
application.

Immediate action leads to immediate effect, the load dropped down to 0.5.
**The root cause was spotted**.
