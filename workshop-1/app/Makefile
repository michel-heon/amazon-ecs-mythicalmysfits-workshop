
ECR_REPOSITORY_URI = 854597669776.dkr.ecr.us-east-2.amazonaws.com/mysfits-fargate-mono-emgrsnif7dfh
ECR_REPOSITORY_URI_LIKE = 854597669776.dkr.ecr.us-east-2.amazonaws.com/mysfits-fargate-like-qizwylydbcjl


docker-run:
	cd monolith-service ;\
	docker run -d -p 8000:80 -e AWS_DEFAULT_REGION=us-east-2 -e DDB_TABLE_NAME=Table-mysfits-fargate monolith-service

mono-push-ecr:
	cd monolith-service ;\
	docker tag monolith-service:latest 854597669776.dkr.ecr.us-east-2.amazonaws.com/mysfits-fargate-mono-emgrsnif7dfh:latest
	docker push 854597669776.dkr.ecr.us-east-2.amazonaws.com/mysfits-fargate-mono-emgrsnif7dfh:latest
	
nolike-build:
	cd monolith-service ;\
	docker build -t monolith-service:nolike . ;\
	docker tag monolith-service:nolike $(ECR_REPOSITORY_URI):nolike ;\
	docker push $(ECR_REPOSITORY_URI):nolike
	
nolike2-build:
	cd monolith-service ;\
	docker build -t monolith-service:nolike2 . ;\
	docker tag monolith-service:nolike2 $(ECR_REPOSITORY_URI):nolike2 ;\
	docker push $(ECR_REPOSITORY_URI):nolike2	

like-build:	
	cd like-service ;\
	docker build -t like-service . ;\
	docker tag like-service:latest $(ECR_REPOSITORY_URI_LIKE):latest ;\
	docker push $(ECR_REPOSITORY_URI_LIKE):latest ;\
	
test-var:
	echo $(ECR_REPOSITORY_URI)