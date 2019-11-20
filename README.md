# ESP8266_WifiConnect_Blynk_Schedule

ESP8266 - Auto select Wifi connect - Blynk standalone - Schedule [Vietnamese language]

### Phần cứng gồm
  - Trên module đã được thiết kế sẵn
    * Push button
    * LDR
      - ADC
    * RGB LED
      - GPIO12 - LED Green 
      - GPIO13 - LED Blue
      - GPIO15 - LED Red
    * DTH22 - cảm biến môi trường được kết nối thêm.
      - GPIO05
      
![ESP8266 Module](https://github.com/PhamDuyAnh/ESP8266_WifiConnect_BlynkStandalone/blob/master/Esp8266-module.jpg)

### Thư viện
  - Dùng các thư viện
    * ESP8266WiFi.h - http://arduino.esp8266.com/stable/package_esp8266com_index.json
    * BlynkSimpleEsp8266.h - https://github.com/blynkkk/blynk-library
    * DHT.h - https://github.com/adafruit/DHT-sensor-library.git

### Hoạt động
  - Tự động lựa chọn các Wifi SSID đã được lưu và kết nối với SSID có tín hiệu mạnh nhất mà ESP8266 tìm được.
  - Kết nối với Blynk Cloud Local server (hoặc Blynk server).
  - Gởi các dữ liệu lên biến Virtuals:
    * V0 - cường độ tín hiệu Wifi
    * V1 - LDR (Light Dependent Resistor)
    * V7 - độ ẩm (humidity) từ cảm biến DTH22
    * V8 - nhiệt độ (temperature) từ cảm biến DTH22
  - Nhận các dữ liệu
    * V3 - giá trị từ 0-1023, điều khiển LED Green
    * V4 - giá trị từ 0-1023, điều khiển LED Blue
    * V5 - giá trị từ 0-1023, điều khiển LED Red
  - Lưu ý
    * ```Blynk.begin``` -> kết nối wifi và liên kết đến blynk cloud
      - ```Blynk.begin(auth, ssid, pass, "myblynk.homeip.net", 8442)``` -> liên kết đến một server khác blynk-cloud.com
      - ```Blynk.begin(auth, ssid, pass, IPAddress(192,168,1,100), 8442)``` -> liên kết đến một IP
    * ```BLYNK_READ(virtualPin)``` ->function will be called every time App Widget requests data for Virtual Pin
    * ```BLYNK_WRITE(virtualPin)``` -> function will be called every time App Widget writes value to Virtual Pin
    * ```ledWifiConnectStatus()``` -> nháy LED khi kết nối wifi
    * ```ledConnectStatus()``` -> nháy LED khi liên kết được blynk cloud
    * ```wifiConnect()``` -> quét các Wifi SSID, lựa chọn các SSID đã được lưu và kết nối với SSID có tín hiệu mạnh nhất mà ESP8266 tìm được.

![Screenshot](https://github.com/PhamDuyAnh/ESP8266_WifiConnect_BlynkStandalone/blob/master/Screenshot_2017-08-30-09-44-22.png)

### Source 
Có thể download tại <https://github.com/PhamDuyAnh/ESP8266_WifiConnect_BlynkStandalone>.

### License
Được chia sẻ theo thỏa ước GNU GPL v3.0

### Tác giả
  Phạm Duy Anh (CKD)
  http://cncprovn.com
