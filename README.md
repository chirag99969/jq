# JQ

## AWS Configs 

```
aws configservice describe-config-rules --region us-west-1 --profile AWS-Volterra-prod-secops | jq '.ConfigRules[]|select(.ConfigRuleState=="ACTIVE")|.ConfigRuleName'
```

```
aws configservice describe-config-rules --region us-west-1 --profile AWS-Volterra-prod-secops | jq '.ConfigRules[]|select(.ConfigRuleName|test("^z_."))|.ConfigRuleName'
```
