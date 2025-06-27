---
title: "Note"
author: "Dhiaan Dave"
description: "An open source speaker for all your music needs, completed with dual speakers and bluetooth compatibility."
created_at: "2025-04-21"
---
# June 22th: Part Sourcing!

I spent my whole morning putting together the component list for my speaker. I went with the Seed Xiao RP2040 as the microcontroller because it was the same thing used for my hackpad so I was used to its specs. Then I found parts on Amazon for the battery, the audio amplifier, and RGB lights to make my speaker look cool. Then I scavenged Ebay to find a bluetooth module. Then I found a boost converter but the actual part costs $1.50 but shipping is like $10! Pretty sure that shipping is the real price for the item and the price written is just to get people to buy it. I found some more connectors for my board and when I put the whole price together it came to around $70 bucks. However since the projects have a point scale of 4, 6, and 10, I was concerned as I thought this was a 4 and the 4 projects have a budget of $50. Luckily, when I asked in the Slack channel, an admin responded and told me that most custom projects default to 6 points and 4 points was for the hackpad. So I have a budget of $150 now! And I probably need it after seeing all the extra things I need to fix all of the problems.

![image](https://github.com/user-attachments/assets/e622f0d2-4193-41b5-b94d-984aea90cb86)

**Total time spent this session: 2h**
---
# June 26th: Starting and finishing the project!

After procastinating for 4 days on how the Bluetooth module doesn't have a KiCad footprint and it seems super outdated, I thought of actually facing the problem. My first thought was to make a symbol but then I realized that I have no idea about the dimensions or anything for the footprint. It was really unfortunate that the Seeed Xiao RP2040 doesn't support bluetooth. Then I thought, "What if I just switch to a different Seeed Xiao that has Bluetooth". So I went with the Seeed Xiao ESP32C6 which has inbuilt Bluetooth. Everything was going fine until I decided to connect the board to the audio amplifier. Did I mention that the audio amplifier had a very weird symbol and footprint in Kicad. So I decided to find a custom one and then too after I added the symbol for some reason I just couldn't connect to any of the pins. So I manually went in and added all the pins. Then I found out that the input for the left and right speakers have to be analog and the Seeed Xiao ESP32C6 doesn't have any digital to analog pins and infact it has analog to digital pins. So instead of searching for a whole new module for DAC pins I switched to a full sized ESP32 WROOM 32. Finally I have all the pins I need! Not quite. See, the battery stores VBAT and GND. The ESP32 WROOM 32 can take GND and 3.3V only. No VBAT because VBAT can sometimes go over 3.3V. So now I have two problems, the first one being how to get the ESP32 WROOM 32 to take the VBAT if it goes above voltage and 2nd how to actually use the 3.3V. So I came up with a solution. I implemented a new charging module and after much research I added a cool thing called a voltage regulator! ![image](https://github.com/user-attachments/assets/dd9a889a-640b-4c4c-b2d9-7fff6774bd92)

![image](https://github.com/user-attachments/assets/c401b853-9ab7-450b-aeed-2c57d1952527)

So I had to make a footprint from scratch for the charging module but luckily the volatge module was so cool as it already had a symbol and footprint. So I finished up my PCB as a circle to get a round speaker with a diameter of 95.411 milimeters. Now all I have to make is the case. So since in the past week a bunch of people were like Onshape is fire, I tried out Onshape. Previously I tried out Fusion 360 which was good but there was a bit of a learning curve and also I was running the web version as my computer was running out of space but the issue with that was that it took a very very very long time to load and then randomly it would sign me out. If I had not saved my design before I got signed out, I would lose it. So I tried Onshape and watched different tutorials for each thing I wanted to do. ![image](https://github.com/user-attachments/assets/507c6683-49d5-4228-8a30-23b07c1781c0)

Finally I finished my speaker's whole case with a diameter of 101 milimeters so the PCB can fit through and also 2 40.5 milimeter cutouts on the side for my dual speakers, a 18 milimeter cutout for the charger to peek through, and I topped it all of with my project's name, "Note", on top. Then it was pretty late so I decided to submit it on friday. ![image](https://github.com/user-attachments/assets/47ac576d-4aeb-4768-a01a-620a474ba955)

**Total time spent this session: 8h**
