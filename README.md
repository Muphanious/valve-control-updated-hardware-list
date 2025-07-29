# valve-control

Use Arduino Uno to control solenoid valves.  
Follow the steps below to set up your own valve control station.

## Purchase

### Send [PCB design](https://github.com/GNHua/valve-control/raw/master/pcb_layout/plots.zip) Out For Manufacturing

* Highly recommend [JLCPCB](https://jlcpcb.com/). Fabrication and shipping took ~1 week for me in the U.S.
* If you choose JLCPCB, go [here](https://jlcpcb.com/quote), upload [plots.zip](pcb_layout/plots.zip), and leave everything else as default.
* If you have access to a PCB baking oven, buying a SMT-Stencil will save you a lot of time for soldering. If not, all the components can still be soldered by hand.

| Top Layer | Bottom Layer |
| --------- | ------------ |
| <img src="https://github.com/GNHua/valve-control/raw/master/pcb_layout/top.png" width="400"> | <img src="https://github.com/GNHua/valve-control/raw/master/pcb_layout/bottom.png" width="400"> |

### Electrical Components To Buy

| Part | Label on PCB | Qty. (per PCB) | Purchase |
| ---- | :----------- | :------------: | :------: |
| [Shift register, SN74HC595N](https://www.digikey.com/product-detail/en/texas-instruments/SN74HC595N/296-1600-5-ND/277246?utm_adgroup=Integrated%20Circuits&slid=&gclid=Cj0KCQjwzK_bBRDDARIsAFQF7zN5-LHxIfRLcNVY-gf6gJ_lS_RSs-WGzMVOjYGovQlShfyqFOsZDr0aAqcmEALw_wcB) | plug on the DIP socket (U1) | 1 | [link](https://www.digikey.com/product-detail/en/texas-instruments/SN74HC595N/296-1600-5-ND/277246?utm_adgroup=Integrated%20Circuits&slid=&gclid=Cj0KCQjwzK_bBRDDARIsAFQF7zN5-LHxIfRLcNVY-gf6gJ_lS_RSs-WGzMVOjYGovQlShfyqFOsZDr0aAqcmEALw_wcB)
| [Optoisolator, HCPL 2731](https://www.digikey.com/product-detail/en/on-semiconductor/HCPL2731/HCPL2731QT-ND/31642) | plug on the DIP sockets (U2-U5) | 4 | [link](https://www.digikey.com/product-detail/en/on-semiconductor/HCPL2731/HCPL2731QT-ND/31642) |
| [Resistor, 2.32 k&Omega;, package 0805](https://www.digikey.com/product-detail/en/stackpole-electronics-inc/RMCF0805FT2K32/RMCF0805FT2K32DKR-ND/1943295) | R1-R16 | 16 | [link](https://www.digikey.com/product-detail/en/stackpole-electronics-inc/RMCF0805FT2K32/RMCF0805FT2K32DKR-ND/1943295) |
| [Common anode diode](https://www.digikey.com/product-detail/en/diodes-incorporated/BAT54AT-7-F/BAT54AT-FDICT-ND/821941) | D1-D4 | 4 | [link](https://www.digikey.com/product-detail/en/diodes-incorporated/BAT54AT-7-F/BAT54AT-FDICT-ND/821941) |
| [PMOS](https://www.digikey.com/product-detail/en/toshiba-semiconductor-and-storage/SSM3J338RLF/SSM3J338RLFCT-ND/5810258) | Q1-Q8 | 8 | [link](https://www.digikey.com/product-detail/en/toshiba-semiconductor-and-storage/SSM3J338RLF/SSM3J338RLFCT-ND/5810258) |
| [1 uF capacitor, package 0805, voltage rating 10V](https://www.digikey.com/product-detail/en/yageo/CC0805KKX7R6BB105/311-1458-1-ND/2833764) | C1 | 1 | [link](https://www.digikey.com/product-detail/en/yageo/CC0805KKX7R6BB105/311-1458-1-ND/2833764) |
| [DIP socket, 2x8](https://www.digikey.com/product-detail/en/assmann-wsw-components/A-16-LC-TT/AE9992-ND/821746) | U1 | 1 | [link](https://www.digikey.com/product-detail/en/assmann-wsw-components/A-16-LC-TT/AE9992-ND/821746) |
| [DIP socket, 2x4](https://www.digikey.com/product-detail/en/assmann-wsw-components/A-08-LC-TT/AE9986-ND/821740) | U2-U5 | 4 | [link](https://www.digikey.com/product-detail/en/assmann-wsw-components/A-08-LC-TT/AE9986-ND/821740) |
| [Stacking headers](https://www.digikey.com/products/en?mpart=85&v=1528) | J2-J4, H1, H2 | 1 | [link](https://www.digikey.com/products/en?mpart=85&v=1528) |
| [Connector, Molex 50212-8000](https://www.digikey.com/product-detail/en/molex-llc/50212-8000/WM4561CT-ND/2524899) | N/A | 18 | [link](https://www.digikey.com/product-detail/en/molex-llc/50212-8000/WM4561CT-ND/2524899) |
| [Connector housing, Molex 0873690200](https://www.digikey.com/product-detail/en/molex-llc/0873690200/WM10118-ND/3264531) | N/A | 9 | [link](https://www.digikey.com/product-detail/en/molex-llc/0873690200/WM10118-ND/3264531) |
| [JST header, Molex 0894010210](https://www.digikey.com/products/en?keywords=0894010210) | J5-J13 | 9 | [link](https://www.digikey.com/products/en?keywords=0894010210) |
| [2.5 mm barrel jack, 5A max, CUI PJ-057BH ](https://www.digikey.com/product-detail/en/cui-inc/PJ-057BH/CP-057BH-ND/1644602?WT.srch=1&gclid=Cj0KCQjwzK_bBRDDARIsAFQF7zMAA_lLykibpOltGBij_q3GgaALm4U1mWajtnpzEGkrmGGN8nhqwBUaAmMTEALw_wcB) | J1 | 1 for each setup | [link](https://www.digikey.com/product-detail/en/cui-inc/PJ-057BH/CP-057BH-ND/1644602?WT.srch=1&gclid=Cj0KCQjwzK_bBRDDARIsAFQF7zMAA_lLykibpOltGBij_q3GgaALm4U1mWajtnpzEGkrmGGN8nhqwBUaAmMTEALw_wcB) |

### Solenoid Valves and Additional Hardware to Buy

* [Clippard, E310C-2C012, 10 mm N-C 3-way Valve, In-line Connector w/LED, 0.030" Orifice, 1.3W, 12 VDC](http://www.clippard.com/part/E310C-2C012)
* [Valve connector cable](http://www.clippard.com/products/electronic-valve-10mm-connector)
* [Manifold](http://www.clippard.com/products/electronic-valve-10mm-manifolds)

Details can be found on page 215-221 in [Clippard Full-line Catalog](http://www.clippard.com/downloads/PDF_Documents/Clippard%20Full%20Line%20Catalog/Clippard%20Full-Line%20Catalog.pdf)

| Part | Description | Qty. (total) | Purchase |
| :--: | :---------: | :----------: | :------: |
| Flangeless Fitting | Tan fitting that connects tubing to manifold | # of total stations that all of your manifolds have (ex. 4 manifolds x 6 stations each = 24 fittings) | [link](https://www.idex-hs.com/store/product-detail/flangeless_fitting_peek_10_32_flat_bottom_for_1_16_od/xlt-111) |
| Fitting Sleeve | Sleeve that goes over your tubing and connects into your flangeless fitting | Same # as the flangeless fittings | [link](https://www.idex-hs.com/store/product-detail/nanotight_sleeve_purple_1_16_od_x_042_id_x_1_6_/f-252) |
| 6mm Tubing | Tubing for the compressed air with connector kit included | 1 | [link](https://www.amazon.com/mxuteuk-Fittings-Meter-Polyurethane-Connect/dp/B0DG2G5Y92?gQT=1&th=1)|
| 6mm Connectors | Additional connectors if you need more | Optional, check included kit first | [link](https://www.amazon.com/Fittings-Pneumatic-Connector-Straight-Splitter/dp/B07PS4YTKG?source=ps-sl-shoppingads-lpcontext&ref_=fplfs&smid=A1MBAH9GZG1ZVG&gQT=1&th=1) |
| Barbed Hose Fitting | Barbed fittings that attach your tubing to the manifolds | 1 per manifold (if you need the vacuum function, 2 per manifold total) | [link](https://www.airlinehyd.com/product/CLIPPARD-11752-3-PKG/1299268?keyword=&utm_term=&utm_campaign=Performance_Max%20Shopping&utm_source=google&utm_medium=cpc&hsa_acc=8114598302&hsa_cam=19543210959&hsa_grp=&hsa_ad=&hsa_src=x&hsa_tgt=&hsa_kw=&hsa_mt=&hsa_net=adwords&hsa_ver=3&gad_source=1&gad_campaignid=19543202823&gbraid=0AAAAADnDkdYo1dbjDbPk0itHc_ecbeBMf&gclid=CjwKCAjw6NrBBhB6EiwAvnT_rpaGui4igj4oRBstU4S0c-p1oLnQICGl3bQQzf5DCxKHSCoOtP8hJRoCNMEQAvD_BwE) |
| Power Supply | Used to power device, check the power/current required (for 24 solenoid valves: 24 valves x 1.3 watts = 31.2 watts / 12v = 12 v 2.6 A power supply) | 1 | [link](https://www.amazon.com/Adapter-100-240V-Converter-Charger-Transformer/dp/B0DFC9BVVP?gQT=1) |
| Hose Adapter | Compressed air pipe adapter goes from 1/2" OD female (measured, 1/4" labeled) to 6mm push connect | 1 | [link](https://www.amazon.com/Connect-Fittings-CEKER-Pneumatic-Connector/dp/B0BXNQL8R1?th=1) |
| Pressure Regulator | Controls the pressure output to the device | 1 | [link](https://www.amazon.com/Primefit-CR1401G-Replacement-Regulator-steel-Protected/dp/B00IDCYIJ6/ref=sr_1_3?crid=312LPXSUDT6QH&dib=eyJ2IjoiMSJ9.mKdgvXgfdo64E5sqkHdOAJFZ_GCAAScbxYyOtXlYlpSzVSKOrJAiwNubbB5S0E_O1iSZjvwgHI0lQJnGWHys_yYaTl92oCXUgMjHQoPkfWtIeu57enSEQqhftyk6RhrcVTCsh5oPgVJcaOT2vi1uKMblr1xNQdaUA_sNg47vdXICcaUQ6we8HDR3he4jJtKgL5hv9dhFCYGTYx8j7so4LzNvWQlpEtGiBWzfFz8yPtWFK4S9K4TiMxDiMpFGrB9DVP8gXEhg28M36VFxAPqZdb_vbCGRCJhAmxMtnEoIpMM.L6F8oDpKHXASva_gKOSJa-UmjLATpq7mTfKtlwD1NJk&dib_tag=se&keywords=air%20pressure%20regulator&qid=1752801566&s=hi&sprefix=air%20pressure%20regulator%2Ctools%2C116&sr=1-3) |
| Hose Adapter | Adapters for the pressure regulator, goes from 1/4" male to 6mm push connect | 2 | [link](https://www.amazon.com/TAILONZ-PNEUMATIC-Straight-Connect-Fittings/dp/B08S3625XJ/ref=sr_1_1_sspa?crid=2MXX89RRTWWY8&dib=eyJ2IjoiMSJ9.yiQCkFkUgjb5a6BXkS2KbsWzjT-8VMnHTc_ukQln8CY97Cg448Mn_8iOajJtfC-O2exCG7i7CwIJWAJD0O1Xq83PoDZjyXIwea7Zo79ovhgCmEbdFeqMzhgE4SbZJXTBqxR2uSni1nVTt5iOR21ctRxpWVamtxdSmogw6f43XNl5RMmru1cTk68d7u4Yo-IerNMoCZpuRrytt6PnC81SdfgpsMswEoTicwBI9JreElRhqprYP7K05BN8QQoVHYA8sS8rezswmAqIkhISDi38eLzILsPwJRk0M06CSp2NBKA.GLVUPj0xJjQQMGd5eMYdIO7jSWFuePatcsuRawyFO3c&dib_tag=se&keywords=1%2F4%2Bnpt%2Bto%2B6mm&qid=1752803268&s=hi&sprefix=1%2F4%2Bnpt%2Bto%2B6mm%2Ctools%2C118&sr=1-1-spons&sp_csd=d2lkZ2V0TmFtZT1zcF9hdGY&th=1) |


## Download

Download [zip](https://github.com/GNHua/valve-control/archive/master.zip) and extract all files.

## Prepare Software

### Flash Arduino Uno

* Connect an Arduino Uno to computer via USB
* Download and Install [Arduino IDE](https://www.arduino.cc/en/Main/Software)
* Open `arduino_valve_control.ino` in `arduino_valve_control` folder with Arduino IDE
* Select USB port: `Tools` > `Port`
* Click `Upload` (the right arrow at the top left corner)
* Wait for uploading to complete

### Python

* Download and Install Python 3.6
  * The Python distribution, [Anaconda](https://www.anaconda.com/download) is recommended, because it comes with pre-installed packages. 
  * Note: On Windows, the directory of installed Python must be added to environment variable. 
* Install Python dependencies
  * Windows: double click `platforms/windows/setup.bat`
  * MacOSX: `$ bash <path to>/platforms/macosx/setup.sh`

## Soldering

(ADD photos of top and bottom layer after soldering)

Solder all the components according to the [table above](#Electrical-Components-To-Buy). The surface mount components are soldered to the bottom layer, while the rest are mounted on the top layer.

### Stacking Headers

In the [table above](#Electrical-Components-To-Buy), the [stacking headers](https://www.digikey.com/products/en?mpart=85&v=1528) contains the following headers.

| Stacking Header | Label on PCB         | Qty. |
| --------------- | :------------------- | :--: |
| 1 x 10          | cut out a 1x2 for J4 | 1    |
| 1 x  8          | H1, H2               | 2    |
| 1 x  6          |                      | 2    |
| 2 x  3          | J2+J3                | 1    |

### H3 - 5V and GND

Because the JST headers at J11 and J12 block H3 on the top layer, I would do the following:

1. Cut a 1x2 stacking header out of an unused one
2. Solder it on H3 from the bottom layer
3. Cut off the female portion on the top layer
4. Put more solder from the top layer

### Barrel Jack

Each setup only needs one barrel jack to connect to a 12 V power supply. The barrel jack can be soldered on any one of the boards.

## Assembly

### Shift Register and Optoisolators

(The images shown below are all taken for the previous PCB design, which is marginally different from the current design.)

After soldering, plug the shift register and optoisolators into their corresponding DIP sockets. Refer to the following image for their orientation.

![image](pics/assembled_top.jpg)

### Stacking PCBs

#### For the impatient

1. Bend or remove the data pins on all boards except Board 1. See the left image below.
2. Make a connector for serial input and serial output. See the right image below.
3. Stack the PCBs and plug in the connector just made.

| Data Pin | Serial Input/Output |
| -------- | ------------------- |
| <img src="https://github.com/GNHua/valve-control/raw/master/pics/datapin.jpg" height="300"> | <img src="https://github.com/GNHua/valve-control/raw/master/pics/serial_in_serial_out_connector.jpg" height="300"> |

#### Details

In the images above, there are 4 boards stacked on an Arduino Uno.  
Each board provides 8 solenoid valve connectors, and the current design supports up to 6 boards.  
**Before putting the boards together, the data pins on all boards except Board 1 must be bent or removed.**
This is because the data pin connects to the serial input of shift register.
On Board 1, the shift register receives data from the Arduino directly.
For the Board 2-n, their shift registers must have its serial input connected to the serial output of board right beneath it.

<img src="https://github.com/user-attachments/assets/c29f8954-5e7a-43b3-8289-7cb6ce2b5e1a" height="300">

Additionally, the bottom most board (the picture is upside down) must be connected to the arduino through the 5V and GND through holes.
