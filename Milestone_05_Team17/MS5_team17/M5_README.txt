Final M5 Submission: Autonomous Systems

Please find below the details, instructions, and deliverables for our final M5 submission.

**Project Deliverables**

* **GitHub Repository:** All completed work can be found on our `M5_EKF` branch: [zooba_workspace Repo](https://github.com/a7medm0stafa/zooba_workspace/tree/M5_EKF).
* **Workspace ZIP:** A ZIP file containing the full workspace with all system packages is also provided.

### 1. Simulations

* **EKF Implementation:** The Extended Kalman Filter (EKF) is implemented in the `Localization` package within `ekf_core.py` and `ekf_localization_node.py`.
* **Configuration:** The Process Noise and Sensor Noise (Q and R matrices) are configured using the `ekf_localization.yaml` file.
* **Configuration Note:** The simulation shares the same controller configuration as the hardware but utilizes a different vehicle configuration.
* **Results:** All EKF simulation plots are located in the `M5_simulation_plots` folder on the Drive.

**To launch the EKF simulation, use the following command:**

```bash
ros2 launch zooba_simulation closed_loop_sim_track.launch.py use_ekf:=true track:="track_1 or track_2 or track_3"

```

### 2. Hardware Performance

* **Firmware Implementation:** To minimize noise and latency over serial communication, the EKF was embedded directly into the Arduino 
firmware. Keeping all sensor readings and filtering at the low level allows the Raspberry Pi to receive clean data and dedicate 
its processing power entirely to the heavy load of path planning and control. The updated Arduino code can be found in the `firmware` 
package under `low_level_controller.ino`.
* **Results & Media:** Plots showing how the hardware moves compared to the desired trajectory (determined by the path planner and controller effort) are included in our submission. 
Additionally, hardware demonstration videos can be found in the `M5_hardware_videos` folder on the Drive.

**To launch the hardware execution, use the following command:**

```bash
ros2 launch high_level_controller closed_loop_hw.launch.py track:="desired track" use_planner:=true

```

Finally, we want to say thank you to everyone on the Autonomous Systems teaching team: Dr. Omar, Dalia, Shaaban, Sheshtawy, and Salah.

This course has been an incredibly fun from start to finish. Even though we struggled massively with the hardware, sensor integration, 
and racing against very tight deadlines that you put for us, we couldn't have accomplished this without your continuous guidance. 
Thank you for not only teaching us this semester but for being there for us over the past five years. You made Mechatronics enjoyable, 
and it was a privilege to have instructors and teaching assistants whom we genuinely consider friends. Thank you again for everything!

**Team 17**
Ahmed Mostafa | Hazim Ashraf | Moustafa Abulmagd | Abdullah Eid
