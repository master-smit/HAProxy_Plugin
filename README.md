# Openshift 2.0 Ruby plugin for External HAProxy

1. Requires HAProxy to be configured in 4 separate conf files

  * /etc/haproxy/haproxy.cfg
  * /etc/haproxy/conf/admin.conf
  * /etc/haproxy/conf/backend_http.conf
  * /etc/haproxy/conf/frontend_http.conf

2. Controller requires "gem install daemons"

  Controller use:
  scl enable ruby193 "ruby haproxy_controller.rb start"

3. Inside /etc/openshift/broker.conf on broker node set:

 ALLOW_HA_APPLICATIONS="true"

 Also allow user to create HA applications

 oo-admin-ctl-user -l $user --allowha true
