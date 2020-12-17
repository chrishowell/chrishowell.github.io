Today I investigated how to use AWS Lambda's new Docker container packaging - using Java rather than Node. All documentation points to a Node package, I refused to give up, it must be simple.

## It was simple
Once you know how to do it, it's ridiculously easy; before that point.. :(
It's actually just a case of copying the compiled jar into the `./lib` directory in the default workdir.

## The three lines
```
FROM amazon/aws-lambda-java:11
COPY build/libs/*-all.jar ./lib/app.jar
CMD ["<function-handler-canonical-name>"]
```

