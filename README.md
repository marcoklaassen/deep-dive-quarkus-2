# Deep Dive Quarkus 2

## Related Repositories

**Use the branch `kafka-deep-dive` in the following repos.**

* [Feedback Basic Infrastructure](https://github.com/marcoklaassen/deep-dive-serverless/tree/kafka-deep-dive)
* [Feedback Form](https://github.com/marcoklaassen/deep-dive-serverless-feedback-form/tree/kafka-deep-dive)
* [Feedback Persistence](https://github.com/marcoklaassen/deep-dive-serverless-feedback-persistence/tree/kafka-deep-dive)

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
oc get route keycloak -n deep-dive-kafka --template=https://{{.spec.host}}
```

Get the admin password

```
oc get secret -n deep-dive-kafka credential-deep-dive-kafka -o json | jq -r '.data."ADMIN_PASSWORD"' | base64 -d
```
