# Web Property redirects

Maintains the redirects for various decommissioned web properties

  - developers.openshift.com
  - forums.openshift.com
  - enterprise.openshift.com
  - install.openshift.com
  - origin.openshift.com
  - hub.openshift.com
  - marketplace.openshift.com
  - ideas.openshift.com
  - openshift.redhat.com
  - www.rhcloud.com

Adding a new Host name requires creating a matching route.

# Testing new redirects

Testing can be done from `curl` without requiring an update to DNS for new sites

    curl http://elb.e203.evg.openshiftapps.com/ -sSL -D - -H 'Host: install.openshift.com' -o /dev/null
