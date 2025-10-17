🐍 VeriSnake – Snake Game on FPGA

- A complete hardware-level implementation of the classic Snake Game using Verilog HDL, designed for the Basys3 FPGA board with real-time VGA output.

🎮 Overview
- VeriSnake is a pure hardware recreation of the nostalgic Snake Game, built entirely in Verilog HDL and displayed through a VGA interface at 640×480 resolution.
- All movement, scoring, and collision logic are executed at the RTL (Register Transfer Level) — no microcontroller or processor used.
- Control the snake using the Basys3 onboard buttons, collect food to grow longer, avoid obstacles, and watch your score increase in real time.
- The game features restart, pause/resume, and special bonus food for an exciting gameplay experience — all on FPGA hardware!


🧩 Key Features
- Real-time Snake Movement using FSM
- VGA Display @ 640×480 Resolution
- Color-coded Elements:
 • Head – Bright Green
 • Body – Dark Green
 • Food – Blue Circle
 • Obstacles – Red Blocks
 • Special Food – Yellow (Gives +5 Points)
- Real-time Score Display in White (Top-Right Corner)
- Game Over Message at Center
- Restart the Game using btnC (Resets Score & Snake Position)
- Pause/Resume using btnL / btnR Long Press
- Modular & Readable Verilog Structure

⚙️ Technical Implementation
🔹 Core Modules
- Module	Function
- snake_main.v	Core game logic: snake control, collision, scoring, restart, pause/resume
- vga_sync_snake.v	Generates HSync, VSync, and visible pixel region for VGA output
- clk25_gen.v	Converts 100 MHz Basys3 clock to 25 MHz VGA clock
- clk_pulse_gen.v	Generates slow (~20 Hz) game tick clock for snake speed control


🍎 Gameplay Logic

- 🎯 Regular Food
- Appears as a blue circle
- Adds +1 point to score
- Randomly relocates after being eaten
- Increases snake length by 1 segment

⭐ Special Food
- Appears occasionally as a yellow circle
- Adds +5 points to score
- Visible for limited frames (temporary)
- Encourages risk–reward gameplay

💥 Collision Conditions
- Snake hits itself → Game Over
- Snake hits obstacle → Game Over

🔁 Restart & Pause
- Restart (btnC): Resets snake, score, and food positions
- Pause/Resume (btnL or btnR long press): Freezes or resumes game clock

🧠 Concepts Applied
- Finite State Machine (FSM) Design
- VGA Signal Timing and Synchronization
- Multi-clock Domain Design
- Real-time Graphics Rendering in Hardware
- Collision Detection and Scoring Logic
- Modular Verilog Design Principles

🧰 Technologies Used
- Verilog HDL
- Xilinx Vivado 2025.1
- Basys3 FPGA Board (Artix-7)
- VGA Display Protocol (640×480 @ 60 Hz)

👨‍💻 Author
Pranav Pissay
🎓 Electrical & Electronics Engineering
🔗 LinkedIn

🏷️ License
This project is licensed under the MIT License
