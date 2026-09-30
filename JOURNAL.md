---
title: "Treeboard"
author: "Alex"
description: "A 75% mechanical low profile keyboard that I designed"
created_at: "2026-08-19"
total_time: "22 hours"
---
For transparency, this was created for the YSWS Keeb, but I do not know if I messed up the submission form, and am unsure if I will be able to finish this.

# Journal

### 2026.08.19
First journal entry of the build progress, I have been browsing the web looking for what keyboard I think would be fun to build, as well as the use of rotary encoders. This is a simple log so far, I have only been brainstorming ideas, looking forward to getting able to build it.

### 2026.08.20

Time Logged: 
2 hours

<img width="2225" height="980" alt="Screenshot_20260820_072820" src="https://github.com/user-attachments/assets/1da52983-f722-456a-b50c-c99b879b88d8" />
I spent some time in onshape planning what I would like the layout of my keyboard to be, I like the design of a 75% since it also makes the space for a rotary encoder.
I will have to check the design to make sure it can fit on the pcb!


I learned a bit about different keyboard layouts, like 60% TKL etc. I think that a 75% will be most practical and a good size to make for this project.

### 2026.08.22

Time Logged: 30mins
0.5 hours
Spent some time learning how to use keyboard design generators, this will save me time when I have to port it into CAD software.
<img width="3054" height="1207" alt="Screenshot_20260822_145927" src="https://github.com/user-attachments/assets/57b2a74d-7813-46ee-b9c3-2b8ad79742d4" />


I learned about KLE and how to use it, I like using the raw text editing since its just like basic coding. I messed around with certain options that I had.



Time Logged: 1.5 hours
I decided to commit to the different layout, as the expanded version in my opinion will be more functional, and visually appealing. I now feel ready to begin the PCB design.
<img width="2187" height="892" alt="Screenshot_20260822_172320" src="https://github.com/user-attachments/assets/8bd238c7-726a-4cdd-8942-6a411161b1e3" />

### 2026.08.23

Logged Time: 1 hour
Created the schematic for the keyboard, used the work I had done earlier to guide the layout, I decided to try and use a nice nano symbol, as there are many cheap ones on aliexpress.

<img width="2252" height="1593" alt="Screenshot_20260823_092817" src="https://github.com/user-attachments/assets/387d478d-8ccf-433a-8df1-dd39530f7466" />

I learned that I need to pay attention to the diode placement, since it will be important when choosing row2col or col2row scanning.


Logged Time: 2 hours
I worked on the PCB now that I had gotten the rough schematic done, this work was done so that I could check the size and components in cad.
Along with the pcb, I worked on combined footprints to support multiple components in the same spot.

<img width="1924" height="779" alt="Screenshot_20260823_130519" src="https://github.com/user-attachments/assets/51ee992e-097e-48a5-a5aa-8069984b5300" />

I learned how to use the KiCad footprint editor, I feel pretty good with it now, my first attempt was copy and pasting raw text data to merge 2 footprints, which did not work. But fixing it manually worked.

### 2026.08.29

Logged Time: 52 mins
0.9 hours
Took a bit of a while between the last time I worked on this.

I had to reroute the schematic and its diodes so that it properly fits the ROW2COL setup rather than the COL2ROW scanning.
While I was doing so, I decided that I should also implement solder pads in the event that one of the pins was not functioning properly.

<img width="2110" height="1195" alt="Screenshot_20260829_130404" src="https://github.com/user-attachments/assets/845ebcb8-9b70-4c57-93d1-8c65c996208b" />

### 2026.08.31

Time Logged: 1.5 hours

Worked on creating the stabilizer mounts, since there are very limited PCB mounted low profile stabilizers, I went with Plate mounted, and had to look through the Gateron datasheets to create a new footprint for the cutouts.
<img width="2042" height="1029" alt="Screenshot_20260831_173445" src="https://github.com/user-attachments/assets/18c9a806-cebd-4c7d-af1f-8fb841ff3cd4" />
I also took some time to reconsider the layout, but decided that this layout for the 75% was going to be the easiest to work with.

