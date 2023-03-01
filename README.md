```
Subject: dnstools
From: Todd T. Fries <todd@fries.net>
To: anyone reading this

I wanted to see what SOA records were in sync, but ``host -C'' didn't
tell me what DNS server was busted.  So I decided to fix that.

Sample output:

$ ksh ./nscheck www.freedaemon.com twitter.com sf.net google.com aol.com weirdnet.nl .
[key: (1) = not found in tld glue, (2) = in tld glue, not in NS list]
==> www.freedaemon.com (zone=freedaemon.com)
    NS ns0.l4.FreeDaemonHosting.net.
                        2607:f2f8:1800::2 | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
                             208.79.89.90 | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
    NS ns0.l1.FreeDaemonHosting.com.
                     2001:470:ba1b:100::1 | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
                           66.210.104.251 | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
    NS ns1.l1.FreeDaemonHosting.net.
                      2001:470:817c:d::5d | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
                           98.174.183.149 | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
    NS ns1.l1.FreeDaemonHosting.com.
                      2001:470:817c:d::5d | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
                           98.174.183.149 | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
    NS ns0.l4.FreeDaemonHosting.com.
                        2607:f2f8:1800::2 | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
                             208.79.89.90 | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
    NS ns0.l1.FreeDaemonHosting.net.
                     2001:470:ba1b:100::1 | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
                           66.210.104.251 | ns0.FreeDaemonHosting.com. hostmaster.FreeDaemonHosting.com. 82 3600 7200 2592000 3600
==> twitter.com (zone=twitter.com)
    NS ns1.p34.dynect.net.
                    2001:500:90:1::34 (1) | ns1.p26.dynect.net. zone-admin.dyndns.com. 2007113855 3600 600 604800 60
                             208.78.70.34 | ns1.p26.dynect.net. zone-admin.dyndns.com. 2007113855 3600 600 604800 60
    NS ns3.p34.dynect.net.
                    2001:500:94:1::34 (1) | ns1.p26.dynect.net. zone-admin.dyndns.com. 2007113855 3600 600 604800 60
                             208.78.71.34 | ns1.p26.dynect.net. zone-admin.dyndns.com. 2007113855 3600 600 604800 60
    NS ns4.p34.dynect.net.
                            204.13.251.34 | ns1.p26.dynect.net. zone-admin.dyndns.com. 2007113855 3600 600 604800 60
    NS ns2.p34.dynect.net.
                            204.13.250.34 | ns1.p26.dynect.net. zone-admin.dyndns.com. 2007113855 3600 600 604800 60
==> sf.net (zone=sf.net)
    NS ns3.p03.dynect.net.
                     2001:500:94:1::3 (1) | ns1.p03.dynect.net. hostmaster.corp.sourceforge.com. 2012092500 3600 600 604800 60
                              208.78.71.3 | ns1.p03.dynect.net. hostmaster.corp.sourceforge.com. 2012092500 3600 600 604800 60
    NS ns2.p03.dynect.net.
                             204.13.250.3 | ns1.p03.dynect.net. hostmaster.corp.sourceforge.com. 2012092500 3600 600 604800 60
    NS ns1.p03.dynect.net.
                     2001:500:90:1::3 (1) | ns1.p03.dynect.net. hostmaster.corp.sourceforge.com. 2012092500 3600 600 604800 60
                              208.78.70.3 | ns1.p03.dynect.net. hostmaster.corp.sourceforge.com. 2012092500 3600 600 604800 60
    NS ns4.p03.dynect.net.
                             204.13.251.3 | ns1.p03.dynect.net. hostmaster.corp.sourceforge.com. 2012092500 3600 600 604800 60
==> google.com (zone=google.com)
    NS ns1.google.com.
                            216.239.32.10 | ns1.google.com. dns-admin.google.com. 2012100401 7200 1800 1209600 300
    NS ns4.google.com.
                            216.239.38.10 | ns1.google.com. dns-admin.google.com. 2012100401 7200 1800 1209600 300
    NS ns2.google.com.
                            216.239.34.10 | ns1.google.com. dns-admin.google.com. 2012100401 7200 1800 1209600 300
    NS ns3.google.com.
                            216.239.36.10 | ns1.google.com. dns-admin.google.com. 2012100401 7200 1800 1209600 300
==> aol.com (zone=aol.com)
    NS dns-07.ns.aol.com.
                             64.236.1.107 | dns-01.ns.aol.com. hostmaster.aol.net. 357951562 43200 180 2592000 300
    NS dns-02.ns.aol.com.
                          205.188.157.232 | dns-01.ns.aol.com. hostmaster.aol.net. 357951562 43200 180 2592000 300
    NS dns-01.ns.aol.com.
                             64.12.51.132 | dns-01.ns.aol.com. hostmaster.aol.net. 357951562 43200 180 2592000 300
    NS dns-06.ns.aol.com.
                            207.200.73.80 | dns-01.ns.aol.com. hostmaster.aol.net. 357951562 43200 180 2592000 300
==> weirdnet.nl (zone=weirdnet.nl)
    NS ns.paphosting.eu.
                        2001:788:2:117::2 | ns.paphosting.net. hostmaster.weirdnet.nl. 2012012500 600 200 604800 600
                           62.220.146.194 | ns.paphosting.net. hostmaster.weirdnet.nl. 2012012500 600 200 604800 600
    NS ns.paphosting.net.
         2001:7b8:3:47:20d:b9ff:fe14:70d4 | ns.paphosting.net. hostmaster.weirdnet.nl. 2012012500 600 200 604800 600
                           213.154.229.21 | ns.paphosting.net. hostmaster.weirdnet.nl. 2012012500 600 200 604800 600
    NS ns.paphosting.nl.
                           2a02:898:28::3 | ns.paphosting.net. hostmaster.weirdnet.nl. 2012012500 600 200 604800 600
                             94.142.245.3 | ns.paphosting.net. hostmaster.weirdnet.nl. 2012012500 600 200 604800 600
==> . (zone=.)
    NS g.root-servers.net.
                             192.112.36.4 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS b.root-servers.net.
                           192.228.79.201 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS c.root-servers.net.
                              192.33.4.12 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS d.root-servers.net.
                           2001:500:2d::d | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
                              128.8.10.90 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS f.root-servers.net.
                           2001:500:2f::f | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
                              192.5.5.241 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS l.root-servers.net.
                       2001:500:3::42 (1) | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
                              199.7.83.42 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS j.root-servers.net.
                   2001:503:c27::2:30 (1) | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
                            192.58.128.30 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS i.root-servers.net.
                         2001:7fe::53 (1) | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
                            192.36.148.17 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS h.root-servers.net.
                     2001:500:1::803f:235 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
                              128.63.2.53 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS a.root-servers.net.
                      2001:503:ba3e::2:30 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
                               198.41.0.4 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS e.root-servers.net.
                           192.203.230.10 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS k.root-servers.net.
                          2001:7fd::1 (1) | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
                             193.0.14.129 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
    NS m.root-servers.net.
                         2001:dc3::35 (1) | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
                             202.12.27.33 | a.root-servers.net. nstld.verisign-grs.com. 2012100401 1800 900 604800 86400
$

Enjoy!

Thanks,
--
Todd Fries .. todd@fries.net .. twitter:@unix2mars .. github:toddfries

Label   | Data           | Notes
--------+----------------+------------------------------
Motto   | In support of  | free software solutions.
Phone   | 1.405.252.0702 | SMS/voice everywhere
Mobile  | 1.405.203.6124 | SMS/voice mobile only
Employer| self employed  | Free Daemon Consulting, LLC
Address | PO Box 16169   | Oklahoma City, OK 73113-2169
PGP     | 3F42004A       |
```

If you find this useful and wish to donate, I accept donations:

- BTC: [16DnvYrewFD8aJqLqwEXTwpsPQEj3XpNXF](bitcoin:16DnvYrewFD8aJqLqwEXTwpsPQEj3XpNXF)

- DCR: [DsXR5efVHrB6UyG2hoB7BuUBXsQc7yPAf4n](decred:DsXR5efVHrB6UyG2hoB7BuUBXsQc7yPAf4n)
