Create a cluster called ```fargate-testing```
```
aws ecs create-cluster --cluster-name fargate-testing
```
Tasks
AWS ECS defines a task definition as a list of containers grouped together. This task definition creates a task family called ```fargate-game``` running a single container called web-game that is based on the Quantum web game (https://github.com/stared/quantum-game).
```
aws ecs register-task-definition --cli-input-json file://...webgame-task.json
```
Modify the following command to reference a valid subnet ID and security group ID from your AWS VPC.
```
aws ecs create-service --cluster fargate-testing --service-name fargate-game-service --task-definition fargate-game:1 --desired-count 1 awsvpcConfiguration={subnets=[subne-abc123],securityGroups=[sg-abc123],assignPublicIp=ENABLED}
```