I learned about the different between plate and PCB mounted stabilizers, unfortunately for me, the seemingly better of the 2, PCB mounted, which use actual screws instead of clips, is not readily made in the low profile format.

### 2026.09.01

Logged Time: 2 hours

I decided that the wireless idea was not going to be worth it, since the necessary GPIO pins was too many for the pro micro footprint.

A wireless design while nice, is not very much needed. I will focus my efforts on other aspects.

I remade the PCB and Schematic to now use the Rasberry Pi Pico instead.
<img width="2304" height="937" alt="Screenshot_20260901_191930" src="https://github.com/user-attachments/assets/94a68dfa-19b1-44ef-9884-4db75e52d603" />

Note: Since this is a low profile design, I had to add slots in the PCB, this means that it can NOT support PCB screw in stabilizers. This is unfortunate, but low profile is higher on the priority list.

### 2026.09.05

Time Logged: 4 hours

After overcoming my decision paralysis on what to do. I have decided to commit to using a pi pico as the mcu, this is because it will have all of the gpio pins that I need.
I also decided to change the layout from a fully exploded to only partially, compacting most except the function row. This is because I did not like the look of a cover that would have had to be made in many pieces.

<img width="2175" height="919" alt="Screenshot_20260905_233224" src="https://github.com/user-attachments/assets/c5467e25-f00d-4803-8ab9-77d21f059ad5" />
After routing all the traces and resolving most of the errors, it seems that my placement for the pico is not ideal, it has caused some issues with the ground fill and was annoying to route the far sides, I may end up changing it to be more central.

I also made the decision that supporting multiple diode footprints would not be worth it, the tht diodes are much larger and the through hole pads are annoying to deal with for routing.


I learned while routing the traces, it becomes quite compact and tight on space since the switches are rather densely packed. I think there may be some concerns with the ground plane while doing this.

### 2026.09.06

Logged Time: 2 hours

Today I spent some time fiddling with the Pico's placement to optimize the 2 goals I had. Keep the port towards the left region of the board and make traces well routed.

I was able to keep the pico as close to the left as possible, I doubt that moving it towards the center will provide a worthwhile improvement.
I was also able to keep gnd fill between nearly all of the traces.
DRC checker shows 3 errors with the gnd pin connections, but despite this, I believe that they are redundant, and are suitable enough. Though I will check.

<img width="2433" height="1494" alt="Screenshot_20260906_153750" src="https://github.com/user-attachments/assets/629b2236-b083-47d5-ac65-0c656e4b0a07" />





Log 2
Time Logged 3 hours

Got some time this weekend, so I kept going at it.
I exported the PCB and began a prototype case design. To optimize for 3d printing, my goal will be to make the aesthetics work with the maximum sizes.
I also had a mock up for how much of a tilt angle I will need to have on the keyboard to allow clearance for the pico.

<img width="1712" height="579" alt="Screenshot_20260906_190840" src="https://github.com/user-attachments/assets/db6ac791-056e-4460-9746-9051cc9e36db" />

### 2026.09.11

Logged time 45 mins
0.75 hours

Today I used the measurements I took last time to model the actual case. This is a prototype size, but it gives me a sense of how the hardware will fit in place.

<img width="1928" height="510" alt="Screenshot_20260911_181635" src="https://github.com/user-attachments/assets/ada60aca-8d0f-4396-af83-02f19e4fddf0" />

### 2026.09.19

Logged Time: 50 minutes
0.9 Hours

Today I finished up the case design. I finalized the bottom cover mounting by using heat set inserts, and made sure that the overhangs were fixed for some of the parts.

<img width="1819" height="956" alt="Screenshot_20260919_145300" src="https://github.com/user-attachments/assets/36f0fc1a-1c3a-4e92-8955-f9f18f25ed54" />








