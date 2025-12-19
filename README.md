# CSnake On ESP32-S3 TFT

Requierments:
 - https://docs.zephyrproject.org/latest/develop/getting_started/index.html
 - https://learn.adafruit.com/adafruit-esp32-s3-tft-feather/overview

Clone repo inside zephyrproject:
```
cd /path/to/zephyrproject &&
git clone git@github.com:Dexter9532/CSnake.git
```

Build image:
```
west build -p always \
  -b adafruit_feather_esp32s3_tft_reverse/esp32s3/procpu \
  -d CSnake/build \
  CSnake/
```

Flash image:
```
cd CSnake/build && west flash
```

## Debug:

To view output run:
```
west espressif monitor
```

## Clang

The project uses clang-format & clang-tidy.

Install dependencies:
```
sudo apt-get update
sudo apt-get install -y clang-tidy
sudo apt-get install -y clang-format
```

Run format check:
```
clang-format --dry-run -Werror src/*
```

Run formatter:
```
clang-format -i src/*
```

Run clang-tidy:
```
clang-tidy src/*.c -- -Iinclude
```
