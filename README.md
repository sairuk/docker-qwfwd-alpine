setup qwfwd on alpine in docker, still testing for now

# compile
needs a custom fork atm, the main branch doesn't support musl libc build run the container
mount a volume for the output

### Run
copy in the compiled binary and cfg to _server_ dir then build the runtime docker image

See the following for info on config
- https://www.quakeworld.nu/wiki/QWfwd
- http://www.quakeworld.nu/blog/377/how-to-use-qwfwd-to-improve
