# Knowledge base
This repository contains resources (links, articles, guides etc) for all knowledge acquired within 
the development's team day-to-day work.

## Running the app
To run the app: 
1. Go to `website` folder where `package.json` is located.
2. Run `npm start`.

## Publishing to Github pages
Publishing to Github pages uses `releases` branch `docs/` folder.
To publish a new release, `docs/` folder must be populated with the `build` command output.

1. Checkout branch `releases`:

`git checkout releases`

2. Merge `master` branch which should contain your most recent changes:

`git merge master`

3. Run `npm run build` from the `website` folder. 

4. Make sure `docs` folder is the **only folder containing changes** (`git status`).
5. Push changes to `release` branch.
6. Visit [Knowledge base site](https://codehub-create.github.io/knowledge-base/) and ensure it's updated.
