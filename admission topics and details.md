# BUET Admission Test - Complete Study Guide

## Test Format
- **Duration**: 45 minutes
- **Type**: Multiple Choice Questions (MCQ)
- **Requirement**: Answer all questions from all topics

---

## 🎯 Learning Storyline: Building a Smart Home System

**Meet Rafi**, an aspiring engineer who wants to build a complete Smart Home Automation System. Throughout his journey, he'll use concepts from all 6 topics:

1. **Programming Languages** - Write Python code to control devices
2. **Digital Logic Design** - Design circuits for sensors and controllers
3. **Communication Theory** - Enable wireless communication between devices
4. **Computer Architecture** - Use microprocessors to process data
5. **Computer Networks** - Connect all devices via home network
6. **Electronic Devices** - Build hardware components (sensors, actuators)

As you study each topic, imagine how Rafi uses these concepts to build his smart home. This real-world context will help you remember better!

---

## 1. Programming Languages

### 🏠 Story Context: Rafi writes Python code to control his smart home devices

### 1.1 Python Fundamentals

#### Data Types
- **Numeric Types**
  - `int`: Whole numbers (e.g., 5, -10, 0)
    - **Example**: `room_temperature = 25` (storing room temp)
  - `float`: Decimal numbers (e.g., 3.14, -0.5)
    - **Example**: `humidity = 65.5` (humidity percentage)
  - `complex`: Complex numbers (e.g., 2+3j)
    - **Example**: Used in signal processing calculations

- **String (str)**
  - Sequence of characters in quotes
  - Immutable
  - Operations: concatenation (+), repetition (*), slicing, indexing
  - Methods: `upper()`, `lower()`, `strip()`, `split()`, `join()`, `replace()`
  - **Example**:
    ```python
    device_name = "Living Room Light"
    status = "ON" + " since 7PM"  # Concatenation
    print(device_name.lower())  # "living room light"
    ```

- **Boolean (bool)**
  - Two values: `True` or `False`
  - Result of comparison operations
  - **Example**:
    ```python
    light_on = True
    door_locked = False
    is_night = (current_hour >= 18)  # True if after 6 PM
    ```

- **Collections**
  - **List**: Ordered, mutable, allows duplicates `[1, 2, 3]`
    - **Example**: `temperatures = [25, 26, 24, 25, 27]` (hourly temps)
  - **Tuple**: Ordered, immutable, allows duplicates `(1, 2, 3)`
    - **Example**: `sensor_location = ("Living Room", "North Wall", 1.5)` (room, wall, height)
  - **Set**: Unordered, mutable, no duplicates `{1, 2, 3}`
    - **Example**: `active_devices = {"light", "fan", "AC"}` (unique devices)
  - **Dictionary**: Key-value pairs, unordered, mutable `{'name': 'John', 'age': 25}`
    - **Example**:
      ```python
      smart_home = {
          'lights': 'ON',
          'temperature': 25,
          'doors_locked': True,
          'active_devices': 5
      }
      ```
- **Assignment**: `=`, `+=`, `-=`, `*=`, `/=`, `%=`
- **Membership**: `in`, `not in`
- **Identity**: `is`, `is not`

#### Control Structures
```python
# If-Else
if condition:
    # code
elif another_condition:
    # code
else:
    # code

# For Loop
for item in sequence:
    # code

# While Loop
while condition:
    # code

# Break, Continue, Pass
break      # Exit loop
continue   # Skip to next iteration
pass       # Do nothing (placeholder)
```

**Smart Home Example**:
```python
# Control lights based on time and motion
if motion_detected and current_hour >= 18:
    lights = "ON"
    print("Motion detected at night - Lights turned ON")
elif current_hour < 6:
    lights = "DIM"
else:
    lights = "OFF"

# Check all sensors
for sensor in ["door", "window", "motion", "smoke"]:
    if sensor_status[sensor] == "alert":
        send_notification(f"{sensor} alert!")
        break  # Exit after first alert

# Monitor temperature continuously
while temperature > 30:
    run_ac()
    time.sleep(60)  # Check every minute
```

#### Built-in Functions
- `abs()`: Absolute value
- `len()`: Length of sequence
- `max()`, `min()`: Maximum/minimum value
- `sum()`: Sum of numbers
- `range()`: Generate sequence of numbers
- `type()`: Get data type
- `int()`, `float()`, `str()`: Type conversion
- `input()`: Get user input
- `print()`: Display output
- `sorted()`: Return sorted list
- `reversed()`: Reverse sequence

#### Functions
```python
# Function definition
def function_name(parameters):
    # code
    return value

# Lambda functions
lambda x: x * 2

# Function with default parameters
def greet(name="Guest"):
    return f"Hello, {name}"
```

**Smart Home Example**:
```python
# Function to control devices
def control_device(device_name, action="toggle"):
    if action == "ON":
        devices[device_name] = True
        return f"{device_name} turned ON"
    elif action == "OFF":
        devices[device_name] = False
        return f"{device_name} turned OFF"
    return f"{device_name} toggled"

# Calculate energy consumption
def calculate_energy(power_watts, hours):
    return power_watts * hours / 1000  # kWh

# Lambda for temperature conversion
celsius_to_fahrenheit = lambda c: (c * 9/5) + 32

# Usage
control_device("Living Room Light", "ON")
energy = calculate_energy(100, 5)  # 100W bulb for 5 hours = 0.5 kWh
temp_f = celsius_to_fahrenheit(25)  # 77°F
```

#### Error Handling
- **Syntax Errors**: Code structure errors (detected before execution)
- **Runtime Errors**: Occur during execution
  - `ZeroDivisionError`: Division by zero
  - `TypeError`: Wrong data type
  - `ValueError`: Invalid value
  - `IndexError`: Index out of range
  - `KeyError`: Key not found in dictionary
  - `NameError`: Variable not defined

```python
try:
    # risky code
except ErrorType:
    # handle error
finally:
    # always executes
```

**Smart Home Example**:
```python
# Reading sensor data with error handling
try:
    temperature = int(sensor.read_temperature())
    if temperature < -50 or temperature > 100:
        raise ValueError("Temperature out of range")
    print(f"Temperature: {temperature}°C")
except ValueError as e:
    print(f"Invalid sensor reading: {e}")
    temperature = 25  # Default safe value
except ZeroDivisionError:
    print("Cannot divide by zero in calculation")
except KeyError:
    print("Device not found in registry")
finally:
    # Always log the attempt
    log_file.write(f"Sensor read at {time.now()}\n")
```

### 1.2 Object-Oriented Programming
- **Class**: Blueprint for creating objects
- **Object**: Instance of a class
- **Inheritance**: Child class inherits from parent
- **Polymorphism**: Same method, different implementations
- **Encapsulation**: Bundling data and methods
- **Abstraction**: Hiding complex details

