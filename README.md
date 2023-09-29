# JQ

## AWS Configs 

### ConfigRuleStatus=ACTIVE
```
aws configservice describe-config-rules --region us-west-1 --profile AWS-Volterra-prod-secops | jq '.ConfigRules[]|select(.ConfigRuleState=="ACTIVE")|.ConfigRuleName'
```

### ConfigRuleName starts with z_
```
aws configservice describe-config-rules --region us-west-1 --profile AWS-Volterra-prod-secops | jq '.ConfigRules[]|select(.ConfigRuleName|test("^z_."))|.ConfigRuleName'
```

### ConfigRuleStatus=ACTIVE and multiple columns
```
aws configservice describe-config-rules --region us-west-1 --profile AWS-Volterra-prod-secops | jq -r '.ConfigRules[]|select(.ConfigRuleState=="ACTIVE")|.ConfigRuleName+ " " +.ConfigRuleState'
```
