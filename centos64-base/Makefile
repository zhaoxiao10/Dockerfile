IMG=kzdev/centos64-base

build:
	docker build -t $(IMG) .

rebuild:
	docker build --no-cache -t $(IMG) .

delete:
	docker rmi $(IMG)

push:
	docker push $(IMG)
