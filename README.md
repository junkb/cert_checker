small set of utilities to check certificate expiration and, if necesary, request a new certificate

expects certain conventions as set forth in the comments

follow the process/steps outlined in initial_setup-root for environment prep as root

follow the process/steps outlined in initial_setup-service_user for environment prep as the service user

for creation/request of the initial certificate, use gen_csr and req_cert

for sample crontab entry, see sample_crontab.  this should be placed in the service user's crontab.  not root.
