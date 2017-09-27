# softMipi4sla

The main perpose of this repository is to research on software implementation of mipi
interface with low cost phy, and make it work.

In the process of creation I will put hera links to blogs, documentation, PCBs and software sources

Ok, so what is SLA 3D printer. It prints 3D model by passing UV light throuth LCD screen to bath with UV resin.
Printer has actuator that moves printed part up the remain of uncured resin passes under part, then next layer is cured, and so on.

This technology is very cheap and makes possible to achive high quality of your prints.

For today (september 2017) cost of such printers is 300-400 USD FOB china. (Wanhao duplicator 7)
Delivery cost with all taxes cost me about 120USD
To use this printer you need separate PC. Most optimal solution for this is to use raspberry PI (costs about 50USD).

So, lets go deeper and figure out what is inside this printer.
<todo Insert link to ictures>

It have:
1. Metal base and enclosure.
2. Actuator (Stepper motor, coupling, leadscrew)
3. UV Lamp with fan on the bottom
4. Mirrors around UV lamp
5. 2K LCD Display
6. Bath with FEP film
7. Electronics that controls oll of this.

Electronics consist of:
1. Arduino board to control motor, FAN and UV Lamp
2. HDMI to MIPI converter
3. Connector adapter for specific LCD

Ok. I've made some researches on aliexpress and figured out that all of this parts is easyly accessible and cost not so much to build this printer localy.

But I was very surprised when saw that 2K LCD without HDMI converter costs just 45 USD. And together their cost is about 120USD.
So what's wrong with this converter and why it is so expensive?

I do not have an answer yet. But I found 2 chips that convert signals and their cost not greater than 7USD.

Ok. So I had an idea. Why not make an PCB that will control all of peripheral, include LCD. And connect it to wifi network through ESP8266 module. So we can get rid of both expensive raspberry pi and hdmi2mipi boards. 

Some weeks of research show me that MIPI DSI, that commonly used by all modern LCDs is not so complex, but it have physical layer, that non of the low cost MCUs supports. 

Ok but we can adapt 3.3v MCU gpio to MIPI interface logic with external components.


