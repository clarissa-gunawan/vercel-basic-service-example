

## Setup the project

From outside your folder
```
npx create-next-app@latest <application-name> --app -ts --tailwind
```

Convert npm --> pnpm for ultra-dast and space-efficient packaging. Uses a shared store and symlinks. Ideal for monorepos and CI/CD

Install if not available globally - usefull to run `pnpm dev` from the terminal
```
npm install -g pnpm
```


```
rm -rf node_modules package-lock.json yarn.lock pnpm-lock.yaml bun.lockb
pnpm install
```

Run using pnpm and open to [http://localhost:3000](http://localhost:3000)
```
pnpm dev
```