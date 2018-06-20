# Shakra

Shakra is a pet project I am using to gather my thoughts around microservice architectures, keep track of some best practices I like to use and learn about the graphql eco system. I have loads of ideas from devops to design and I want to start fleshing them out here. I would also like to get a react app running for web and mobile, but 1 thing at a time. I want a solid foundation and I can add on from there. This is more of a learning exercise so doing things right is more important than getting things out :)

Note I know it's bad to over engineer things and I am not encouraging that. If you are building an app for 5 users this is problem the worst architecture you could adopt ;)

## Architecture

Shakra will be made up of services that have as little coupling as possible/makes sense. Most services will have a backing database that is exposed via a prisma container (for now I just point to a single mysql instance). Prisma is a new type of ORM that sits on top of your database, exposing queries and mutations through a graphql api. A second api will handle any functionality required by the service. It will also dictate what functionality is available from the service.

Right now there are 2 available services
- User service
- Goal Service

The API repo is a gateway api that stitches all the services together and exposes them as 1 api. 

Inter service communication happens with prisma bindings.

There are READMEs in all of the sub-modules, but they may have mistakes. Focus on setting up each service (prisma first within those), then the API wrapper. There are probably some mistakes in the docs, I am updating them over time.

## Future

I do want to build a fully fledged performance system in the end and I want it to be something that I can deploy to production and it would scale etc. For now this isn't really catered for - environments, deployment pipeline, tests - but I really do want to get to all that. For now I am just in proof of concept and it is going well!

## Contributions

Contributions are always welcome as long as they make sense. If you have something that you feel I will learn from - new libraries, patterns, naming, etc - please let me know!!!