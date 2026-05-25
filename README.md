# Thermometer
A thermometer with an attiny 85!
# KRYO-VALE

A sleek, handheld digital thermometer project built completely from scratch. 

It uses a custom-designed PCB tucked inside a 3D-printed cylindrical case that snaps together without any screws. A neat little OLED screen on the front gives you real-time temperature stats.

I designed this to learn the ropes of hardware engineering, custom PCB routing, and 3D modeling on curved surfaces.

---

## 🔌 The Schematic

Here is the electrical logic behind the build. It shows how the microcontroller links up with the 128x32 OLED screen over the I2C bus and connects to the digital temperature probe. I added pull-up resistors to keep the data lines stable and prevent signal noise inside the case.

![Project Schematic]("C:\Users\Jayden\OneDrive\Pictures\Screenshots 1\Screenshot 2026-05-12 012002.png")

---

## 🎛️ The PCB Layout

This is the custom 35mm wide board routed in KiCad. Since space inside a cylinder is super tight, everything had to be placed strategically. The components use low-profile footprints, and the board edges are perfectly sized to slide straight into the 3D-printed internal rails without rattling.

![PCB Layout]("C:\Users\Jayden\OneDrive\Pictures\Screenshots 1\Screenshot 2026-05-12 011955.png")

---

## 📐 The CAD Design

The enclosure modeled in Fusion 360. It’s a two-part interlocking cylinder that uses a lip-and-groove joint to snap-lock shut without needing a single screw. 

To get the rectangular OLED window to sit perfectly flat on a curved surface, I used a tangent-plane projection to punch the cutout. I also added a dedicated 5mm circular hole right at the dead center of the bottom face so the temperature probe wires can pass through cleanly and pop out the base.

![CAD Design]("C:\Users\Jayden\OneDrive\Pictures\Screenshots 1\Screenshot 2026-05-25 111834.png") "C:\Users\Jayden\OneDrive\Pictures\Screenshots 1\Screenshot 2026-05-25 112544.png"

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
"C:\Users\Jayden\OneDrive\ドキュメント\marcopad\Thermometer\Thermometer.csv" 
---

## 📦 Bill of Materials (BOM)

These are the exact components used to assemble the **KRYO-VALE** active board. All footprints match standard, easy-to-source through-hole components.

| Reference | Qty | Value | Component Description | Footprint Type |
| :--- | :---: | :--- | :--- | :--- |
| **U2** | 1 | ATtiny85-20P | 8-bit AVR Microcontroller (The Brains) | `Package_DIP:DIP-8_W7.62mm` |
| **U3** | 1 | DS18B20 | Digital Temperature Sensor | `Package_TO_SOT_THT:TO-92_Inline` |
| **U4** | 1 | 0.91" OLED | Waveshare / BuyDisplay I2C Screen | `Display:ER_OLEDM0.91_1x-I2C` |
| **R1** | 1 | 4.7kΩ | Pull-up Resistor | `Resistor_THT:R_Axial_DIN0207...` |
| **R2** | 1 | 5.6kΩ | Pull-up Resistor | `Resistor_THT:R_Axial_DIN0207...` |
| **BT1** | 1 | CR2032 | 3V Coin Cell Battery Holder | `Battery:BatteryHolder_Keystone_3002` |
| **BZ1** | 1 | Buzzer | TDK Magnetic Audio Indicator | `Buzzer_Beeper:Buzzer_TDK_PS1240...` |


