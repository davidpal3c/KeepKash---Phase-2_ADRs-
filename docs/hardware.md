# Hardware ADR

## Status: 
Accepted 

 
<br>
## Context: 
In the development of KeepKash, we needed to decide the selection of specific hardware requirements with the goal of keeping the app straightforward and accessible across devices. Since users will manually enter expenses and other budgeting information, our focus is on minimal hardware dependencies to streamline development and improve accessibility.  
 
<br>
## Decision: 
To streamline development and maintain simplicity, KeepKash will not rely on any specific hardware features beyond the essentials provided by the device (e.g. touchscreen for data input). No additional hardware, such as camera or biometric authentication, will be integrated at this stage.  

 

    --> Touchscreen input: 
    The app will use the device’s touchscreen for manual entry of data, allowing users to input information such as expenses, income, and set budget goals. 

	Rationale: 
	Touchscreen input provides a straightforward method for data entry, suitable for a minimalistic app without hardware dependencies.  

 

 
<br>
## Consequences 

 

--> Simplicity and Accessibility: 
By focusing solely on touchscreen input, the app 	remains accessible on any mobile device, regardless of additional hardware 			features. 

--> Minimal Development Overhead:
Avoiding extra hardware integration will reduce complexity and development time, aligning with the project’s goals for streamlined functionality, simplicity, and development time constraints. 

--> Future Expandability: 
Should we decide to introduce additional features, such as biometric authentication, in the future, we can revisit hardware requirements accordingly. 