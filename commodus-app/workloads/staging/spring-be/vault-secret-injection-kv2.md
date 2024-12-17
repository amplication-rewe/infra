# Vault Key-Value Secret Injection

## Creating the secret in Vault

We have auto-generated the `vault-injector-config-spring-be.yaml` for you and added this to the `kustomization.yaml` file.
We have also extended the `deployment-changes.yaml` (or `cron-job-changes.yaml` if a cron-job template was choosen) so that it includes the necessary annotations on the `Deployment` to make the secret-injection work.

**There is one last thing left for you**: the `vault-injector-config-spring-be.yaml` was configured to inject the secret from
`"rd-platform-k8s-staging/riag/retail/team-ca/commodus-app/spring-be/spring-be-secrets"`. In order for the secret injection to work you need to head to the Vault UI `https://vault.staging.cloud.riag.digital/ui/` and create a secret on the above-mentioned path. Your secrets will be mounted in the filesystem of your container under the path `/vault/secrets/`.