**Smart Home Example**:
```python
# Base class for all smart devices
class SmartDevice:
    def __init__(self, name, location):
        self.name = name
        self.location = location
        self.is_on = False

    def turn_on(self):
        self.is_on = True
        return f"{self.name} is now ON"

    def turn_off(self):
        self.is_on = False
        return f"{self.name} is now OFF"

# Inheritance: Light inherits from SmartDevice
class SmartLight(SmartDevice):
    def __init__(self, name, location, brightness=100):
        super().__init__(name, location)
        self.brightness = brightness

    def set_brightness(self, level):
        self.brightness = level
        return f"Brightness set to {level}%"

# Polymorphism: Different devices, same method name
class SmartThermostat(SmartDevice):
    def __init__(self, name, location, temp=25):
        super().__init__(name, location)
        self.temperature = temp

    def turn_on(self):  # Overrides parent method
        self.is_on = True
        return f"AC started at {self.temperature}°C"

# Usage
light = SmartLight("Bedroom Light", "Bedroom")
light.turn_on()
light.set_brightness(75)

thermostat = SmartThermostat("Living Room AC", "Living Room", 24)
thermostat.turn_on()
```

### 1.3 Data Structures & Algorithms
- **Arrays**: Fixed-size sequential collection
- **Linked Lists**: Nodes connected by pointers
- **Stacks**: LIFO (Last In First Out)
- **Queues**: FIFO (First In First Out)
- **Trees**: Hierarchical structure
- **Graphs**: Nodes and edges

**Sorting Algorithms**:
- Bubble Sort: O(n²)
- Selection Sort: O(n²)
- Insertion Sort: O(n²)
- Merge Sort: O(n log n)
- Quick Sort: O(n log n) average

**Searching Algorithms**:
- Linear Search: O(n)
- Binary Search: O(log n) - requires sorted array

**Smart Home Example**:
```python
# Linear Search: Find a device by name
devices = ["Light", "Fan", "AC", "TV", "Heater"]
search_device = "AC"
for i, device in enumerate(devices):
    if device == search_device:
        print(f"{device} found at position {i}")
        break

# Binary Search: Find temperature in sorted log
temp_log = [20, 21, 22, 23, 24, 25, 26, 27, 28]  # sorted
target = 25
left, right = 0, len(temp_log) - 1
while left <= right:
    mid = (left + right) // 2
    if temp_log[mid] == target:
        print(f"Temperature {target} found at index {mid}")
        break
    elif temp_log[mid] < target:
        left = mid + 1
    else:
        right = mid - 1

# Bubble Sort: Sort sensor readings
sensor_data = [25, 22, 27, 21, 26]
for i in range(len(sensor_data)):
    for j in range(len(sensor_data) - i - 1):
        if sensor_data[j] > sensor_data[j + 1]:
            sensor_data[j], sensor_data[j + 1] = sensor_data[j + 1], sensor_data[j]
print(f"Sorted temperatures: {sensor_data}")  # [21, 22, 25, 26, 27]
```

---

## 2. Digital Logic Design

### 🔌 Story Context: Rafi designs digital circuits for his smart home sensors and controllers

### 2.1 Number Systems

#### Binary (Base 2)
- Uses: 0, 1
- Example: 1011₂ = 11₁₀
- Conversion: Sum of powers of 2
- **Smart Home Example**: Representing 8 sensors (on/off)
  ```
  Sensors: Door, Window, Motion, Smoke, Light, Temp, Humidity, Camera
  Binary: 10110101 (means Door=ON, Window=OFF, Motion=ON, etc.)
  ```

#### Decimal (Base 10)
- Uses: 0-9
- Standard number system
- **Example**: Temperature = 25°C, Humidity = 65%

#### Octal (Base 8)
- Uses: 0-7
- Example: 13₈ = 11₁₀
- **Conversion Example**:
  ```
  Binary 11011₂ → Group by 3: 011 011 → Octal: 33₈
  Decimal 27 → 33₈
  ```

#### Hexadecimal (Base 16)
- Uses: 0-9, A-F (A=10, B=11, C=12, D=13, E=14, F=15)
- Example: B₁₆ = 11₁₀
- **Smart Home Example**: Device IDs
  ```
  Device MAC Address: A4:5E:60:F2:1C:3B
  Color Code: #FF5733 (Red=FF, Green=57, Blue=33)
  ```
- **Conversion Example**:
  ```
  Binary 11111111₂ → Hex: FF₁₆ → Decimal: 255₁₀
  This represents maximum brightness (255) for LED
  ```

#### Complements
- **1's Complement**: Invert all bits (0→1, 1→0)
- **2's Complement**: 1's complement + 1 (used for negative numbers)

**Example**: Temperature difference calculation
```
Current temp: 25°C = 00011001₂
Desired temp: 20°C = 00010100₂
Difference: 25 - 20 = 5°C

Using 2's complement for subtraction:
20 in binary: 00010100
1's complement: 11101011
2's complement: 11101011 + 1 = 11101100

Add: 00011001 + 11101100 = 00000101 = 5°C
```

#### Binary Arithmetic
- Addition: Standard binary addition with carry
- Subtraction: Using 2's complement
- Multiplication: Shift and add
- Division: Shift and subtract

**Smart Home Example**:
```
Sensor Reading Addition:
  1011₂ (11 lux - Room 1)
+ 0110₂ (6 lux - Room 2)
-------
 10001₂ (17 lux total)

Binary Multiplication (Power calculation):
  101₂ (5 devices)
× 011₂ (3 hours)
-------
  101
 101
-------
1111₂ (15 device-hours)
```

### 2.2 Boolean Algebra

#### Basic Laws
- **Identity Law**: A + 0 = A, A · 1 = A
- **Null Law**: A + 1 = 1, A · 0 = 0
- **Idempotent Law**: A + A = A, A · A = A
- **Complement Law**: A + A' = 1, A · A' = 0
- **Commutative Law**: A + B = B + A, A · B = B · A
- **Associative Law**: (A + B) + C = A + (B + C)
- **Distributive Law**: A(B + C) = AB + AC

#### De Morgan's Laws
- (A + B)' = A' · B'
- (A · B)' = A' + B'

#### Karnaugh Maps (K-Maps)
- Used to simplify Boolean expressions
- Groups of 1, 2, 4, 8, 16 cells
- Results in minimal sum-of-products or product-of-sums

**Smart Home Example**: Simplify automatic light control logic
```
Inputs: A=Motion, B=Daylight, C=Manual_Override
Output: Light ON

Truth Table:
A B C | Light
0 0 0 | 0
0 0 1 | 1  (Manual ON)
0 1 0 | 0
0 1 1 | 1  (Manual ON)
1 0 0 | 1  (Motion + Dark)
1 0 1 | 1
1 1 0 | 0  (Motion + Bright - no need)
1 1 1 | 1  (Manual ON)

K-Map simplification:
Light = C + A·B'
(Light ON if Manual Override OR (Motion AND NOT Daylight))
```

