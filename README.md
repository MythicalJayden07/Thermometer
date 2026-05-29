# Thermometer
A thermometer with an attiny 85!
# KRYO-VALE

A sleek, handheld digital thermometer project built completely from scratch. 

It uses a custom-designed PCB tucked inside a 3D-printed cylindrical case that snaps together without any screws. A neat little OLED screen on the front gives you real-time temperature stats.

I designed this to learn the ropes of hardware engineering, custom PCB routing, and 3D modeling on curved surfaces.

---

## 🔌 The Schematic

Here is the electrical logic behind the build. It shows how the microcontroller links up with the 128x32 OLED screen over the I2C bus and connects to the digital temperature probe. I added pull-up resistors to keep the data lines stable and prevent signal noise inside the case.

<img width="1605" height="717" alt="Screenshot 2026-05-12 012002" src="https://github.com/user-attachments/assets/bbd4ff4b-15e8-4f23-bf1d-3bfdcab29fb4" />


---

## 🎛️ The PCB Layout

This is the custom 35mm wide board routed in KiCad. Since space inside a cylinder is super tight, everything had to be placed strategically. The components use low-profile footprints, and the board edges are perfectly sized to slide straight into the 3D-printed internal rails without rattling.
<img width="936" height="756" alt="Screenshot 2026-05-12 011945" src="https://github.com/user-attachments/assets/b5a4a94d-4167-462f-9ad7-74184aa7e96f" />


---

## 📐 The CAD Design

The enclosure modeled in Fusion 360. It’s a two-part interlocking cylinder that uses a lip-and-groove joint to snap-lock shut without needing a single screw. 

To get the rectangular OLED window to sit perfectly flat on a curved surface, I used a tangent-plane projection to punch the cutout. I also added a dedicated 5mm circular hole right at the dead center of the bottom face so the temperature probe wires can pass through cleanly and pop out the base.
<img width="947" height="690" alt="Screenshot 2026-05-12 011955" src="https://github.com/user-attachments/assets/717ee9be-201d-42c1-9864-ae77d266d9c4" />
<img width="1918" height="1075" alt="Screenshot 2026-05-12 235535" src="https://github.com/user-attachments/assets/33de7286-8f26-40a5-8809-a739388018fc" />
<img width="406" height="613" alt="Screenshot 2026-05-25 112413" src="https://github.com/user-attachments/assets/4b2cecb1-a9e5-4987-849c-88948dad647f" />
<img width="464" height="631" alt="Screenshot 2026-05-25 112544" src="https://github.com/user-attachments/assets/7b91b519-4dca-4e62-aeff-906fb3a5f31e" />
<img width="354" height="314" alt="Screenshot 2026-05-25 112444" src="https://github.com/user-attachments/assets/1130ed86-2911-4fd9-93f8-8ce3fff45fef" />
<img width="607" height="633" alt="Screenshot 2026-05-25 111834" src="https://github.com/user-attachments/assets/476bb7e1-7534-4ff3-9007-a4b4a9094766" />


---

## 🛠️ How it Goes Together

1. **Print the Case:** 3D print the two shell halves. They use a lip-and-groove joint to snap lock together tightly.
2. **Solder the Board:** Populate the PCB with the resistors, headers, and components.
3. **Flash it:** Flash the firmware onto the micro-controller.
4. **Assembly:** Slide the PCB into the case rails, push the sensor through the bottom hole, and snap the handle shut.

---

## 👋 About Me
This is my second official hardware repo! Messing around with CAD timelines and PCB footprints has been a journey, but seeing it all come together is awesome. 

## BOM
[Thermometer.csv](https://github.com/user-attachments/files/28411570/Thermometer.csv)

---

| Reference | Qty | Value | Footprint | Exclude Status | Datasheet | Purchase Link |
| :--- | :---: | :--- | :--- | :--- | :---: | :---: |
| **A1** | 1 | Arduino_Nano_v3.x | `Module:Arduino_Nano` | Excluded from board | [Datasheet](http://www.mouser.com/pdfdocs/Gravitech_Arduino_Nano3_0.pdf) | [Buy Here](https://robu.in/product/arduino-nano-board-3-0-with-ch340-chip-unsoldered/) |
| **BT1** | 1 | Battery_Cell | `Battery:BatteryHolder_Keystone_3002_1x2032` | — | — | [Buy Here](https://www.digikey.in/en/products/detail/keystone-electronics/3002/227444?msockid=2353f8918b6f63df132eeff98ada62c1) |
| **BZ1** | 1 | Buzzer | `Buzzer_Beeper:Buzzer_TDK_PS1240P02BT_D12.2mm_H6.5mm` | — | — | [Buy Here](https://mou.sr/3MZ5Tfb) |
| **C1** | 1 | C | — | Excluded from board | — | [Buy Here](https://in.element14.com/chemi-con/ekmg160ell100me11d/aluminum-electrolytic-capacitor/dp/1686765) |
| **R1** | 1 | 4.7k | `Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal` | — | — | [Buy Here](https://robu.in/product/4-7k-ohm-0-25w-metal-film-resistor-pack-of-100/) |
| **R2** | 1 | 5.6k | `Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P7.62mm_Horizontal` | — | — | [Buy Here](https://a.co/d/0f5nhf8v) |
| **U2** | 1 | ATtiny85-20P | `Package_DIP:DIP-8_W7.62mm` | — | [Datasheet](http://ww1.microchip.com/downloads/en/DeviceDoc/atmel-2586-avr-8-bit-microcontroller-attiny25-attiny45-attiny85_datasheet.pdf) | [Buy Here](https://mou.sr/3MYk2cD) |
| **U3** | 1 | DS18B20 | `Package_TO_SOT_THT:TO-92_Inline` | — | [Datasheet](http://datasheets.maximintegrated.com/en/ds/DS18B20.pdf) | [Buy Here](https://amzn.in/d/0bOUQO8z) |
| **U4** | 1 | ER_OLEDM0.91_1x-I2C | `Display:ER_OLEDM0.91_1x-I2C` | — | [Datasheet](https://www.buydisplay.com/download/manual/ER-OLEDM0.91-1_Datasheet.pdf) | [Buy Here](https://robu.in/product/0-91-inch-128x32-i2c-iic-serial-blue-oled-lcd-display-module/) |
| — | 1 | CR2032 Battery | Physical Coin Cell (3V Lithium) | — | — | [Buy Here](https://a.co/d/0gqPE7Ru) |






