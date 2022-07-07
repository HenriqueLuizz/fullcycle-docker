# Build container

docker build -t henriqueluizz/codeeducation .

## Check Image size

docker images | grep henriqueluizz/codeeducation

## Run

docker run --rm henriqueluizz/codeeducation