### 2.3 Logic Gates

| Gate | Symbol | Boolean | Truth Table Result |
|------|--------|---------|-------------------|
| AND | · | A·B | 1 only if both inputs are 1 |
| OR | + | A+B | 1 if any input is 1 |
| NOT | ' | A' | Inverts the input |
| NAND | ⊼ | (A·B)' | 0 only if both inputs are 1 |
| NOR | ⊽ | (A+B)' | 1 only if both inputs are 0 |
| XOR | ⊕ | A⊕B | 1 if inputs are different |
| XNOR | ⊙ | (A⊕B)' | 1 if inputs are same |

**Universal Gates**: NAND and NOR (can implement any logic function)

**Smart Home Circuit Examples**:
```
1. Door Lock System (AND gate):
   Password_Correct AND Fingerprint_Match → Door_Unlock
   1 AND 1 = 1 (unlocked)

2. Alert System (OR gate):
   Smoke_Detected OR Gas_Leak → Sound_Alarm
   1 OR 0 = 1 (alarm ON)

3. Motion Sensor (NOT gate):
   NOT Daylight → Enable_Motion_Sensor
   NOT 0 = 1 (sensor enabled at night)

4. Safety Override (NAND gate):
   NOT(Door_Open AND AC_Running) → Safety_OK
   Prevents AC when door is open

5. Exclusive Mode (XOR gate):
   Heating XOR Cooling → System_Active
   Can't run both simultaneously
```

### 2.4 Combinational Circuits

#### Multiplexer (MUX)
- Many inputs → one output
- Selection lines choose which input passes through
- 2:1, 4:1, 8:1, 16:1 MUX

**Smart Home Example**: 4:1 MUX to select which sensor to display
```
Inputs: I0=Temperature, I1=Humidity, I2=Light, I3=Motion
Select: S1 S0
        0  0 → Display Temperature
        0  1 → Display Humidity
        1  0 → Display Light level
        1  1 → Display Motion status

If S1=0, S0=1, Output shows Humidity reading
```

#### Demultiplexer (DEMUX)
- One input → many outputs
- Selection lines choose which output receives input

**Smart Home Example**: 1:4 DEMUX to control different rooms
```
Input: Central command signal
Select: S1 S0
        0  0 → Control Room 1
        0  1 → Control Room 2
        1  0 → Control Room 3
        1  1 → Control Room 4

One controller sends commands to selected room
```

#### Encoder
- 2ⁿ inputs → n outputs
- Converts decimal to binary

#### Decoder
- n inputs → 2ⁿ outputs
- Converts binary to decimal

#### Adders
- **Half Adder**: Adds 2 bits (Sum, Carry)
- **Full Adder**: Adds 3 bits (2 inputs + carry in)
- **Ripple Carry Adder**: Chain of full adders

**Smart Home Example**: Energy consumption counter
```
Half Adder (2 sensors):
A B | Sum Carry
0 0 |  0    0
0 1 |  1    0
1 0 |  1    0
1 1 |  0    1   (Both sensors active)

Full Adder (3 sensors with previous carry):
A B Cin | Sum Cout
1 1  1  |  1   1   (All three active: Sum=1, Carry=1)

Use case: Counting total active devices
Device1=1, Device2=1, Device3=1, Device4=1
4-bit addition using full adders → Total = 4 devices ON
```

#### Subtractors
- **Half Subtractor**: Subtracts 2 bits
- **Full Subtractor**: Subtracts with borrow

#### Comparator
- Compares two binary numbers
- Outputs: A>B, A=B, A<B

### 2.5 Sequential Circuits

#### Flip-Flops
- **SR Flip-Flop**: Set-Reset (invalid state when S=R=1)
- **JK Flip-Flop**: Improved SR (J=K=1 toggles)
- **D Flip-Flop**: Data (output follows input on clock)
- **T Flip-Flop**: Toggle (toggles on T=1)

**Smart Home Examples**:

```
1. D Flip-Flop - Store last command:
   D=1 (Turn ON), Clock pulse → Q=1 (Device stays ON)
   Stores the state until next clock pulse

2. T Flip-Flop - Toggle switch:
   T=1, Clock → Light toggles (ON→OFF or OFF→ON)
   Used for: Press button to toggle devices

3. JK Flip-Flop - Smart control:
   J=1, K=0 → Set (Device ON)
   J=0, K=1 → Reset (Device OFF)
   J=1, K=1 → Toggle
   J=0, K=0 → No change (maintain current state)
```

#### Registers
- Group of flip-flops
- Store multiple bits
- **Shift Registers**: SISO, SIPO, PISO, PIPO

#### Counters
- **Asynchronous**: Ripple counter (clock not simultaneous)
- **Synchronous**: All flip-flops clocked together
- **Up Counter**: Counts upward
- **Down Counter**: Counts downward
- **Ring Counter**: Output circulates
- **Modulo-N Counter**: Counts from 0 to N-1

**Smart Home Example**: 4-bit Up Counter for visitor counting
```
Clock Pulse | Counter Output (Q3 Q2 Q1 Q0) | Decimal
     0      |      0  0  0  0              |    0
     1      |      0  0  0  1              |    1 (1 visitor)
     2      |      0  0  1  0              |    2 (2 visitors)
     3      |      0  0  1  1              |    3
     ...
     15     |      1  1  1  1              |   15 (max)
     16     |      0  0  0  0              |    0 (reset)

Modulo-10 Counter for decimal display (0-9 visitors on screen)
Modulo-60 Counter for timer (0-59 seconds)
```

---

## 3. Communication Theory

### 📡 Story Context: Rafi implements wireless communication between smart home devices

### 3.1 Analog Communication

#### Amplitude Modulation (AM)
- Varies amplitude of carrier wave
- **Modulation Index**: m = Am/Ac (0 to 1)
- **Bandwidth**: BW = 2fm (fm = max frequency of message)
- Applications: AM radio

**Smart Home Example**: Wireless sensor using AM
```
Carrier frequency (fc) = 2.4 GHz (Wi-Fi frequency)
Message signal (temperature data) fm = 1 kHz

Modulation Index m = 0.8 (good quality)
Bandwidth = 2 × 1 kHz = 2 kHz

If carrier amplitude = 5V, message amplitude = 4V
m = 4/5 = 0.8 ✓
```

