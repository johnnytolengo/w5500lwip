# w5500lwip

Compatible with Ethernet Wiznet 5500 ESP32 (not tested with ESP8266)
Static or DHCP Modes available.
It is a very raw script but it works, also the dns server.

What it needs to run:

1) Setup the wifi module "on" or at least "WiFi.mode(WIFI_OFF)" to bring up the lwip interface and the "WiFiClient"

2) Arduino's setup() example:

  static ip: 
  uint8_t mac_addr[6] = { 0xDE, 0xAD, 0xBE, 0xEF, 0xFE, 0xE };
  IPAddress ip(192, 168, 1, 50);
  IPAddress subnet(255, 255, 255, 0);
  IPAddress gateway(192, 168, 1, 1);
  IPAddress dns(192, 168, 1, 1);  
  Ethernet.begin(mac_addr,ip,subnet,gateway, dns);
  
  dhcp ip:
  Ethernet.begin(mac_addr);

3) to use some client just use:
  WiFiClient wifiClient;
  

That's it!

!!! Note: the are a lot of work to do eg. handling link states, reconnections, transitions, Eth configuration things and so on... !!!
