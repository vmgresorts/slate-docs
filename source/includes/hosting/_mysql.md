## Database

The databases for this application are hosted using [Google Cloud SQL](https://cloud.google.com/sql/). You can find the connection info in the relevant environment files; you shouldn't have a problem connecting to the instances using it. As of Feb 3rd 2020, there are three databases:

- `portal_dev`
- `portal_prod`
- `portal_vmg_archive`

When running locally, to prevent headaches you should _always_ connect to `portal_dev`. You can point your instance towards `portal_prod`, but only do so if you have good reason and understand the consequences.

If you want to, you could host an instance of mysql locally and point the application to it. You'd have to first prepare the database by building all of the required tables and populate them, but it's doable and it would give you an isolated instance to work with. Though it's usually perfectly fine to just point your aplpication towards `portal_dev`.
