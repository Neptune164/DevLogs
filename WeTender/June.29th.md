### WeTender
#### Developing
- 1.Constructed the architeture and tech-stack.
- 2.Created GitHub repository and initialize local git branch.
- 3.Connected to the database (MongoDB Atlas) successfully.
- 4.Developed the entity and repository for the user document.

#### Troubleshooting
- 1. Can't share the context of the Appilication file when testing.
- **ans:** Copy the `application.yaml` to the dir `test/java/resourse`. Create it if doesn't exist.
- 2. Exception on the params of `@Document`
- **ans:** Double-check the param and use `collection`.
- **p.s. @Document has three params:**
- `collection`: related to the collection in the database.
- `collation`: related to the order rule.
- `locale`: similar with `collation`