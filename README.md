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


# Initial Deployment

```bash
oc process -f openshift-template.yaml -p CA_CERTIFICATE="$(cat certs/DigiCertCA.crt)" \
    -p DEVELOPERS_CERTIFICATE="$(cat certs/developers_openshift_com.crt)" -p DEVELOPERS_KEY="$(cat certs/developers_openshift_com.key)" \
    -p FORUMS_CERTIFICATE="$(cat certs/forums_openshift_com.crt)" -p FORUMS_KEY="$(cat certs/forums_openshift_com.key)" \
    -p ENTERPRISE_CERTIFICATE="$(cat certs/enterprise_openshift_com.crt)" -p ENTERPRISE_KEY="$(cat certs/enterprise_openshift_com.key)" \
    -p INSTALL_CERTIFICATE="$(cat certs/install_openshift_com.crt)" -p INSTALL_KEY="$(cat certs/install_openshift_com.key)" \
    -p ORIGIN_CERTIFICATE="$(cat certs/origin_openshift_com.crt)" -p ORIGIN_KEY="$(cat certs/origin_openshift_com.key)" \
    -p HUB_CERTIFICATE="$(cat certs/hub_openshift_com.crt)" -p HUB_KEY="$(cat certs/hub_openshift_com.key)" \
    -p MARKETPLACE_CERTIFICATE="$(cat certs/marketplace_openshift_com.crt)" -p MARKETPLACE_KEY="$(cat certs/marketplace_openshift_com.key)" \
    -p IDEAS_CERTIFICATE="$(cat certs/ideas_openshift_com.crt)" -p IDEAS_KEY="$(cat certs/ideas_openshift_com.key)" \
    -p REDHAT_CERTIFICATE="$(cat certs/openshift_redhat_com.crt)" -p REDHAT_KEY="$(cat certs/openshift_redhat_com.key)" \
    -p RHCLOUD_CERTIFICATE="$(cat certs/www_rhcloud_com.crt)" -p RHCLOUD_KEY="$(cat certs/www_rhcloud_com.key)" \
  | oc create -f -
```
