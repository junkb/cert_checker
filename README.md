depends on:
- bash
- openssl
- python
- acme-tiny [https://github.com/junkb/acme-tiny]

small set of utilities to check certificate expiration and, if necesary, request a new certificate

expects certain conventions as set forth in the comments

1. create a service/system account:

```bash
export service_username='certfetcher'
useradd --system --user-group --shell /bin/bash --create-home --home "/var/lib/${service_username}" --comment 'pki certificate fetcher' "${service_username}"
unset service_username
```

2. make the necessary sudo adjustments to allow the service acount to reload/restart the appropriate services

follow the process/steps outlined in initial_setup/initial_setup-root for environment prep as root

follow the process/steps outlined in initial_setup/initial_setup-service_user for environment prep as the service user

for creation/request of the initial certificate, use gen_csr and req_cert


for sample web server config, see initial_setup/example_config-httpd.

for sample crontab entry, see initial_setup/sample_crontab.  this should be placed in the service user's crontab.  not root.
