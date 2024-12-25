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

RAM usage: 271M
CPU Load average (over 1 minute): 0.02

### Stress test #1

With one node process: `node server.js`

```sh
wrk -t10 -c1000 -d600s http://192.168.20.25:3000/
```

RAM usage: 464M
CPU Load average (over 5 minutes): 0.99

Results:

```
  10 threads and 1000 connections
  Thread Stats   Avg      Stdev     Max   +/- Stdev
    Latency   637.91ms  199.62ms   1.93s    75.44%
    Req/Sec   158.71    102.28   580.00     66.03%
  726619 requests in 10.00m, 185.02MB read
  Socket errors: connect 0, read 256, write 0, timeout 889
Requests/sec:   1210.83
Transfer/sec:    315.71KB
```
