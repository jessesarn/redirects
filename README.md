# Web Property redirects

Maintains the redirects for various decommissioned web properties or naked domains

  - openshift.com
  - openshift.org
  - developers.openshift.com
  - developer.openshift.com
  - forums.openshift.com
  - enterprise.openshift.com
  - install.openshift.com
  - origin.openshift.com
  - hub.openshift.com
  - marketplace.openshift.com
  - ideas.openshift.com
  - openshift.redhat.com
  - www.rhcloud.com
  - okd.io
  - www.openshift.org
  - docs.openshift.org
  - projectquay.io
  - osdworkshop.io
  - try.openshift.com
  - blog.openshift.com
  - account.openshift.com

Adding a new Host name requires creating a matching route.

# Testing new redirects

Testing can be done from `curl` without requiring an update to DNS for new sites

    curl http://elb.apps.openshift-web.p0s5.p1.openshiftapps.com/ -sSL -D - -H 'Host: install.openshift.com' -o /dev/null


# Initial Deployment

```bash
oc new-app openshift-template.yaml
```
