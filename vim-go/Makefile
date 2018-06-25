IMAGE=vim-go
TAG=latest
NAME=$(IMAGE)

.PHONY: build

build:
	docker build -f Dockerfile -t $(IMAGE):$(TAG) .

commit:
	docker commit $(shell docker ps --quiet --filter name=$(NAME)) $(IMAGE):$(TAG)

run:
	docker run --name $(NAME) --rm -it $(IMAGE):$(TAG) /bin/sh
