- **3 Hours**
- **8 Marks**
# 1 Open/Closed Loop CS Overview
## 1.1 Differences
| **Parameter / Factor**                  | **Open-Loop Control System**                                  | **Closed-Loop Control System**                             |
| --------------------------------------- | ------------------------------------------------------------- | ---------------------------------------------------------- |
| **1. Feedback Path**                    | No feedback path (output is not measured)                     | Feedback path exists (output is measured and compared)     |
| **2. Accuracy**                         | Low accuracy (depends on calibration)                         | High accuracy (due to error correction)                    |
| **3. Stability**                        | Always stable (no feedback to cause oscillations)             | May become unstable if not designed properly               |
| **4. Effect of Disturbances**           | Cannot correct disturbances; output affected directly         | Automatically corrects disturbances using feedback         |
| **5. Complexity**                       | Simple design and low cost                                    | Complex design and higher cost                             |
| **6. Response Time**                    | Faster response (no computation delay for feedback)           | Slower response (feedback computation takes time)          |
| **7. Calibration Required**             | Frequent calibration needed                                   | Less calibration needed (self-correcting)                  |
| **8. Bandwidth**                        | Limited bandwidth                                             | Wider bandwidth possible                                   |
| **9. Sensitivity to Parameter Changes** | Highly sensitive (changes in system parameters affect output) | Less sensitive (feedback reduces sensitivity)              |
| **10. Application Examples**            | Washing machine timer, traffic light, toaster, microwave oven | Temperature control (AC, oven), robot arm, cruise control  |
| **11. Steady-State Error**              | Present and cannot be corrected                               | Can be reduced or eliminated (with integral action)        |
| **12. Transient Response Control**      | Not possible to control transient response                    | Transient response can be shaped (via PID tuning)          |
| **13. Noise Immunity**                  | Less affected by sensor noise (no sensors)                    | More affected by sensor noise (amplified in feedback loop) |
| **14. Power Consumption**               | Generally lower                                               | Higher (due to continuous sensing and computation)         |
| **15. Failure Mode**                    | System continues even if output is wrong                      | System may fail or oscillate if sensor/feedback fails      |
## 1.2 Block Diagrams
### 1.2.1 Diagrams
1. Open Loop
	- ![[Pasted image 20260422162521.png]]
2. Closed Loop
	- ![[Pasted image 20260422162532.png]]
### 1.2.2 Components
- **Reference Inputs**
	- desired value that is required to be observed as an output of the physical system.
	- desired speed, temperature set by the user represent a reference input
- **Controller**:
	- main processing part of the system which computes the input to the plant such that desired output is achieved based on given reference input
- **Actuator**:
	- device that is used to control the input to the plant.
	- motor can be taken as an example of an actuator
- **Plant/Process**:
	- physical system to be controlled
	- automobiles, fan, heater, disk, etc.
- **Disturbances**:
	- undesirable input to the system that may cause the output to deviate from the desired reference input
- **Output**:
	- the aspect or attribute of the physical system that we are about to control
	- speed, temperature can be taken as example.
- **Sensor**:
	- used to sense the output of the system and is fed to the input where error is calculated
- **Error Detector**
	- determines the error being produced in the system
	- error is calculated by determining the difference between the output of the system and the reference input.
# 2 PID Controllers
## 2.1 Control Objectives and Metrics
- Main objective of control system design is to make output track the reference input even in the presence of measurement noise, model error and disturbances.
- Objective fulfillment can be analyzed and assessed through various metrics
	- **Stability**:
		- for the system to be stable, all variables in the system remain obunded.
	- **Performance**:
		- it describes how well the output is tracking the change in the reference input
		- different aspects of performance:
			- *Rise Time* (T$_r$):
				- time required to change from 10% to 90% of its final value.
				- measure of ability of a system to fast input signals.
			- *Peak Time* (T$_P$):
				- time required to reach the first peak of the response
			- *Overshoot* (M$_P$):
				- refers to an output exceeding its final, stead-state value.
				- percentage amount by which the peak of the response exceeds the final value.
			- *Settling Time* (T$_S$)
				- time required for the system to settle down to within 1% of its final value.
	- **Disturbance rejection**:
		- how well the impact of disturbances (undesired effects) can be minimized
	- **Robustness**:
		- The system to be designed must be able to tolerate the modeling error of the plant.
		- the stability and performance of the system should not be significantly affected by the presence of model errors.
