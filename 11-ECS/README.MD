# ECS[Elastic Container Service]
* Fundamental problems with Docker
1. Auto Scaling
2. Auto Healing

# Auto Scaling
* When someone with or without intensionlly delete the dockert container does not capable of auto healing
* Without auto healing if it goes down when someone what to access the application they face downtime 

# Auto Scaling
* Without auto scaling we cannot run our applicaton
* Example....For our application the API requests are 100 it can manage but at the time of festival's if we get 10,000 API'S requests it cannot handle
* Kuberneties will solves the problems of Auto healing and auto scaling 
* With k8s we can take our containers to production level
* ECS doess not have all the features or capabilities like k8s has
