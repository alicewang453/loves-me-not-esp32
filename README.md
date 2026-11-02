# Loves Me, Loves Me Not

A small hanging art installation that plays "he loves me, he loves me not" forever. A screen draws a flower with a random number of petals, then plucks them one at a time while alternating between "loves me" and "loves me not," and lands on a final answer before starting a new flower.

<img src="hungup.png" width="400" alt="The installation: a decorated envelope holding the ESP32 screen, hung from a ceiling vent">

## How it works

The code is a single Arduino sketch, [`creative_installation1.ino`](creative_installation1.ino), running on a TTGO T1 (an ESP32 board with a built-in screen):

- **Random flowers**: each round picks 6–11 petals and a speaker ("He loves," "She loves," "They love" or "I love").
- **Drawing petals**: each petal is a chain of filled circles laid along an angle of `i × 360° / petals` from the center. Plucking a petal redraws it in the background color.
- **Smooth text**: messages are drawn into off-screen sprites with the TFT_eSPI library and pushed to the screen all at once, so they don't flicker.
- **Battery life**: it runs on a small rechargeable battery and uses the ESP32's deep sleep between cycles to save power.

## Tech

C++ (Arduino) · ESP32 · TFT_eSPI

Built for COMS 3930 at Columbia (Module 1: generative art installation).

## Build it yourself

**Hardware materials:**
* TTGO T1 board with built-in ESP32 microcontroller 
* USB-C to USB-C cable 
* Laptop with USB-C port

Installation Materials: 
* Envelope
* [Rechargeable Battery](https://www.makerfocus.com/products/4pcs-952540-3-7v-1000mah-battery-with-jst1-25-connector-lithium-rechargeable-battery)
* Hole puncher
* Electric drill
* Tape
* Thread
* Popsicle Sticks (2) 
* Pencil, eraser, colored pens, colored pencils 

Process: 
1. Connect TTGO T1 board to laptop via USB-C to USB-C cable. Set up Arduino IDE by selecting “TTGO T1” for board and the correct USB-C port. 
2. Develop program (found in repo) in Arduino IDE.
3. Upload code to device.
4. Repeat steps 2 and 3 until graphic looks right (see in blogpost the technical challenge of drawing petals)
5. Draw Yoshi design on envelope with pencil, then go over with colored pens (Note, at time of installation, only colored pens were available - step 9's image is post-installation, colored in with colored pencils).
   
   <img src="drawing.png" width="400" alt="Alt text for image">
   
7. Drill a small hole in the middle of each popsicle stick.
   
   <img src="drill.png" width="400" alt="Alt text for image">
   
8. Use the hole puncher to punch 2 holes in the envelope - one in the top left corner, and one in the top right corner.
9. Cut 2 pieces of thread of equal length. Decide length based on how far you want the device to hang from the ceiling.
10. Designate the 2 popsicle sticks to correspond with each of the 2 holes in the envelope. Similarly, designate the 2 pieces of thread with each of the 2 sticks/holes. Tie one end of each thread into its designated popsicle stick and the other end into its designated envelope hole.

    <img src="stick.png" width="400" alt="Alt text for image">
    
11. Hang the device by slotting the popsicle sticks into the ceiling air vent!
    
    <img src="hungup.png" width="400" alt="Alt text for image">

