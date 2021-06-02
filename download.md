## Download

```
git clone https://github.com/fdch/thornblower
cd thornblower
pd main.pd
```

## Dependencies

You need the following Pure Data libraries available via `deken` (`Help>Find Externals`):
- hidio: for the `[hidio]` object to get the PS4 controller data. This can be searched with `deken` or in Benitoite's [github repo](https://github.com/Benitoite/hidio). Alternatively, you can install danomatika's [joyosc](https://github.com/danomatika/joyosc) and reassign some receives... 
- `fd_lib`: availble via `deken`, or [here](https://github.com/fdch/fd_lib)

optional: 
- else: for `[else/pan4~]` object (only used in 4-channel mode)

---

See [README.md](README.md) and [usage.md](usage.md) for instructions.