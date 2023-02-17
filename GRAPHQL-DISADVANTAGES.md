## Disadvantages:

* You __need to learn__ how to set up GraphQL. The ecosystem is still rapidly evolving so you have to keep up.
* You need to send the queries from the client, you can just send strings but if you want more comfort and caching
*  you'll use a client library -> __extra code__ in your client
* You need to define the schema beforehand => __extra work__ before you get results
* You need to have a graphql endpoint on your server => __new libraries__ that you don't know yet
* Graphql queries are __more bytes__ than simply going to a REST endpoint
* The server needs to do __more processing__ to parse the query and verify the parameters

## But, those are more than countered by these:

* GraphQL is __not that hard to learn__
* The extra code is __only a few KB__
* By defining a schema, you will __prevent much more work afterwards__ fixing bugs and enduring hairy upgrades
* There are a lot of people switching to GraphQL so there is a __rich ecosystem__ developing, with excellent tooling
* When using persistent queries in production (replacing GraphQL queries with simply an ID and parameters), you actually send __less bytes__ than with REST
* The extra processing for incoming queries is negligible
* Providing a __clean decoupling of API and backend__ allows for much faster iteration on backend improvenments

---

> <https://stackoverflow.com/questions/40689858/are-there-any-disadvantages-to-graphql>
