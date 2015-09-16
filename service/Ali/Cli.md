# Setup

```
sudo pip install aliyuncli
```

next step is not necessary from my experience (already satisfied)

```
sudo pip install aliyun-python-sdk-ecs
```

```
aliyuncli ecs --help
```

```
aliyuncli configure
```

region=cn-beijing 

output=json

to change, simply run the command above again or edit files: ~/. aliyuncli /credentials and ~/. aliyuncli /config

then, we can do some test:

```
aliyuncli ecs DescribeRegions --output table
```

# Security Groups

To output help info

```
aliyuncli ecs CreateSecurityGroup help
```

<b> TO NOTE: RegionId can be omitted in following commands<b/>

## Create a Security Group

```
aliyuncli ecs CreateSecurityGroup --RegionId cn-beijing --SecurityGroupName search_sg --Description sg_for_search_machines
```

by right this should return SecurityGroupId, which we have to record and use later

## Authorize Security Group

```
aliyuncli ecs AuthorizeSecurityGroup --SecurityGroupId mySecurityGroupId --SourceCidrIp 0.0.0.0/0 --IpProtocol tcp --PortRange 9200/9300
```

## Describe Security Group Attribute

```
aliyuncli ecs DescribeSecurityGroupAttribute --SecurityGroupId mySecurityGroupId --RegionId cn-beijing
```

## Describe Security Groups

```
aliyuncli ecs DescribeSecurityGroups --RegionId cn-beijing
```

## Revoke Security Group (Unnecessary)

```
aliyuncli ecs RevokeSecurityGroup --SecurityGroupId mySecurityGroupId --SourceCidrIp 0.0.0.0/0 --IpProtocol tcp --PortRange 9200/9300
```

## Delete Security Group (Unnecessary)
 - 只有组内不存在实例，或者没有被其他组的安全规则引用时才可以删除。

```
aliyuncli ecs DeleteSecurityGroup --SecurityGroupId mySecurityGroupId --RegionId cn-beijing
```

## Join Security Group
 - 只有在实例状态为 Stopped 或 Running 状态下才可以执行该操作。
 - 每个实例最多属于 5 个安全组
 - 每个安全组最多拥有个 1000 个实例
 
```
aliyuncli ecs JoinSecurityGroup --InstanceId myInstanceId --SecurityGroupId mySecurityGroupId
```

## Leave Security Group (Unnecessary)

```
aliyuncli ecs LeaveSecurityGroup --InstanceId myInstanceId --SecurityGroupId mySecurityGroupId
```

## Describe Instance Status

```
aliyuncli ecs DescribeInstanceStatus --RegionId cn-beijing
```

## Describe Instances
```
aliyuncli ecs DescribeInstances
```

```
aliyuncli ecs DescribeInstances --InstanceIds ["i-25faivxbm"] //cannot make this para work
```

# References

 - https://docs.aliyun.com/?spm=5176.1970908.105.2.5Uu0Pe#/pub/aliyun-command-line-interface/quickStart/install-aliyun-command-line-interface
 - https://docs.aliyun.com/?spm=5176.1970908.105.2.5Uu0Pe#/pub/aliyun-command-line-interface/quickStart/configure-aliyun-command-line-interface
 - https://docs.aliyun.com/?spm=5176.1971658.105.2.86MaeY#/pub/ecs/open-api/instance&describeinstances
 - http://help.aliyun.com/knowledge_detail/5974779.html?spm=5176.7189909.0.0.JT52NO