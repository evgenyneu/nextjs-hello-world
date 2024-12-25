
# Next.js Hello World

This is a simple Next.js app that returns "Hello, World!" message, made for benchmarking Next.js resource usage.

## Build

```sh
npm install
npm run build
```

Run:

```sh
node .next/standalone/server.js
```


## Deploy

```sh
ssh lorange "mkdir -p ~/nextjs-hello-world"
scp -r .next/standalone/* lorange:~/nextjs-hello-world/
```

Run:

```sh
ssh lorange
cd ~/nextjs-hello-world
node server.js
```
