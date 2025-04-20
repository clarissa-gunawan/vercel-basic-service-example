

## Setup the project

### Bootstrap next.js application
From outside your folder bootstrap next.js application. It includes using App Router, Typescript, Tailwind CSS, ES Lint, Turbopack, pnpm. The application is initialize inside a src directory. 
```
npx create-next-app@latest <application-name> --app --ts --tailwind --eslint --turbopack --use-pnpm --src-dir 
```

### Convert npm --> [pnpm](https://pnpm.io/) 
For ultra-dast and space-efficient packaging. Uses a shared store and symlinks. Ideal for monorepos and CI/CD

Install if not available globally - usefull to run `pnpm dev` from the terminal
```
npm install -g pnpm
```

### Clean other package managers and install dependencies
```
rm -rf node_modules package-lock.json yarn.lock pnpm-lock.yaml bun.lockb
pnpm install
```

### Run using pnpm and open to [http://localhost:3000](http://localhost:3000)
```
pnpm dev
```

## Automate releasing and changelog

### Setup as a dev dependency
```
pnpm add -D release-please
```

### Good Commits
Ensure commits follow [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/#summary):  recommends build:, chore:, ci:, docs:, style:, refactor:, perf:, test:

```
feat: add email alert on contact form
fix: layout issue on mobile
chore: update dependencies
```


### Initial Tag
```
git tag v1.0.0
git push origin v1.0.0
```


### Workflow
1. Push regular commits to main
2. release-please opens a release PR with:
    * Updated CHANGELOG.md
    * Updated package.json version
3. You review and merge the PR
4. GitHub release is created automatically 🎉
5. Vercel can deploy that version instantly via main deployment


## Linting

Install [CommitLint](https://github.com/conventional-changelog/commitlint)
```
pnpm add -D commitlint @commitlint/config-conventional husky
```

Within `commitlint.config.js`

``` 
module.exports = { extends: ['@commitlint/config-conventional'] };\
```

Install [Husky](https://typicode.github.io/husky/)
```
pnpm exec husky init
echo "pnpm commitlint --edit \$1" > .husky/commit-msg
```