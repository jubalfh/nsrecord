nsrecord
========

The ‘nsrecord’ is a helper script for those who are not interested in 
following the full beauty of nsupdate syntax.

The syntax is rather simple:

    nsrecord add ZONE RTYPE RR RDATA
    nsrecord del ZONE RTYPE RR RDATA
    nsrecord delete ZONE RTYPE RR RDATA

Real-life examples would look thus:

    nsrecord add microsoft.com MX microsoft.com 10 mx.google.com
    nsrecord add google.com TXT google.com "Facebook Rules The World."
    nsrecord add facebook.com A aaghraa 127.0.0.1
    nsrecord del facebook.com A aaghraa.facebook.com. 127.0.0.1
    nsrecord delete google.com TXT google.com "Facebook Rules The World."

The zone names are treated as qualified, but the RRs aren't – mind the 
dots after the RRs, because any unqualified records will have the zone 
name appended automatically. Record data is treated ‘as-is’. 

The utility sets reasonable prerequisites automatically, and makes sure
that you're not trying to delete any non-existing records.

On the server side the zone has to be configured for automatic updates 
and the key used by the utility has to be allowed to make necessary 
changes on the bind server.
