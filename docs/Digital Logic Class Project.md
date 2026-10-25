This project is for my current digital logic course. My intention is to integrate the concepts covered in class into my RF side projects. This will be a very basic RF project that is more focused on 
highlighting digital logic circuits.




**Digital RF Signal Detection and Activity Monitor**

Primary objective: Design and construct a circuit that detects RF energy, classifies received signal strength, and counts separate detection events using physical digital logic ICs.
Functional requirements

ID	  | Requirement	                        | Verification

FR-01 | Detect RF energy above a threshold	| Detector voltage measurement
FR-02 |	Classify signals into weak, medium, and strong	| Truth table and LED testing
FR-03 |	Illuminate only the appropriate classification LED	| Logic simulation
FR-04 |	Count new RF detection events	| Four-bit binary counter
FR-05 |	Reset the counter to zero	| Manual reset switch
FR-06 |	Operate without an Arduino or computer	| Standalone demonstration


Input	| Definition
A	: RF strength exceeds threshold 1
B	: RF strength exceeds threshold 2
C	: RF strength exceeds threshold 3

<img width="675" height="518" alt="image" src="https://github.com/user-attachments/assets/11f40319-d579-4480-b781-e4c47328102a" />


