# Tuya Light Switch Conversion
Converting Tuya light switches to local

I bought these [Moeshouse smart light switches](https://www.moeshouse.com/collections/smart-switch/products/wifi-smart-light-switch-push-button-neutral-wire-required-1-2-3-gang) for my whole house, around 17 switches. I've tried them for about 8 months with their local integration for Home Assistant. It worked fine, but had a few issues.
- Wifi constantly disconected and didn't reconnect. This made them basically useless.
- They say "local" but they require a local key that changes and the you need to reconfigure them in Home Assistant. The solution to this is to block their internet access.

So I opened them up and took a look inside. The company that manifactures them is Tuya and in the past you could flash Tasmota or ESPHome on their chips, but my luck ran out as the ones I got had the `WB3S` module in it. I found a video on Youtube of a guy replacing the module with a `ESP12E` module and it got me thinking of doing the same. One problem with these smart light switches is they don't have a secondary chip that controlled things on the switch like the dimmers the guy in the video used. So the Tasmota MCU and ESPHome MCU won't work. After days of searching I came across someone who wanted to do the same as I, but he got lucky and had one of the older wifi modules based on the `ESP8266` which could be flashed. You can have a look at his post [here](https://www.hackster.io/michael_zanetti/smartlife-tuya-wifi-light-switch-with-tasmota-and-nymea-09a7a6)

I've decided to make this repo to help anyone with the same problem.

# Getting started
#### Identify the wifi module in your Tuya switch
Here I have a 2 gang switch, but this conversion works for the 1 gang, 2 gang and 3 gang smart switches linked above.
