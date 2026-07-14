--- 
title: "Flower Press"
description: "Project Documentation for a Flower Press"
layout: default
---

# Flower Press

While not incredibly technical, this was still a fun and creative project to work on!

I had wanted to make a flower press like this for a while. The design, based on a similar press that belonged to my great grandma, is fairly simple. It is essentially a sandwich-like mechanism that presses flora in between the wooden planks in order to preserve them. I made this particular press as a gift.

## Initial Design

I started the project by scribbling down some ideas and drawings about what I wanted the press to look like, how the press would stay intact, and how the press would apply pressure in order to efficiently press the flowers or leaves placed in it.

<p align="center"> 
<img src="Images/FlowerPress/drawing.jpg" alt="Centered Image" style="max-width:50%"> 
</p> 

I wanted the press to have multiple layers so that multiple flora could be pressed at the same time, which is why you see multiple stacks of wood in the bottom left of the above picture.

## Manufacturing

To build the press, I bought a couple of ¾”x2’x4’ pieces of wood. I then used a table saw to cut the wood into usable chunks, which were slightly larger than a standard piece of printer paper.

I taped together the best cuts so that their edges aligned as best as they could, and I used a drill press to create the holes for the bolts that would hold the whole contraption together.

<p align="center"> 
<img src="Images/FlowerPress/taped.jpg" alt="Centered Image" style="max-width:50%"> 
</p> 

I was then able to use the bolts, washers, and wing nuts to secure everything in place.

<p align="center"> 
<img src="Images/FlowerPress/cut_raw.jpg" alt="Centered Image" style="max-width:50%"> 
</p> 

Finally, I used a bandsaw to further line up each of the individual pieces and sandpaper to smooth the entire surface.

<p align="center"> 
<img src="Images/FlowerPress/rounded.jpg" alt="Centered Image" style="max-width:50%"> 
</p> 

## Beautification

After constructing the press, I did multiple rounds of staining the wood to create a rich color. I then bought some flower-themed stencils from Michaels and spray painted patterns onto the top of the press using various colors. To finish it off, I applied several layers of polyurethane to act as a protective coat.

<p align="center"> 
<img src="Images/FlowerPress/headon.png" alt="Centered Image" style="max-width:50%"> 
</p> 

<p align="center"> 
<img src="Images/FlowerPress/fromtheside.png" alt="Centered Image" style="max-width:50%"> 
</p> 

## Usage

Here is a rose that I was able to press and later frame!

<p align="center"> 
<img src="Images/FlowerPress/rose.jpg" alt="Centered Image" style="max-width:50%"> 
</p> 



<!-- Load PyScript assets safely into your Jekyll page -->
<link rel="stylesheet" href="https://pyscript.net" />
<script defer src="https://pyscript.net"></script>

<div style="margin: 20px 0; border: 1px solid #ccc; padding: 10px; border-radius: 5px; background: #f9f9f9;">
  <p><strong>🌸 Flower Press Simulator Terminal:</strong> Click inside to type.</p>
  
  <script type="mpy" terminal worker>
import time

async def run_press_simulator():
    print("====================================")
    print("      FLOWER PRESS SIMULATOR        ")
    print("====================================\n")
    
    name = await input("Enter your name to start pressing: ")
    print(f"\nWelcome, {name}! Let's prep the wooden planks.")
    
    layers = ["Empty", "Empty", "Empty"]
    
    while True:
        print("\n--- Current Press Status ---")
        for i, layer in enumerate(layers, 1):
            print(f"Layer {i}: {layer}")
        print("----------------------------")
        
        print("\nWhat would you like to do?")
        print("1. Add a flower to a layer")
        print("2. Tighten wing nuts (Process Pressing)")
        print("3. Reset press")
        print("4. Exit simulator")
        
        choice = await input("Select an option (1-4): ")
        
        if choice == "1":
            try:
                layer_num = int(await input("Which layer (1-3)? "))
                if 1 <= layer_num <= 3:
                    flower = await input("What flower/leaf are you placing inside? ")
                    layers[layer_num - 1] = f"Fresh {flower}"
                    print(f"\n--> Placed {flower} into Layer {layer_num}!")
                else:
                    print("\n[Error] Invalid layer number.")
            except ValueError:
                print("\n[Error] Please enter a valid number.")
                
        elif choice == "2":
            print("\nTightening bolts and wing nuts...")
            time.sleep(1)
            print("Applying even pressure across the 3/4\" wood planks...")
            time.sleep(1)
            
            for i in range(3):
                if "Fresh" in layers[i]:
                    layers[i] = layers[i].replace("Fresh", "Perfectly Pressed")
            print("\n--> Done! Your flora has been preserved.")
            
        elif choice == "3":
            layers = ["Empty", "Empty", "Empty"]
            print("\n--> Press cleared and reset.")
            
        elif choice == "4":
            print(f"\nThanks for using the simulator, {name}!")
            break
        else:
            print("\n[Error] Invalid choice. Choose 1, 2, 3, or 4.")
        time.sleep(0.5)

run_press_simulator()
  </script>
</div>

