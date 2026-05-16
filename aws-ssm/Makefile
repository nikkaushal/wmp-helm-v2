def:
	git pull
	terraform init
	terraform apply -auto-approve

docker-build:
	git pull
	aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 293222827824.dkr.ecr.us-east-1.amazonaws.com
	docker build -t 293222827824.dkr.ecr.us-east-1.amazonaws.com/aws-ssm .
	docker push 293222827824.dkr.ecr.us-east-1.amazonaws.com/aws-ssm
	