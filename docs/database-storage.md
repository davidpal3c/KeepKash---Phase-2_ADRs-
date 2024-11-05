# Database Storage ADR

## Status: 
Accepted

<br>

## Context: 
Our expense tracking app requires a database to persist user data, including income, expenses, categories, and budget goals. Our team’s focus is on developing a secure, scalable, and easy to manage solution that facilitates rapid prototyping, robust data handling, and future extensibility for deployment in different platforms.  
 
<br>

## Decision: 
We propose using SQLite for local storage on the mobile device, combined with encrypting user data and Firebase as a cloud-based option to be introduced in the future for data persistence and syncing across devices.  

 

--> SQLite: 
To provide offline-first functionality, SQLite will be used to store user data locally. It does not require server-side infrastructure and is supported across devices.  
     

 Rationale: 
Local storage will ensure users have access and can log data even when offline, making it a practical solution for a personal expense tracking app providing uninterrupted access.  

 

--> Encryption: 
Local data may still be vulnerable to access by unauthorized users if the device is lost or stolen. Data on the device will be encrypted using SQLite Encryption Extension (SEE) to secure the data stored locally, and Firebase built-in security encryption in-transit rules using HTTPS. 
     

<br>

Rationale: 
Encrypting data locally in the device and in-transit to cloud storage will ensure the user’s information is secured from third parties. Even Firebase administrators will not be able to view the raw data.  

  

--> Firebase (Cloud Storage): 
To support future synchronization across devices, and its ease of integration, scalability and secure data management, Firebase will provide a cloud-based storage option for KeepKash.  

 

 Rationale: 
Firebase provides real-time data synchronization ensuring users will 	be able to access their information on different devices seamlessly if this feature is 	added in later phases.  

 
--> Security Measures: 
We will implement various security measures to protect the local storage against potential threats by using Firebase authentication library.  

 	 

 <br>

## Consequences 

The decision to use local storage with encryption, and cloud storage provider will have the following consequences: 

 
<br>
* Pros: 

    --> Enhanced User Flexibility and Control: 
SQLite ensures users will be able to use the app offline and data will be kept in their device, while Firebase allows for cloud synchronization in the future, expanding the application usability.  

    --> Security: SQLite local encrypted data will make sure data is kept safe locally from third parties, while Firebase’s out-of-the-box robust security rules protect user data in the cloud.  

 

 <br>

## Challenges: 

    --> Cross-Device Synchronization: 
More advanced encryption and key management may be required to Implementing data synchronization across multiple devices to ensure consistent data security. 

    --> Moderate Learning Curve: 
Although Firebase provides comprehensive documentation and community support, the development team may still take some time to familiarize with Firebase integration, this is why it is kept as a future implementation down the road.  