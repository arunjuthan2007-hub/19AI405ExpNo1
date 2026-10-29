<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: Arunjuthan.M.A</h3>
<h3>Register Number : 212225230020 </h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>



<h2>Program:</h2>

```

import random

class MedicinePrescribingAgent:
    def __init__(self):
        self.location = 1
        self.performance = 0
        self.fever_threshold = 98.5

    def check_patient(self, room, temperature):
        print(f"\nAgent is checking Room {room}")
        print(f"Patient temperature: {temperature} F")

        if temperature > self.fever_threshold:
            print("Patient has a fever.")
            print("Medicine prescribed to the patient.")
            self.performance += 1
        else:
            print("Patient does not have a fever.")
            print("No medicine prescribed.")

    def move_to_room(self, room):
        if self.location != room:
            print(f"\nAgent moves from Room {self.location} to Room {room}")
            self.performance -= 1
            self.location = room

    def run(self, temperatures):
        rooms = [1, 2]
        random.shuffle(rooms)

        for room in rooms:
            self.move_to_room(room)
            self.check_patient(room, temperatures[room])

        print("\n--- Final Performance ---")
        print(f"Performance score: {self.performance}")


print("Medicine Prescribing Agent using PEAS")
print("-------------------------------------")

temperatures = {}

temperatures[1] = float(input("Enter temperature of patient in Room 1 (F): "))
temperatures[2] = float(input("Enter temperature of patient in Room 2 (F): "))

agent = MedicinePrescribingAgent()
agent.run(temperatures)
```

<h2>Output:</h2>
<img width="762" height="337" alt="image" src="https://github.com/user-attachments/assets/6fe55242-fa97-4d0e-912e-4e19efd3f19d" />

<h2>Result:</h2>
Thus, the AI agent was developed and executed successfully.
