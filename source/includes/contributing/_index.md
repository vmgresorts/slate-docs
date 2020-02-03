# Contributing

To make changes to the API, all you have to do is publish them to the relevant Github branches. Everything from there will be handled automatically - mostly. There are a few exceptions:

1. Kubernetes configurations are not automatically processed.
2. Database updates must be manually applied. For example, adding a new entity to Doctrine. It will do most of the work for you, but not all of it.
3. Changes to any environment variables must be done manually through kubernetes. Alternatives to make this easier are being explored.

Outside of those niche scenarios, all of your commits to CI/CD enabled branches will be promptly and automatically handled by our [pipelines](https://app.buddy.works/vmgportal/portal-react-2/pipelines). This comes with an important responsibility - everything you commit to those branches **must** be production ready, or things will explode!

These are the branches currently connected to a CI/CD pipeline:

1. `production` - pushes to `https://api.wtfportal.com`
2. `master` - pushes to `https://api.vmgportal.com`
3. `vmg-archive` - pushes to `https://archive.wtfportal.com`
