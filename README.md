# Bistro_92
Menu-Based Food Ordering System using Arduino

Simulation Drive_Link:https://drive.google.com/file/d/1thehSNac30nnVtCKd0aIbP8aAud-VeDd/view?usp=sharing

1.Project Overview:
This project is a simple food ordering system controlled via pushbuttons and displayed on a 16x2 LCD screen.  
Users can:
- Scroll through menu items
- Set quantity
- Add items to a cart
- Place an order
All operations are handled using four buttons without needing any keyboard or touchscreen.

2.Components Required:
- Arduino UNO (or compatible board)
- 16x2 LCD Display
- 4 Pushbuttons
- Breadboard and Jumper wires
- Resistors (optional, 220Ω for safety)

3.Circuit Diagram (Description):
- LCD Pins** connected to Arduino:
  - RS → Pin 12
  - E  → Pin 11
  - D4 → Pin 5
  - D5 → Pin 4
  - D6 → Pin 3
  - D7 → Pin 2
  - LCD VCC → 5V
  - LCD GND → GND
- Buttons:
  - Menu Button → Pin 8
  - Select Button → Pin 9
  - Up Button → Pin 6
  - Down Button → Pin 7
  - One side of button → GND
  - Other side → Arduino input pin with internal pullup activated.

 5. Working Principle:
- The system uses pushbuttons for user input.
- Up/Down Buttons: Scroll through food items.
- Select Button:
  - Short Press: Select an item and set quantity.
  - Long Press (>1.5 sec): Place order and print cart details.
- Menu Button: Resets the cart and goes back to the main menu.

The LCD shows the current selection and quantity dynamically.  
The Serial Monitor outputs cart details for verification.

 6. Software/Programming:
- Developed using Arduino IDE (C/C++ language).
- Used LiquidCrystal.h library to control the LCD.
- Debouncing is handled using simple *delay()* functions after each button press.
- Button logic is built around *INPUT_PULLUP* mode to simplify circuit design.
- Long press detection is implemented using *millis()* timer.

7. Code Explanation :
This Arduino code creates a simple menu system on a 16x2 LCD screen using buttons to navigate, select, and order items.
•	Buttons (Menu, Select, Up, Down) let the user scroll through a food menu (Burger, Pizza, Pasta, Drinks), pick an item, and set its quantity.
•	When an item is selected, the user adjusts the quantity with Up/Down, and pressing Select adds it to a cart (which can hold up to 5 items).
•	Holding down the Select button for more than 1.5 seconds triggers a long press, placing the order — it shows "Placing Order..." and sends the order details to the Serial Monitor.
•	Pressing the Menu button resets the cart anytime.

- showMenu(): Displays the list of menu items.
- showQuantity(): Lets the user set quantity after selecting an item.
- placeOrder(): Displays the order details and resets the cart.
- resetCart(): Clears all cart data to start fresh.
- loop(): Continuously checks button presses and updates LCD accordingly.

8. Applications:
- Self-order kiosks at small food courts or cafes.
- Menu navigation systems.
- Basic learning project for:
  - Button control
  - LCD interfacing
  - State machine concepts


9. Future Improvements :
- A buzzer for feedback sounds can be added.
- A EEPROM storage to save cart items even after reset can be added
- Use of a simple touch sensor instead of buttons 
-Use of Bluetooth/Wi-Fi for mobile app for order placement.
