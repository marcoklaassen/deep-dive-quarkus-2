# Deep Dive Quarkus 2

## Related Repositories

**Use the branch `quarkus-deep-dive-2` in the following repos.**

* [Feedback Basic Infrastructure](https://github.com/marcoklaassen/deep-dive-serverless/tree/quarkus-deep-dive-2)
* [Feedback Form](https://github.com/marcoklaassen/deep-dive-serverless-feedback-form/tree/quarkus-deep-dive-2)
* [Feedback Persistence](https://github.com/marcoklaassen/deep-dive-serverless-feedback-persistence/tree/quarkus-deep-dive-2)

## SSO Installation

Apply `sso-*.yaml` resources:

* operator
* instance
* realm
* client
* user

### Login to Red Hat sso

Get the route

```
oc get route keycloak -n deep-dive-quarkus --template=https://{{.spec.host}}
```

Get the admin password

```
oc get secret -n deep-dive-quarkus credential-deep-dive-quarkus -o json | jq -r '.data."ADMIN_PASSWORD"' | base64 -d
```
