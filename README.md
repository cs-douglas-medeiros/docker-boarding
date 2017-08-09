# Docker-Boarding

A Docker container for [Fastlane/Boarding](https://github.com/fastlane/boarding/)

DockerHub: https://hub.docker.com/r/emcniece/docker-boarding/

## Running

Pull the docker container, then run with your desired environment variables:

```sh
docker pull emcniece/docker-boarding

docker run -d \
  -e ITC_USER=myUser@domain.com \
  -e ITC_PASSWORD=passForMyUser \
  -e ITC_APP_ID=targetAppId \
  -e ITC_APP_TESTER_GROUPS="My Testers Group" \
  -e FASTLANE_ITC_TEAM_ID="0123" \
  -p 3000:3000 \
  emcniece/docker-boarding
```

## Building

If you have Make installed, the Makefile will help with building the container.

Ensure that `.env` is populated before building and running.

```sh
# Load environment variables for Makefile use
source .env

# Show commands
make

# Build image
make image

# Run container normally
make run

# Run container without starting app
make run-debug

# Upload to Dockerhub
make docker

# Tag with VERSION and upload
make release

# Remove running named container
make kill

# Remove image from your system
make clean