#### Frequency Modulation (FM)
- Varies frequency of carrier wave
- **Frequency Deviation**: Δf
- **Modulation Index**: β = Δf/fm
- **Bandwidth**: BW = 2(Δf + fm) (Carson's rule)
- Advantages: Better noise immunity than AM
- Applications: FM radio, TV audio

**Smart Home Example**: Bluetooth communication
```
Carrier frequency = 2.4 GHz
Message frequency fm = 3 kHz (voice command)
Frequency deviation Δf = 75 kHz

Modulation Index β = 75 kHz / 3 kHz = 25
Bandwidth = 2(75 + 3) = 156 kHz

Better for smart home: Less affected by electrical noise from appliances
```

#### Phase Modulation (PM)
- Varies phase of carrier wave
- Similar to FM
- **Modulation Index**: β = kp·Am

### 3.2 Digital Communication

#### Pulse Code Modulation (PCM)
- **Sampling**: Sample analog signal at Nyquist rate (≥2fm)
- **Quantization**: Convert samples to discrete levels
- **Encoding**: Convert to binary
- Steps: Sampling → Quantization → Encoding

**Smart Home Example**: Digitizing voice commands
```
Human voice frequency range: 300 Hz - 3400 Hz
Max frequency fm = 3400 Hz

Nyquist rate = 2 × 3400 = 6800 Hz
Practical sampling rate fs = 8000 Hz (standard)

Quantization levels = 256 (8-bit encoding)
Bit rate = 8000 samples/sec × 8 bits = 64 kbps

Example samples of temperature sensor:
Analog: 24.7°C, 25.1°C, 24.9°C, 25.3°C
Quantized (to nearest 0.5°C): 24.5, 25.0, 25.0, 25.5
Binary: 11001, 11010, 11010, 11011
```

#### Digital Modulation
- **ASK (Amplitude Shift Keying)**: Varies amplitude for 0 and 1
- **FSK (Frequency Shift Keying)**: Different frequencies for 0 and 1
- **PSK (Phase Shift Keying)**: Different phases for 0 and 1
- **QAM (Quadrature Amplitude Modulation)**: Varies both amplitude and phase

**Smart Home Example**: Sending device status wirelessly
```
Data to send: 1011 (Light=ON, Fan=OFF, AC=ON, Door=ON)

ASK:
  Bit 1 → High amplitude (5V)
  Bit 0 → Low amplitude (0V)

FSK:
  Bit 1 → Frequency f1 = 2400 MHz
  Bit 0 → Frequency f2 = 2450 MHz

PSK:
  Bit 1 → Phase = 180°
  Bit 0 → Phase = 0°
```

#### Sampling Theorem (Nyquist Theorem)
- **Sampling Rate**: fs ≥ 2fm
- **Nyquist Rate**: Minimum sampling rate = 2fm
- **Aliasing**: Occurs when fs < 2fm

**Example**: Motion sensor sampling
```
Motion detection frequency: 10 Hz (fast movements)
Minimum sampling rate = 2 × 10 = 20 samples/second
Practical rate = 25 samples/second (safety margin)

If fs = 15 Hz < 20 Hz → Aliasing occurs (missed movements)
```

### 3.3 Signal Processing

#### Fourier Transform
- Converts time domain → frequency domain
- Shows frequency components of signal

#### Signal-to-Noise Ratio (SNR)
- SNR (dB) = 10 log₁₀(Signal Power/Noise Power)
- Higher SNR = better quality

#### Bandwidth
- Range of frequencies in signal
- **Baseband**: 0 to fm
- **Passband**: fc - fm to fc + fm

#### Shannon's Theorem
- **Channel Capacity**: C = B log₂(1 + SNR)
- C = maximum data rate (bps)
- B = bandwidth (Hz)
- SNR = signal-to-noise ratio

**Smart Home Example**: Wi-Fi channel capacity
```
Wi-Fi bandwidth B = 20 MHz
Signal power = 100 mW
Noise power = 1 mW
SNR = 100/1 = 100 (= 20 dB)

Channel Capacity C = 20 × 10⁶ × log₂(1 + 100)
                   = 20 × 10⁶ × log₂(101)
                   = 20 × 10⁶ × 6.66
                   = 133.2 Mbps (theoretical max)

Practical throughput: ~70-100 Mbps (due to protocol overhead)

If noise increases (SNR drops to 50):
C = 20 × 10⁶ × log₂(51) = 113.5 Mbps (reduced capacity)
```

### 3.4 Transmission Media

#### Guided Media
- **Twisted Pair Cable**
  - UTP (Unshielded) and STP (Shielded)
  - Categories: Cat5, Cat5e, Cat6, Cat7
  - Uses: Telephone, Ethernet
  - **Smart Home**: Cat6 cable for wired cameras
    - Speed: 1 Gbps
    - Distance: Up to 100 meters
    - Example: Connecting 8 security cameras to NVR

- **Coaxial Cable**
  - Better shielding than twisted pair
  - Uses: Cable TV, internet
  - **Smart Home**: Cable TV distribution to multiple rooms

- **Fiber Optic Cable**
  - Light transmission
  - Types: Single-mode, Multi-mode
  - Advantages: High bandwidth, no EMI, long distance
  - Uses: High-speed internet, backbone networks
  - **Smart Home**: Fiber to home (FTTH)
    - Speed: 1 Gbps - 10 Gbps
    - Perfect for: Streaming 4K, cloud storage, multiple devices
#### Impairments
- **Attenuation**: Signal strength decreases with distance
- **Distortion**: Signal shape changes
- **Noise**: Unwanted signals (thermal, crosstalk, impulse)

---

## 4. Computer Architecture and Microprocessors

### 4.1 Computer Organization

#### Von Neumann Architecture
- **Components**: CPU, Memory, I/O
- **Stored Program Concept**: Instructions and data in same memory
- **Single bus**: Data and instructions share same path
- **Sequential Execution**: One instruction at a time

#### Harvard Architecture
- **Separate Memory**: Instructions and data in different memory
- **Separate Buses**: Parallel access to instructions and data
- **Faster**: Can fetch instruction and data simultaneously

#### CPU Components
- **ALU (Arithmetic Logic Unit)**: Performs arithmetic and logical operations
- **Control Unit**: Coordinates operations, fetches instructions
- **Registers**: Fast temporary storage
  - **PC (Program Counter)**: Address of next instruction
  - **IR (Instruction Register)**: Current instruction
  - **MAR (Memory Address Register)**: Memory address to access
  - **MDR (Memory Data Register)**: Data to read/write
  - **Accumulator**: Stores intermediate results

#### Instruction Cycle
1. **Fetch**: Get instruction from memory
2. **Decode**: Interpret instruction
3. **Execute**: Perform operation
4. **Store**: Write result

### 4.2 Memory Hierarchy

#### Levels (Fastest to Slowest)
1. **Registers**: Inside CPU, fastest, smallest
2. **Cache**: L1 (fastest), L2, L3
3. **Main Memory (RAM)**: Larger, slower than cache
4. **Secondary Storage**: HDD, SSD (persistent)
5. **Tertiary Storage**: Tape, optical disks

**Smart Home Example**: Home automation controller
```
Registers (32 bytes):
  - Current sensor reading: temperature = 25
  - Access time: 1 nanosecond

L1 Cache (64 KB):
  - Frequently used device states
  - Access time: 2-4 nanoseconds

L2 Cache (256 KB):
  - Recent sensor history
  - Access time: 10-20 nanoseconds

RAM (4 GB):
  - All device configurations
  - Running programs
  - Access time: 100 nanoseconds

SSD (256 GB):
  - Historical data logs
  - Access time: 0.1 milliseconds

Speed comparison:
Register to RAM = 100x slower
Register to SSD = 100,000x slower!
```

#### Memory Types
- **RAM (Random Access Memory)**
  - **SRAM**: Static, faster, expensive (cache)
  - **DRAM**: Dynamic, slower, cheaper (main memory)
  - Volatile: Loses data when power off

- **ROM (Read-Only Memory)**
  - **PROM**: Programmable once
  - **EPROM**: Erasable with UV light
  - **EEPROM**: Electrically erasable
  - Non-volatile: Retains data

#### Cache Memory
- **Mapping Techniques**
  - **Direct Mapping**: Each block has one possible location
  - **Associative Mapping**: Block can go anywhere
  - **Set-Associative Mapping**: Combination of both

- **Replacement Policies**
  - **LRU (Least Recently Used)**
  - **FIFO (First In First Out)**
  - **LFU (Least Frequently Used)**

**Smart Home Example**: Caching device states
```
Cache size: 4 blocks
Devices: Light1, Light2, Fan, AC, TV, Heater (6 devices)

Direct Mapping:
  Block 0: Light1 (address 0, 4)
  Block 1: Light2 (address 1, 5)
  Block 2: Fan (address 2)
  Block 3: AC (address 3)
  Conflict: TV (address 4) replaces Light1 in Block 0

LRU Replacement:
  Recently used: AC (5 sec ago), Fan (10 sec), Light1 (30 sec), TV (60 sec)
  If cache full and need Heater → Replace TV (least recently used)

Cache Hit: Request Light1 → Found in cache (fast, 2ns)
Cache Miss: Request Heater → Not in cache, fetch from RAM (100ns)

Hit Rate = Hits / Total Requests
If 8 hits out of 10 requests = 80% hit rate (good performance)
```
- **Byte (B)**: 8 bits
- **Kilobyte (KB)**: 1024 bytes = 2¹⁰ bytes
- **Megabyte (MB)**: 1024 KB = 2²⁰ bytes ≈ 1 million bytes
- **Gigabyte (GB)**: 1024 MB = 2³⁰ bytes ≈ 1 billion bytes
- **Terabyte (TB)**: 1024 GB = 2⁴⁰ bytes
- **Petabyte (PB)**: 1024 TB = 2⁵⁰ bytes

**Smart Home Data Storage Examples**:
```
1 Temperature Reading:
   - Value (2 bytes): 25°C stored as 0x0019
   - Total: 2 bytes

1 Hour of readings (every minute = 60 readings):
   - 60 × 2 bytes = 120 bytes

1 Day (24 hours):
   - 24 × 120 = 2,880 bytes ≈ 2.8 KB

1 Month (30 days):
   - 30 × 2.8 KB = 84 KB

1 Year:
   - 365 × 2.8 KB = 1,022 KB ≈ 1 MB

Security Camera (1080p, H.264):
   - Bitrate: 4 Mbps = 0.5 MB/second
   - 1 hour: 0.5 × 60 × 60 = 1,800 MB = 1.76 GB
   - 24 hours: 42.2 GB/day
   - 1 month: 1.27 TB (need large storage!)

Smart Home Hub Memory:
   - Program code: 512 KB
   - Device states: 10 KB
   - Logs (7 days): 2 MB
   - Total RAM needed: ~4 MB minimum
```

### 4.4 Instruction Set Architecture

#### RISC vs CISC

| Feature | RISC | CISC |
|---------|------|------|
| Instructions | Simple, fixed length | Complex, variable length |
| Cycles | One per instruction | Multiple per instruction |
| Registers | Many registers | Few registers |
| Addressing Modes | Few | Many |
| Examples | ARM, MIPS | x86, 8086 |

#### Addressing Modes
- **Immediate**: Operand in instruction itself
- **Direct**: Address of operand in instruction
- **Indirect**: Instruction has address of address
- **Register**: Operand in register
- **Register Indirect**: Register contains address
- **Indexed**: Base + Index
- **Relative**: PC + Offset

### 4.5 8085 Microprocessor

#### Features
- 8-bit processor
- 16-bit address bus (64 KB memory)
- 8-bit data bus
- Clock: 3 MHz
- 40-pin DIP package

#### Registers
- **Accumulator (A)**: 8-bit, main register for operations
- **Flags**: Sign, Zero, Auxiliary Carry, Parity, Carry
- **General Purpose**: B, C, D, E, H, L (8-bit)
- **Program Counter (PC)**: 16-bit
- **Stack Pointer (SP)**: 16-bit

#### Pin Diagram
- **AD0-AD7**: Multiplexed address/data bus
- **A8-A15**: Upper address bus
- **ALE**: Address Latch Enable
- **RD, WR**: Read/Write control
- **IO/M**: I/O or Memory operation
- **RESET**: Reset processor
- **CLK**: Clock input
- **INTR, INTA**: Interrupt request/acknowledge

#### Instruction Set
- **Data Transfer**: MOV, MVI, LDA, STA, LHLD, SHLD
- **Arithmetic**: ADD, SUB, INR, DCR, DAD
- **Logical**: ANA, ORA, XRA, CMP, CMA
- **Branch**: JMP, JZ, JNZ, JC, JNC, CALL, RET
- **Stack**: PUSH, POP
- **Machine Control**: HLT, NOP, EI, DI

**Smart Home Example**: Temperature control program (8085 Assembly)
```assembly
; Read temperature sensor and control heater
MVI A, 00H        ; Clear accumulator
IN 10H            ; Read temperature from port 10H (e.g., 18°C)
MVI B, 20H        ; Load desired temp (20°C) into B
CMP B             ; Compare current with desired
JNC TURN_OFF      ; If current >= desired, turn off heater

; Turn ON heater
MVI A, 01H        ; Load 1 (ON signal)
OUT 20H           ; Send to heater port
JMP END

TURN_OFF:
MVI A, 00H        ; Load 0 (OFF signal)
OUT 20H           ; Send to heater port

END:
HLT               ; Stop program

; Another example: Count active devices
LXI H, 3000H      ; Load address of device states
MVI C, 00H        ; Counter = 0
MVI B, 08H        ; 8 devices to check

LOOP:
MOV A, M          ; Get device state
CPI 01H           ; Compare with 1 (ON)
JNZ SKIP          ; If not ON, skip
INR C             ; Increment counter

SKIP:
INX H             ; Next device
DCR B             ; Decrement device count
JNZ LOOP          ; If not zero, continue

MOV A, C          ; Move count to accumulator
OUT 30H           ; Display count
HLT
```

#### Interrupts
- **TRAP**: Non-maskable, highest priority
- **RST 7.5, 6.5, 5.5**: Maskable, vectored
- **INTR**: Maskable, non-vectored

**Smart Home Example**: Emergency handling
```
Normal operation: Monitor temperature

TRAP (Priority 1):
  - Fire alarm detected!
  - Cannot be disabled
  - Immediately execute fire safety routine
  - Action: Turn off gas, unlock doors, call fire dept

RST 7.5 (Priority 2):
  - Smoke sensor alert
  - Can be masked if in maintenance mode
  - Action: Turn on exhaust fan, send notification

RST 6.5 (Priority 3):
  - Door sensor - unauthorized entry
  - Action: Sound alarm, capture image, notify owner

RST 5.5 (Priority 4):
  - Low battery warning
  - Action: Send notification to replace batteries

INTR (Priority 5):
  - Regular sensor readings
  - Action: Store temperature, humidity data

Interrupt Priority Order:
TRAP > RST 7.5 > RST 6.5 > RST 5.5 > INTR

Scenario:
  System monitoring temperature (normal task)
  → Smoke detected (RST 7.5) → Interrupt, handle smoke
  → While handling smoke, TRAP (fire) occurs
  → Preempt smoke handler, execute fire routine (highest priority!)
```

### 4.6 8086 Microprocessor
- 16-bit processor
- 20-bit address bus (1 MB memory)
- 16-bit data bus
- **Segmentation**: CS, DS, SS, ES
- **Pipelining**: Fetch and execute overlap
- **Two units**: BIU (Bus Interface Unit), EU (Execution Unit)

---

## 5. Computer Networks

### 🌐 Story Context: Rafi connects all smart home devices to a home network and the internet

### 5.1 OSI Model (7 Layers)

| Layer | Name | Function | Protocols/Devices |
|-------|------|----------|-------------------|
| 7 | Application | User interface | HTTP, FTP, SMTP, DNS |
| 6 | Presentation | Data format, encryption | SSL/TLS, JPEG, ASCII |
| 5 | Session | Manages connections | NetBIOS, RPC |
| 4 | Transport | End-to-end delivery | TCP, UDP |
| 3 | Network | Routing, IP addressing | IP, ICMP, ARP, Router |
| 2 | Data Link | Frame, MAC addressing | Ethernet, PPP, Switch, Bridge |
| 1 | Physical | Bits, physical medium | Cables, Hub, Repeater |

### 5.2 TCP/IP Model (4 Layers)
1. **Application**: Combines OSI layers 5, 6, 7
2. **Transport**: TCP, UDP
3. **Internet**: IP, ICMP, ARP
4. **Network Access**: Combines OSI layers 1, 2

**Smart Home Data Flow Example**:
```
Scenario: Phone app turns on bedroom light

Layer 7 (Application):
  - App sends HTTP POST request
  - URL: http://192.168.1.50/light/bedroom/on

Layer 6 (Presentation):
  - Encrypt data with TLS (HTTPS)
  - Convert JSON: {"device":"light", "action":"on"}

Layer 5 (Session):
  - Establish session with smart hub
  - Maintain connection for multiple commands

Layer 4 (Transport):
  - Use TCP port 80 (HTTP) or 443 (HTTPS)
  - Break data into segments
  - Add source port: 45678, destination port: 80

Layer 3 (Network):
  - Add IP header
  - Source IP: 192.168.1.100 (phone)
  - Destination IP: 192.168.1.50 (hub)
  - Router determines path

Layer 2 (Data Link):
  - Add frame header
  - Source MAC: A1:B2:C3:D4:E5:F6 (phone)
  - Dest MAC: 11:22:33:44:55:66 (hub)
  - Switch forwards based on MAC

Layer 1 (Physical):
  - Convert to electrical signals (Wi-Fi)
  - Transmit at 2.4 GHz or 5 GHz
  - Bitrate: 100 Mbps
```

### 5.3 Network Devices

#### Hub
- Layer 1 device
- Broadcasts to all ports
- No intelligence
- Creates collisions
- **Example**: Rarely used in modern smart homes (inefficient)

#### Switch
- Layer 2 device
- Forwards based on MAC address
- Creates separate collision domains
- Learns MAC addresses
- **Smart Home Example**: 8-port Gigabit switch
  ```
  MAC Table:
  Port 1: A1:B2:C3:D4:E5:F6 (Smart Hub)
  Port 2: 11:22:33:44:55:66 (Security Camera 1)
  Port 3: AA:BB:CC:DD:EE:FF (Security Camera 2)
  Port 4: 12:34:56:78:90:AB (NAS Storage)

  Data from Camera 1 to Hub:
  Switch checks MAC table → Forwards only to Port 1 (efficient!)
  ```

#### Router
- Layer 3 device
- Forwards based on IP address
- Connects different networks
- Creates separate broadcast domains
- **Smart Home Example**: Home router
  ```
  WAN (Internet): 203.190.242.15 (public IP)
  LAN (Home): 192.168.1.0/24 (private IPs)

  Routing Table:
  192.168.1.0/24 → Local network (Wi-Fi/Ethernet)
  0.0.0.0/0 → Default gateway (Internet)

  NAT (Network Address Translation):
  Translates private IPs to public IP for internet access
  192.168.1.100:45678 → 203.190.242.15:45678
  ```

#### Bridge

- Layer 2 device
- Connects two LAN segments
- Filters traffic based on MAC

#### Gateway

- All layers
- Protocol converter
- Connects different network architectures

#### Repeater

- Layer 1 device
- Regenerates signal
- Extends network distance

### 5.4 Network Protocols

#### Application Layer

- **HTTP (Port 80)**: Web browsing
- **HTTPS (Port 443)**: Secure web
- **FTP (Port 20, 21)**: File transfer
- **SMTP (Port 25)**: Send email
- **POP3 (Port 110)**: Receive email
- **IMAP (Port 143)**: Email management
- **DNS (Port 53)**: Domain name resolution
- **DHCP (Port 67, 68)**: Automatic IP configuration
- **SSH (Port 22)**: Secure shell
- **Telnet (Port 23)**: Remote login

#### Transport Layer

- **TCP (Transmission Control Protocol)**
  - Connection-oriented
  - Reliable (acknowledgment, retransmission)
  - Flow control, congestion control
  - Three-way handshake: SYN → SYN-ACK → ACK
  - Uses: HTTP, FTP, SMTP

- **UDP (User Datagram Protocol)**
  - Connectionless
  - Unreliable (no acknowledgment)
  - Faster than TCP
  - Uses: DNS, DHCP, VoIP, streaming

#### Network Layer

- **IP (Internet Protocol)**
  - Addressing and routing
  - IPv4: 32-bit (4 octets)
  - IPv6: 128-bit (8 groups of 4 hex digits)

- **ICMP (Internet Control Message Protocol)**
  - Error reporting and diagnostics
  - Ping, Traceroute

- **ARP (Address Resolution Protocol)**
  - IP address → MAC address

- **RARP (Reverse ARP)**
  - MAC address → IP address

#### Data Link Layer

- **Ethernet**: LAN protocol
- **PPP (Point-to-Point Protocol)**: WAN connections
- **HDLC**: Synchronous data link

### 5.5 IP Addressing

#### IPv4

- **Format**: xxx.xxx.xxx.xxx (0-255 each)
- **Total**: 2³² = ~4.3 billion addresses

**Classes**:
| Class | Range | Default Mask | Network/Host Bits | Use |
|-------|-------|--------------|-------------------|-----|
| A | 1-126 | 255.0.0.0 (/8) | 8/24 | Large networks |
| B | 128-191 | 255.255.0.0 (/16) | 16/16 | Medium networks |
| C | 192-223 | 255.255.255.0 (/24) | 24/8 | Small networks |
| D | 224-239 | - | - | Multicast |
| E | 240-255 | - | - | Experimental |

**Special Addresses**:
- **127.0.0.1**: Loopback (localhost)
- **0.0.0.0**: Default route
- **255.255.255.255**: Broadcast

**Private IP Ranges**:
- Class A: 10.0.0.0 - 10.255.255.255
- Class B: 172.16.0.0 - 172.31.255.255
- Class C: 192.168.0.0 - 192.168.255.255

#### Subnetting

- **Subnet Mask**: Divides IP into network and host portions
- **CIDR Notation**: /24 means first 24 bits are network
- **Number of Subnets**: 2ⁿ (n = borrowed bits)
- **Hosts per Subnet**: 2ʰ - 2 (h = host bits, -2 for network and broadcast)

#### IPv6

- **Format**: 8 groups of 4 hex digits (xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx)
- **Total**: 2¹²⁸ addresses
- **Benefits**: More addresses, better security, no NAT needed

### 5.6 Network Topologies

- **Bus**: Single cable, all devices connected
  - Cheap, easy to install
  - Single point of failure
  - **Example**: Old Ethernet (10BASE2) - rarely used now

- **Star**: Central hub/switch, devices radiate
  - Easy to add/remove devices
  - Hub failure = network down
  - **Smart Home Example**: Most common
    ```
    Central Router/Switch
         |
    +----+----+----+----+
    |    |    |    |    |
   Cam1 Cam2 Hub  NAS  AP
    ```

- **Ring**: Circular connection
  - Equal access for all
  - Break in ring = network down
  - **Example**: Token Ring networks (obsolete)

- **Mesh**: Every device connected to every other
  - **Full Mesh**: All connected
  - **Partial Mesh**: Some connected
  - Redundant, reliable
  - Expensive
  - **Smart Home Example**: Zigbee mesh network
    ```
    Smart bulbs form mesh:
    Bulb1 ↔ Bulb2 ↔ Bulb3
      ↔      X      ↔
    Bulb4 ↔ Bulb5 ↔ Hub

    If Bulb2 fails, message routes through alternate path
    Hub → Bulb5 → Bulb1 → Bulb3 (still reaches destination!)
    ```

- **Tree**: Hierarchical
  - Scalable
  - Centralized management

- **Hybrid**: Combination of topologies
  - **Smart Home Example**: Star + Mesh
    ```
    Main Router (Star center)
         |
    +----+----+
    |    |    |
   WiFi Zigbee Z-Wave
   (Star) (Mesh) (Mesh)
    ```
- **MAN (Metropolitan Area Network)**: City (Cable TV)
- **WAN (Wide Area Network)**: Country/world (Internet)

### 5.8 Network Security

#### Threats

- **Malware**: Virus, worm, trojan, ransomware
- **Phishing**: Fake emails/websites
- **DDoS (Distributed Denial of Service)**: Overwhelm server
- **Man-in-the-Middle**: Intercept communication
- **SQL Injection**: Database attack
- **Brute Force**: Password guessing

#### Security Measures

- **Firewall**: Filters traffic
- **Encryption**: Scramble data (AES, RSA)
- **VPN (Virtual Private Network)**: Secure tunnel
- **IDS/IPS**: Intrusion Detection/Prevention
- **Authentication**: Username/password, 2FA
- **SSL/TLS**: Secure web communication
- **Antivirus**: Detect malware

---

## 6. Electronic Devices

### 6.1 Semiconductor Physics

#### Intrinsic Semiconductor

- Pure semiconductor (Si, Ge)
- Equal electrons and holes
- Conductivity increases with temperature

#### Extrinsic Semiconductor

- **N-type**: Doped with donor atoms (P, As, Sb)
  - Extra electrons (majority carriers)
  - Holes (minority carriers)

- **P-type**: Doped with acceptor atoms (B, Al, Ga)
  - Extra holes (majority carriers)
  - Electrons (minority carriers)

#### PN Junction Diode

- **Forward Bias**: P connected to positive, N to negative
  - Current flows (low resistance)
  - Barrier potential decreases

- **Reverse Bias**: P connected to negative, N to positive
  - Minimal current (high resistance)
  - Barrier potential increases

- **Breakdown**: Reverse voltage exceeds limit
  - **Zener Breakdown**: Heavily doped, low voltage
  - **Avalanche Breakdown**: Lightly doped, high voltage

#### V-I Characteristics

- Forward: Current increases exponentially after threshold (~0.7V for Si)
- Reverse: Small leakage current until breakdown

### 6.2 Special Purpose Diodes

#### Zener Diode

- Operates in reverse breakdown
- **Voltage Regulation**: Maintains constant voltage
- Zener voltage: Vz (e.g., 5V, 12V)

#### LED (Light Emitting Diode)

- Emits light when forward biased
- Colors: Red, green, blue, etc.
- Forward voltage: ~1.8-3.3V

#### Photodiode

- Generates current when exposed to light
- Reverse biased
- Uses: Light sensors, optical communication

#### Schottky Diode

- Metal-semiconductor junction
- Fast switching
- Low forward voltage drop

#### Varactor Diode

- Variable capacitance with voltage
- Uses: Tuning circuits, FM radios

### 6.3 Bipolar Junction Transistor (BJT)

#### Types

- **NPN**: Emitter (N) - Base (P) - Collector (N)
  - Electrons are majority carriers

- **PNP**: Emitter (P) - Base (N) - Collector (P)
  - Holes are majority carriers

#### Regions of Operation

- **Active**: BE forward biased, BC reverse biased (amplification)
- **Saturation**: Both junctions forward biased (switch ON)
- **Cutoff**: Both junctions reverse biased (switch OFF)
- **Inverted**: BE reverse biased, BC forward biased (rarely used)

#### Parameters

- **α (Alpha)**: Ic/Ie (common base current gain) ≈ 0.95-0.99
- **β (Beta)**: Ic/Ib (common emitter current gain) = 20-200
- **Relationship**: β = α/(1-α), α = β/(1+β)
- **Ie = Ib + Ic**

#### Configurations

- **Common Emitter (CE)**
  - High voltage and current gain
  - 180° phase shift
  - Most common

- **Common Base (CB)**
  - High voltage gain, no current gain
  - No phase shift
  - High frequency applications

- **Common Collector (CC)** (Emitter Follower)
  - High current gain, no voltage gain
  - No phase shift
  - Impedance matching

### 6.4 Field Effect Transistor (FET)

#### JFET (Junction FET)

- **N-channel**: Current flows through N-type channel
- **P-channel**: Current flows through P-type channel
- Terminals: Source, Drain, Gate
- Voltage-controlled device (high input impedance)
- **Parameters**:
  - **IDSS**: Drain current when VGS = 0
  - **VP (Pinch-off voltage)**: VGS when ID = 0

#### MOSFET (Metal-Oxide-Semiconductor FET)

- **Depletion Mode**: Normally ON, apply voltage to turn OFF
- **Enhancement Mode**: Normally OFF, apply voltage to turn ON
- **N-channel** and **P-channel** types
- Higher input impedance than JFET
- Uses: Digital circuits, power electronics

### 6.5 Operational Amplifier (Op-Amp)

#### Characteristics

- Very high gain (10⁵ - 10⁶)
- Very high input impedance (MΩ)
- Very low output impedance (Ω)
- Two inputs: Inverting (-), Non-inverting (+)
- Output: Vout = A(V+ - V-)

#### Ideal Op-Amp

- Infinite gain
- Infinite input impedance
- Zero output impedance
- Infinite bandwidth
- Zero offset voltage

#### Configurations

**Inverting Amplifier**:

- Gain: Av = -Rf/Rin
- 180° phase shift

**Non-Inverting Amplifier**:

- Gain: Av = 1 + Rf/Rin
- No phase shift

**Voltage Follower** (Buffer):

- Gain: Av = 1
- High input impedance, low output impedance

**Summing Amplifier**:

- Vout = -(V1 + V2 + V3)
- Adds multiple inputs

**Difference Amplifier**:

- Vout = Rf/Rin (V2 - V1)
- Subtracts inputs

**Integrator**:

- Output is integral of input
- Uses capacitor in feedback

**Differentiator**:

- Output is derivative of input
- Uses capacitor at input

**Comparator**:

- Compares two voltages
- Output: High or Low

### 6.6 Power Electronics

#### Rectifiers

- Convert AC to DC

**Half-Wave Rectifier**:

- One diode
- Efficiency: 40.6%
- Output: Pulsating DC (one half cycle)

**Full-Wave Rectifier**:

- Center-tapped transformer + 2 diodes OR Bridge (4 diodes)
- Efficiency: 81.2%
- Output: Both half cycles

**Bridge Rectifier**:

- 4 diodes in bridge configuration
- No center-tap needed
- Most common

#### Filters

- Smooth pulsating DC
- **Capacitor Filter**: Most common, reduces ripple
- **LC Filter**: Better smoothing
- **π Filter**: Capacitor-Inductor-Capacitor

#### Voltage Regulators

- Maintain constant output voltage
- **Zener Regulator**: Simple, uses Zener diode
- **IC Regulators**: 78xx (positive), 79xx (negative)
  - Example: 7805 (5V), 7812 (12V)

#### DC-DC Converters

- **Buck Converter**: Step down voltage
- **Boost Converter**: Step up voltage
- **Buck-Boost**: Step up or down
- Uses: Switch mode power supplies

#### Thyristors

**SCR (Silicon Controlled Rectifier)**:

- 4-layer PNPN device
- 3 terminals: Anode, Cathode, Gate
- Turns ON with gate pulse
- Turns OFF when current drops below holding current
- Uses: Motor control, dimmer switches

**TRIAC**:

- Bidirectional SCR
- Controls AC power
- 3 terminals: MT1, MT2, Gate
- Uses: AC motor control, light dimmers

**DIAC**:

- Bidirectional diode
- Triggers TRIAC
- Two terminals

**UJT (Unijunction Transistor)**:

- Triggering device
- Relaxation oscillator

---

## Study Tips for 45-Minute Test

### Time Management

- **7-8 minutes per topic**
- Don't spend more than 1 minute per question
- Skip difficult questions, return later
- Review answers if time remains

### High-Priority Topics (Most Frequently Asked)

1. **Programming**:
   - Python data types, operators, functions
   - Error types
   - Time complexity

2. **Digital Logic**:
   - Number system conversions
   - Boolean algebra laws
   - K-map simplification
   - Flip-flops

3. **Communication**:
   - Modulation types (AM, FM)
   - Sampling theorem
   - Channel capacity

4. **Computer Architecture**:
   - 8085 architecture and instructions
   - Memory hierarchy
   - RISC vs CISC

5. **Networks**:
   - OSI model layers
   - TCP vs UDP
   - IP addressing and subnetting
   - Network devices

6. **Electronics**:
   - PN junction characteristics
   - BJT configurations
   - Op-amp circuits
   - Rectifiers

### Quick Revision Points

**Formulas to Remember**:

- Shannon's theorem: C = B log₂(1 + SNR)
- Nyquist rate: fs ≥ 2fm
- BJT: β = Ic/Ib, Ie = Ib + Ic
- Inverting amplifier: Av = -Rf/Rin
- Non-inverting amplifier: Av = 1 + Rf/Rin
- Hosts per subnet: 2ʰ - 2
- Half-wave efficiency: 40.6%
- Full-wave efficiency: 81.2%

**Key Values**:

- 1 KB = 1024 bytes = 2¹⁰ bytes
- 1 MB = 1024 KB = 2²⁰ bytes
- 1 GB = 1024 MB = 2³⁰ bytes
- Si barrier potential: ~0.7V
- Ge barrier potential: ~0.3V
- Class A: 1-126, Mask: 255.0.0.0
- Class B: 128-191, Mask: 255.255.0.0
- Class C: 192-223, Mask: 255.255.255.0

### Final Preparation

1. Practice past year questions daily
2. Create flashcards for quick facts
3. Take timed mock tests weekly
4. Review wrong answers thoroughly
5. Focus on weak areas
6. Get adequate sleep before exam
7. Stay calm and confident

**Good luck with your BUET admission! 🎯**
