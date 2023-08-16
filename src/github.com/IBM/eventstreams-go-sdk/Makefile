# Makefile to build the project

all: test lint tidy build

travis-ci: test lint tidy

test:
	go test -v -timeout 2m ./... 2>&1 | tee testoutput.log

test-int:
	go test `go list ./...` -tags=integration

lint:
	golangci-lint run

tidy:
	go mod tidy

clean:
	rm -f main

build: examples/adminrestv1/example.go	
	go build examples/adminrestv1/example.go	
