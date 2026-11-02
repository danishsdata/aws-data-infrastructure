# aws-data-infrastructure

Parameterized CloudFormation templates for the three data clusters I
build most often: Aurora PostgreSQL, Redshift, and DocumentDB. Same
shape every time, so a new environment is a parameter change, not a
new design.

Portfolio implementation of patterns I use as an AWS DBA / data engineer.

## Run

Deploy one stack per template, for example:

```
aws cloudformation create-stack \
  --stack-name app-aurora \
  --template-body file://templates/aurora-postgres.yaml \
  --parameters file://parameters/example.json \
    ParameterKey=MasterPassword,ParameterValue=<PASSWORD>
```

Passwords are deliberately not in parameters/example.json. Pass them at
deploy time, or better, from Secrets Manager.
