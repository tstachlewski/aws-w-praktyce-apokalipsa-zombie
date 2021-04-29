Pierwsze kroki z AWS CLI:

```
aws ec2 describe-instances

aws ec2 describe-instances --query "Reservations[*].Instances[*].InstanceId"

aws ec2 describe-instances --query "Reservations[*].Instances[*].InstanceId" --output table
```
Dokumentacja: https://docs.aws.amazon.com/cli/latest/reference/index.html#cli-aws


Weryfikacja "kim" jestesmy
```
aws sts get-caller-identity --query Arn
```
