# Vault

```
$ export VAULT_TOKEN="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
```

Create policy.
```
$ vault policy-write my-policy -<<EOF
path "secret/*" {                                                       
  capabilities = ["create", "read", "update", "delete", "list"]                
}       
EOF
```

List policy.
```
$ vault policies
my-policy
default
secret
root
```

Create token.
```
$ vault token-create -policy=my-policy
Key             Value
---             -----
token           227c6035-295a-78d6-2d33-ab2ea3039bfb
token_accessor  439e4dd9-4616-5286-48f2-35238ac1014a
token_duration  768h0m0s
token_renewable true
token_policies  [my-policy default]

```
