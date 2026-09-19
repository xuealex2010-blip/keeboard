# Keeboard
Hack Club Sponsored DIY Keyboard

Hey, thanks for checking this out, this is my own attempt at creating a DIY 75% Low Profile Mechanical Keyboard.

More details about the process can be found in the Journal Logs.

## CAD
https://cad.onshape.com/documents/ea891d14d2da634eb3b1d96d/w/6142ce2636ba78c1d8d6bd10/e/d20a11642471013c1442f2cf

<img width="2310" height="1335" alt="Screenshot_20260919_161556" src="https://github.com/user-attachments/assets/edefbc54-321a-4b6a-87cb-14db47dd6922" />

I decided to go for an affordable green keycap set since I love the color and its one of the cheapest low profile options.

<img width="1819" height="956" alt="Screenshot_20260919_145300" src="https://github.com/user-attachments/assets/ecf838d2-2046-4d28-9471-258b829aa2f3" />

I used heat set inserts and square nuts to hold the case together, I think that this is better than a large 3D print as its designed to be printed at that size. I used only 2 screw lengths which kept the hardware costs low.

## KiCad

### Schematic

<img width="2525" height="1423" alt="Screenshot_20260919_162051" src="https://github.com/user-attachments/assets/6ec1077b-513b-4de1-86e6-6bdad163432d" />

The schematic final design uses a very basic layout of all the switches. 
I used a generic connector instead of the PiPico symbol to manage the GPIO positions better. I made sure to double check with the official pinouts.

### PCB

<img width="2042" height="872" alt="Screenshot_20260919_162352" src="https://github.com/user-attachments/assets/5a7ecd4e-ad7a-4313-9337-b728aaacf16e" />

This PCB uses a lot more vias than expected, this was to separate the long traces better, and improve ground fill space.

I also made special edge cuts in the PCB, this is because the low profile layout stabilizers drop deep below the plate that it would collide with the PCB if not so.
