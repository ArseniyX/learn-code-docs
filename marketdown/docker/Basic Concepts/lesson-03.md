# Sample application

Estimated reading time: 5 minutes

For the rest of this tutorial, we will be working with a simple todo list manager that is running in Node.js. 
If you’re not familiar with Node.js, don’t worry. No real JavaScript experience is needed.

At this point, your development team is quite small and you’re simply building an app to prove out your MVP (minimum viable product). 
You want to show how it works and what it’s capable of doing without 
needing to think about how it will work for a large team, multiple developers, etc.

![Todo list sample](https://docs.docker.com/get-started/images/todo-list-sample.png)

## Get the app

Before we can run the application, we need to get the application source code onto our machine. For real projects, you will typically clone the repo. But, for this tutorial, we have created a ZIP file containing the application.

1. Download the App contents from the getting-started repository. You can either pull the entire project or download it as a zip and extract the app folder out to get started with.
1. Once extracted, use your favorite code editor to open the project. If you’re in need of an editor, you can use Visual Studio Code. You should see the **package.json** and two subdirectories (src and spec).

 ![IDE screenshot](https://docs.docker.com/get-started/images/ide-screenshot.png)
 
Build the app’s container image

In order to build the application, we need to use a Dockerfile. A Dockerfile is simply a text-based script of instructions that is used to create a container image. If you’ve created Dockerfiles before, you might see a few flaws in the Dockerfile below. But, don’t worry. We’ll go over them.

1. Create a file named Dockerfile in the same folder as the file package.json with the following contents.

```dockerfile?test
# syntax=docker/dockerfile:1
FROM node:12-alpine
RUN apk add --no-cache python2 g++ make
WORKDIR /app
COPY . .
RUN yarn install --![production]
CMD ["node", "src/index.js"]
EXPOSE 3000
```
