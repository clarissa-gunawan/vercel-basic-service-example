

## Setup the project

### Bootstrap next.js application
From outside your folder bootstrap next.js application. It includes using App Router, Tailwind CSS and Typescript
```
npx create-next-app@latest <application-name> --app -ts --tailwind
```

### Convert npm --> pnpm 
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
Ensure commits follow conventional commits:  recommends build:, chore:, ci:, docs:, style:, refactor:, perf:, test:
https://www.conventionalcommits.org/en/v1.0.0/#summary
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
