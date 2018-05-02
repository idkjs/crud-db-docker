Demo for a Basic Fullstack GraphQL App with [ReasonApollo](https://github.com/apollographql/reason-apollo) / [Prisma](https://prisma.io)

# Installing & Running

```s
cd server
yarn && yarn start
cd ..
yarn && yarn start
```

## Running two instances

To run to front ends against the server run `yarn start` in root run on your local machine, the run `docker run -p 8080:80 idkjs/crud-image` in another terminal.

Both instance will work against the running server, exactly the same way, in theory. There is some kind of latency on the docker image. The refetch query function seems to not be working quickly enough or its not waiting for a respose. Need to work that out.

## Note on graphql

Only seems to work on graphql@12.3. Otherwise anything above that is throwing a parse(doc) experimental graphql-tag error. Strangely, works on a webpack, no react-scripts version with 13.2.

Culprit is probably refetchqueries and inMemoryCache settings.
