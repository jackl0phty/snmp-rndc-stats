- DESCRIPTION:
==============

* __snmp_rndc_stats.pl__ is a [Perl](http://www.perl.org/)
command-line utility which will allow you to display Bind9
stats via [SNMP](http://en.wikipedia.org/wiki/Simple_Network_Management_Protocol).
A Network Monitoring solution such as [Zenoss](http://www.zenoss.com/)
or [Nagios](http://www.nagios.org/) can then use those stats to build graphs using 
[RRDtool](http://www.mrtg.org/rrdtool/) representing DNS stats.

- LICENSE:
==========

+ This software is licensed under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0).
A copy of the licese is also available in the LICENSE file of this repo.

- REQUIREMENTS:
===============

+  __snmp_rndc_stats.pl__ should be executed on the server running 
your Network monitoring solution such as Zenoss or Nagios.

+ Ensure firewall access has been granted on your Bind9 server
to allow SNMP connections from your network monitor.

+ You may test the output of __snmp_rndc_stats.pl__, by running it manually.
However, the output is meant to be passed to SNMPD. Therefore, the output
may appear to you as a useless string of numbers without a newline at the end.

- OPTIONAL-COMMAND-LINE-ARGUMENTS:
==================================

+ __--success__ Prints rndc success stats.

+ __--referral__ Prints rndc referral stats.

+ __--nxrrset__ Prints rndc nxrrset stat.

+ __--nxdomain__ Prints rndc nxdomain stats.

+ __--recursion__ Prints rndc recursion stats.

__--failure__ Prints rndc failure stats.

+ __--all__ Prints all rndc stats.

- DIAGNOSTICS:
=============

+ The only errors generated are file open errors.  Carp confess is used to
generate a backtrace of any resulting errors.

- ATTRIBUTES:
=============

+ There are currently no attributes for this cookbook.

- USAGE:
========

+ As previously mentioned, this script is meant to send output to SNMPD.
However, the following optional commands are supported:

+ ./snmp_rndc_stats.pl --success
+ ./snmp_rndc_stats.pl --referral
+ ./snmp_rndc_stats.pl --nxrrset
+ ./snmp_rndc_stats.pl --nxdomain
+ ./snmp_rndc_stats.pl --recursion
+ ./snmp_rndc_stats.pl --failure
+ ./snmp_rndc_stats.pl --all
