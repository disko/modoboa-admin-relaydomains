#####
Setup
#####

To tell Postfix this feature exists, you must generate two new map
files and then update your configuration.

To generate the map files, run the following command::

  $ modoboa-admin.py postfix_maps --extensions modoboa-admin-relaydomains --dbtype <the database you use> <path>

Replace values between ``<>`` by yours.

Edit the :file:`/etc/postfix/main.cf` file and copy the following
lines inside::

  relay_domains = <driver>:/etc/postfix/sql-relaydomains.cf
  transport_maps = 
      <driver>:/etc/postfix/sql-relaydomains-transport.cf
      <driver>:/etc/postfix/sql-relaydomain-aliases-transport.cf

  smtpd_recipient_restrictions =
      permit_mynetworks
      reject_unauth_destination
      check_recipient_access 
          <driver>:/etc/postfix/sql-relay-recipient-verification.cf

Replace ``<driver>`` by the name of the database you use.

Reload postfix.
