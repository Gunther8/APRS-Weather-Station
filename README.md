# APRS Weather Station | APRS 气象站

A Python-based APRS weather station that periodically fetches weather data from the OpenWeather API and transmits it to an APRS-IS server. Designed for ham radio enthusiasts, especially APRS users.

本项目是一个基于 Python 的 APRS 气象站，定期从 OpenWeather API 获取天气数据，并将其发送到 APRS-IS 服务器。适用于业余无线电爱好者，特别是 APRS 用户。

---

## Features | 功能特点

- Fetches real-time weather data (temperature, humidity, wind speed & direction) via OpenWeather API.
  通过 OpenWeather API 获取实时天气数据（温度、湿度、风速、风向）。
- Formats weather data in APRS protocol and uploads to an APRS-IS server.
  采用 APRS 协议格式化天气数据并上传到 APRS-IS 服务器。
- Connects to `rotate.aprs2.net:14580` via TCP/IP.
  采用 TCP/IP 连接 `rotate.aprs2.net:14580` 服务器进行数据上传。
- Transmits data at a 10-minute interval.
  采用 10 分钟间隔定期发送数据。

---

## Prerequisites | 先决条件

### Software | 软件要求

- Python 3.x

### Dependencies | 依赖库

```sh
pip install requests
```

---

## Configuration | 配置

Edit the following fields in `aprs_weather.py` to match your setup | 在 `aprs_weather.py` 中修改以下配置项：

```python
CALLSIGN = "BI3MCY-10"          # Your APRS callsign | 你的 APRS 呼号
PASSCODE = "******"             # Your APRS-IS passcode | 你的 APRS-IS passcode
SERVER   = "rotate.aprs2.net"   # APRS-IS server | APRS-IS 服务器
PORT     = 14580                # Server port | 服务器端口
LATITUDE  = *                   # Latitude | 纬度
LONGITUDE = *                   # Longitude | 经度
OPENWEATHER_API_KEY = "******"  # Your OpenWeather API key | 你的 OpenWeather API 密钥
```

---

## Usage | 运行方法

```sh
python aprs_weather.py
```

---

## Example Packet | 示例数据包

```
BI3MCY-10>APRS,TCPIP*:@181230z0256.90N/12210.08E_040/015g...t068h75b10132 Airports WX in Python | gang8848@gmail.com
```

---

## License

MIT
