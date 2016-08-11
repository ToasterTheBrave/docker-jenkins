# Overview
Jenkins image built with Docker installed.  This allows running docker commands from shell

# Usage
There are two volumes that are useful to attach to this image.

Mounting docker.sock allows using the Docker daemon on the host machine, which will bring up containers alongside the jenkins container, rather than running Docker in Docker.  Mounting jenkins_home allows config and items to persist after the container is killed.

# Example
```
docker run \
	--name jenkins \
	-p 8080:8080 \
	-d \
	--volume /var/run/docker.sock:/var/run/docker.sock \
	--volume /Users/tylerruppert/projects/docker-volumes/jenkins_home:/var/jenkins_home \
	ruppdog/jenkins
```

# License and Author
Author: Tyler Ruppert

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0
Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.