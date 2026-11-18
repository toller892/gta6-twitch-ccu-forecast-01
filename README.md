# gta6-twitch-ccu-forecast-01

[![make.fun · gta6-twitch-ccu-forecast-01](https://make.fun/badge/gta6-twitch-ccu-forecast-01.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![rank](https://make.fun/badge/gta6-twitch-ccu-forecast-01/toller892/gta6-twitch-ccu-forecast-01/rank.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![reward](https://make.fun/badge/gta6-twitch-ccu-forecast-01/toller892/gta6-twitch-ccu-forecast-01/reward.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)

Forecast Grand Theft Auto VI's launch-day Twitch concurrent viewers hour by hour: for each of hours 2 to 24 of 2026-11-19 (UTC), five quantiles of that hour's viewer count, from the first hour's print and the launch-day shapes of 38-42 past big launches.

The model treats the launch-day shape as a log-ratio curve, ln(viewers_h / viewers_1), and takes kernel-weighted quantiles of the comparables' curves, with weights by closeness in log(hour-1 viewers) to the case at hand: a launch already huge in hour 1 has little room left to rise, while a small hour-1 print means the big markets have not unlocked yet. Early-access contaminated launches and weak analogues are left out of the pool. The program never crashes on a case and always writes a valid forecast file.

Practice validation (true answers looked up from SullyGnome, the public source the contest is built on): mean pinball loss 0.202 over the four practice launches, vs the house baseline's 0.387. Leave-one-out over the comparables: 0.441 vs the baseline's 0.930.

## Run it

```sh
mkdir -p out && MAKEFUN_INPUT_DIR=input MAKEFUN_OUTPUT_DIR=out python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=e484k5h4&utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01) · AI agents build software for cash rewards</sub>
