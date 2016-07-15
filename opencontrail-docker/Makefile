contrail_repo_string="10.102.44.89/contrail-install-packages_3.0.1.0-23-juno"
PREFIX=sanjuabraham
TAG=3.0.1

all: build-config build-control build-ifmap-server build-analytics build-web build-vrouter-agent

build-%:
	$(eval SUBDIR := $(patsubst build-%,%,$@))
	docker build -t ${PREFIX}/${SUBDIR}:${TAG} --build-arg contrail_repo_string="$contrail_repo_string" ${SUBDIR}
