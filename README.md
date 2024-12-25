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
scp -r .next/standalone/. lorange:~/nextjs-hello-world/
```

Run:

```sh
ssh lorange
cd ~/nextjs-hello-world
node server.js
```


## Benchmarking

```sh
sudo apt install wrk
wrk -t10 -c1000 -d180s http://192.168.20.25:3000/
```

Results:

```
> wrk -t10 -c1000 -d180s http://192.168.20.25:3000/

```

### Before (after reboot)

RAM usage: 237M
CPU Load average (over 1 minute): 0.06

### Server running

RAM usage:
CPU Load average (over 1 minute):

### Stress test

```sh
wrk -t10 -c1000 -d600s http://192.168.20.25:3000/
```

RAM usage:
CPU Load average (over 5 minutes):