## 2.2 Controller Design
| **Parameter / Factor**                 | **P Controller**                                                    | **PI Controller**                                                    | **PD Controller**                                                         | **PID Controller**                                                              |
| -------------------------------------- | ------------------------------------------------------------------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| **1. Stability**                       | Less stable; can oscillate if gain high                             | More stable than P; integral action may reduce phase margin slightly | Improves stability by adding damping                                      | Best stability when tuned properly                                              |
| **2. Rise Time (tᵣ)**                  | Decreases as Kp increases                                           | Decreases (similar to P), but may increase slightly due to integral  | Decreases significantly                                                   | Fastest rise time (Kp + Kd effect)                                              |
| **3. Peak Time (tₚ)**                  | Decreases with higher Kp                                            | Slightly higher than P due to integral lag                           | Lower than P                                                              | Lowest among all (fast response)                                                |
| **4. Maximum Overshoot (Mₚ)**          | Increases with Kp                                                   | Increases more than P if Ki high                                     | Reduces overshoot significantly                                           | Minimal overshoot if well-tuned                                                 |
| **5. Settling Time (tₛ)**              | Moderate; can be long if underdamped                                | Longer than P due to integral windup                                 | Shorter than P                                                            | Shortest settling time (Kd speeds up damping)                                   |
| **6. Steady-State Error (eₛₛ)**        | Non-zero for step input                                             | Zero for step input (type 1 system)                                  | Same as P (non-zero for step)                                             | Zero for step input (type 1 system)                                             |
| **7. Effect of Noise**                 | Low sensitivity                                                     | Low sensitivity                                                      | High sensitivity (amplifies high-frequency noise)                         | High sensitivity (derivative amplifies noise)                                   |
| **8. Integral Windup**                 | Not applicable                                                      | Possible (if actuator saturates)                                     | Not applicable                                                            | Possible (integral term)                                                        |
| **9. Complexity / Tuning**             | Simplest (1 parameter: Kp)                                          | Moderate (2 params: Kp, Ki)                                          | Moderate (2 params: Kp, Kd)                                               | Most complex (3 params: Kp, Ki, Kd)                                             |
| **10. Application Example**            | First-order systems, level control                                  | Speed control, temperature control (eliminate offset)                | Servo motors, fast positioning (no offset correction)                     | Robotics, drones, precision motion control                                      |
| **11. Response to Disturbance**        | Moderate rejection                                                  | Better rejection (integral acts on accumulated error)                | Poor rejection (no integral)                                              | Best rejection (integral + derivative action)                                   |
| **12. Phase Lag / Lead**               | No lag/lead                                                         | Lag (integral adds phase lag)                                        | Lead (derivative adds phase lead)                                         | Lag-lead (balanced)                                                             |
| **13. Type of System Achieved**        | Type 0                                                              | Type 1 (integrator → zero steady-state error)                        | Type 0 (same as P)                                                        | Type 1                                                                          |
| **14. Initial Kick / Derivative Kick** | None                                                                | None                                                                 | Large initial kick if step input                                          | Derivative kick (can be reduced by filtering)                                   |
| **15. Use If**                         | System is simple, overshoot acceptable, stead-state error tolerable | zero steady-state error needed, speed not critical                   | faster response, less overshoot needed, but steady-state error acceptable | fast response, zero steady-state error, minimal overshoot and noise manageable. |
# 3 Software Coding of PID Controller
- PID controller can be implemented using software
- at first, required initialization is done which is followed by reading reference value and sensor value.
- then after that error can be calculted
	- which further is used to compute the output of PID controller
- the refined output is fed to the actuator which in turn controls the plant based on the value of proportional, integral and derivative constant defined in the program.
## 3.1 Algorithm
1. **Initialize** controller gains (Kp, Ki, Kd) and variables (integral = 0, previous_error = 0)
2. **Set** sampling time (Δt)
3. **Repeat** every Δt milliseconds:
    - Read current sensor value (process variable)
    - Calculate error = setpoint − process variable
    - Add to integral: integral = integral + error × Δt
    - Calculate derivative = (error − previous_error) / Δt
    - Compute output = Kp × error + Ki × integral + Kd × derivative
    - Apply output to actuator (motor, heater, etc.)
    - Update previous_error = error
    - Wait for Δt milliseconds
## 3.2 Pseudo Code
```
1.  SET Kp, Ki, Kd
2.  SET integral = 0
3.  SET previous_error = 0
4.  SET dt = sampling_time (e.g., 0.01 seconds)

5.  LOOP forever:
6.      sensor_value = read_sensor()
7.      setpoint = get_target_value()
8.      error = setpoint - sensor_value
9.      integral = integral + error * dt
10.     derivative = (error - previous_error) / dt
11.     output = (Kp * error) + (Ki * integral) + (Kd * derivative)
12.     send_to_actuator(output)
13.     previous_error = error
14.     wait(dt)
15.  END LOOP
```
# 4 PID Tuning
- adjustment of its control parameters to the optimum values for the desired control response.
- quantitative analysis can be used to determine the values of PID
- however, quantitative analysis is not necessary when safety and cost of using plant is not concerned.
- there are various method for PID tuning, one of which ad hoc tuning process.
- the steps are:
	- start with small value of P gain, D and I gains, as 0.
	- increase value of D until oscillation is seen, and then D gain is decremented by a factor of 2 to 4
	- then increase value of P gain until oscillation or excessive overshoot is observed, and then P gain is reduced by a factor of 2 to 4
	- then increase value of I gain and reduce it slightly when oscillation or excessive overshoot is seen
	- above steps are repeated until satisfactory performance is achieved.