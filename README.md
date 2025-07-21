# Blockchain-Based Mental Healthcare System
In recent years, blockchain technology has evolved from financial to industrial usage, from wellness to healthcare, and from commerce to the service sector. The convergence of blockchain technology and electronic mental health presents an evolutionary system that provides solutions to the challenges of the healthcare system. This report outlines how blockchain revolutionizes the accessibility, security, and anonymity of patient data, as well as the quality of mental healthcare services. We build a system using the Hyperledger Fabric blockchain that fills the gap of the mental system, which lacks the tools to verify the credentials of medical professionals, control, and secure access to one's medical data. In the decentralized cloud system, IPFS has been integrated for secure data sharing, storing patients' encrypted data, and the hash value is stored in the blockchain. The system also offers users teletherapy treatment and access control over their data. To maintain quality treatment, we also implement a review feature. Through this project, we can transform the mental health service with more advances. This is not just a mental healthcare project; through this project, we can also understand how to develop other healthcare sectors.

## System Architecture
We consider the e-mental service a website-based system that can verify the end users, like verified patents, doctors, and researchers. The patients get verified by their national ID number. The doctors get verified by their degree certificates. The authorities are the peer nodes of the Hyperledger Fabric private network that hold the full ledger of patients' data, and they also verify the end users. The researchers have to pay to get registered in the system to get patients' data by getting permission from them. The verified patients can create an appointment with their preferred doctor, or the system will choose a doctor for them. Patients have to pay first to create the appointment. The doctor will conduct teletherapy sessions for the patients who are on his appointment list. Therapy sessions, recorded videos, documents, and patients' healthcare data are kept in the distributed cloud storage IPFS. This digital content is encrypted and decrypted using the admin's private key before uploading as well as downloading. Blockchain will be used to store the hash value, which comes back from the IPFS, and that is the location of the saved record in the cloud. The patient can give and revoke access to whoever wants to see their data. And the access will be maintained by a list that will also be stored in the blockchain. The other non-sensitive data is stored using mysql database. After treatment has finished, the patients can give the  doctors a review of the quality of the treatment. Both verified and unauthenticated website visitors can see the reviews of a doctor. But Unauthenticated visitors can not create an appointment. Researchers have to get permission from patients in order to get their medical records.

![System Architecture Image](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/Articture_diagram.jpg)  

## System Actors

![System Actors Image](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/Actor.jpg)  

**Healthcare Authorities** - They are the committing Peers or endorsing Peers of the hyperledger permissioned network. They take transaction proposals and execute them to create endorsements. And they also maintain the state of the Blockchain and commit verifiable transactions. They can join the network by funding the system that will be used to develop the blockchain even further.  

**Authorities** - They are the admins of the system and also play the role of a healthcare institute. They are the main authority that permits them to join the network. They also verify or remove doctors' certificates and patients' identities, hire doctors, and solve any other problems, queries of lower-layer users. Their public key is used to encrypt and decrypt medical content. But they cannot decrypt data without the permission of the patients.  

**Doctors** - They are healthcare practitioner who get appointments, provide teletherapy sessions to patients. They are verified by the admin, without verification they cannot get appointment or treat patient. They get verified by uploading their degree credentials and also updating them. They can get and update patients' medical record with getting permission. They can also block their appointment time if there is no appointment in that time.  

**Patients** - They use the system to get teletherapy creating appointment by payment. They can upload their personal information and grant assess on their data. They can choose doctors by the review and after treatment they give review to doctors.  

**Researchers** - They can apply to the system and be approved by the admin. Researchers can get patients' confidential data by requesting access permission from them.  

## Requirements

#### Features for Doctors
  1. **Profile Management** - Doctors can request their profile updates for qualifications, specialties, and availability, including authentic documents.
  2. **Appointment Management** - Access a calendar for scheduling and managing patient appointments. Receive notifications for upcoming appointments.
  3. **Patient Records** - View, update, and download or print patient medical records, treatment histories, and assessment results, all securely stored on the blockchain.
  4. **Request Access** - Can request access to patients' data.
  5. **Create Session** - Can create sessions with appointed patients to give teletherapy.
  6. **Treatment Plans** - Create and update personalized treatment plans for patients, including medication prescriptions if necessary.
  7. **Billing** - Manage billing through smart contracts, streamlining administrative tasks.
  8. **Patient Feedback** - Get patient feedback and ratings, improving the quality of care.
  9. **Fees** Pay a monthly fee to the authority for using the platform.
  10. **Contact** - Contact with authorities in case of any complaints or reporting any issue.
  11. **Patient List** - Can see the patient list of those who created an appointment and those who got treated.

#### Features for Patients
  1. **Profile Creation** - Patients can create and manage their profiles, including personal information, medical history, and preferences.
  2. **Appointment Booking** - Schedule appointments with doctors based on availability, specialties, and the appointment will be booked after paying session fees.
  3. **Access Control** - Can grant and remove access to others who want to see medical reports.
  4. **Join Session** - Can participate in teletherapy sessions with mental health professionals.
  5. **Contact** - Contact with authorities in case of any queries, complaints, or reporting.
  6. **Feedback and Ratings** - Provide feedback and ratings for healthcare providers.
  7. **Doctor List** - Patients can check the available doctors list, their ratings, and also search for doctors by their names and specialities.

#### Features for Administrators
  1. **User Management** - Admins can verify and remove user accounts.
  2. **Doctor Management** - Admins can verify and remove doctors’ accounts.
  3. **Blockchain Network Management** - Oversee the blockchain network, including nodes, security.
  4. **Compliance and Reporting** - Monitor and ensure compliance with healthcare regulations and reporting requirements.
  5. **Analytics and Insights** - Access analytics tools to monitor system performance and user engagement.
  6. **Financial Management** - Oversee financial transactions, payments, and financial reporting.

#### Features for Researchers
  1. Researchers can request to get verified by paying.
  2. They can make access requests to patients.
  3. Can see the patient’s  medical records and treatment history after getting access from the patients.
  4. The system will give a flowchart of different types of patients' mental health conditions.

#### Features for the System

**Verification and Identification** - The system must verify every user in the system. In the registration form patient has to give their national ID number to get verified. One ID card can be used only once to get registered. If a NID has been used before, then the patient can not register with that NID and can not get the services of the system. In blockchain, patients are identified by a blockchain address that is generated by combining the patient's ID + NID number. Without verifying patient cannot able to create any appointment, but he can see the doctor's information and review. Doctors will have to upload their credentials to get verified. The admin will check the authenticity of the credentials and permit the doctor's request. Without verification, doctors cannot get any appointments or treat patients. For researchers to get registered, they have to pay some money; otherwise, they cannot have access to the system functionality.  

**Storage Security** - The recorded treatment videos, documents, and patients' medical records should be stored in the decentralised storage for better security. Our solution to the storage issue with blockchain is the Inter Planetary File System, a distributed storage that helps. First, an asymmetric encryption method is used to encrypt the medical information using the  authorities' secret key. The patient's identity address will then be linked to the encrypted data in the IPFS. The hash value of the data comes back via cloud storage, which is then logged in the blockchain, where the patient's identity address is mapped. Only the  patient and doctor, if granted, can able to store the data.   

**Access Control** - The system should be able to give patient control over their data. Patients can grant any participants, doctors, researchers, or authorities access to their data. In the backend, the ID of the participant will be added to the access list. This list is unique to each patient and is kept on the Hyperledger blockchain. The ID will be deleted from the list if the patient wants to withdraw their access from the participant. Only the patients and doctors have the update access to medical data.  

**Secure Sharing** - Participants can securely share the medical data. Any participant who wants to access a patient's sensitive data the check the participant's ID against the access list of the patient. If ID is in the access list, then the system takes the patient's identity address and fetches stored materials corresponding to the address. Then the encrypted data is decrypted using the admin's private key. On the other hand, if the participant's ID is not found in the access list, then an access request is sent to the patient. If the patient accepts the request, then the sender's ID is added to the list, and he gets the medical information. Else participant's data request has been cancelled.  

## System Design

#### Sequence Diagram

![Sequence Diagram](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/Sequence%20of%20storing%20and%20sharing.jpg)

#### Use Case Diagram

![Use Case Diagram](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/Use%20Case%20Diagram.jpg)

#### Class Diagram

![Class Diagram](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/Class_diagram.drawio.png)

#### Data Flow Diagram

![Data Flow Diagram](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/Data%20flow%20diagram.jpg)

#### Component Diagram

![Component Diagram](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/Component%20Diagram.jpg)

#### Context Diagram

![Context Diagram](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/Context%20diagram.jpg)


## System UI

#### Admin Panel (Doctors List)

![Doctors list in admin panel](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/doctor%20list%20admin%20view.png)

#### Patient Interface (Doctors)

![Doctors view in patients dashbord](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/doctor%20list%20patient%20view.png)

#### Patient Control Access Panel

![Control access in patient panel](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/access%20list.png)

#### Doctor's Appointment Window

![Doctors appointment window](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/appointment%20list%20doctor%20view.png)

####  Teletherapy Seasons

![Teletherapy season view](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/blob/a6d7e066042905cf75bd219ad1bbda59452b854e/images/session%20room%20doctor%20view.png)


## How to deploy the system locally

Before getting started, you need linux operating system to setup the environment. If you already have docker installed and Hyperledger fabric fabric-samples, you can skip this step.

#### Installation of Docker, Docker Compose, Hyperledger Fabric

  1. Assuming you already have git installed on your computer. Check for the git version using the command provided below. If you do not get any version in the log you need to install git  
  ```
  git --version 
  ```

  2. Next, install jq using the command below:  
  ```
  sudo apt-get install jq
  ```

  3. Now, we will install Docker and Docker Compose. But first, remove the older versions of Docker (if any) using the following commands:      
  ```
  sudo apt-get remove docker docker-engine docker.io containerd runc
  ```
  It is okay if the above command reports that none of these packages are installed or package 'xyz..' is not installed.  
  
  4. Now, Update apt:
  ```
  sudo apt-get update
  ```

  5. Install packages to allow apt to use a repository over HTTPS:
  ```
  sudo apt-get update && sudo apt-get install apt-transport-https ca-certificates gnupg-agent software-properties-common lsb-release -y
  ```
  This may take some time to install.  
  
  6. The command below is for downloading Docker’s official GPG key. where -o defines the output path and --dearmor is to help convert the file into gpg format.
  ```
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-keyring.gpg
  ```
  Don't worry if this command does not show you any response or logs in terminal. Here, docker-keyring.gpg is the file containing the key.  
  
  7. Use the following command to set up the stable repository and add it to the list of package sources:  
  ```
  echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
  ```
  This command will also not show any response or logs in terminal.  
  
  8. Now, update the apt package again:  
  ```
  sudo apt-get update
  ```
  **NOTE:** If you a GPG error when running apt-get update, run the following command:  
  ```
  sudo chmod a+r /etc/apt/keyrings/docker.gpg
  sudo apt-get update
  ```

  9. Install Docker:  
  ```
  sudo apt-get install docker-ce docker-ce-cli containerd.io -y
  ```

  10. Next, you need to use the following commands to ensure that the user can run the docker commands with proper access privilege.  
 
  - Add docker to user group
  ```
  sudo groupadd docker
  ```
  This might report that the docker group is already added, which is fine  
  - Now, add the current user to the docker group using:   
  ```
  sudo usermod -a -G docker $USER
  ```
  - Finally, activate the change by:  
  ```
  newgrp docker
  ```
  - Now, you need to rebot the PC to make the changes function properly. Therefore, run the command:  
  ```
  sudo reboot
  ```
  This will restart your machine and then again open the terminal and follow step 9. it should work now.  
  
  11. Download the docker-compose binary file using the command mentioned below. You can see the version that we are using is 1.29.2. If you use an older version, you may get errors in upcoming steps. Therefore you should maintain the version according to the instruction  
  ```
  sudo curl -L https://github.com/docker/compose/releases/download/1.29.2/docker-compose-`uname -s`-`uname -m` -o /usr/local/bin/docker-compose
  ```
  Depending on your internet, this may take time.  
  
  12. Make it executable using:  
  ```
  sudo chmod +x /usr/local/bin/docker-compose
  ```
  Dont' worry, if this command does not show any response or logs in terminal.  
  
  13. Now, check the installation:  
  ```
  docker-compose --version
  ```
  You should see a version like **docker-compose version 1.29.2, build 5becea4c**  
  
  14. Now, our computer is ready to install Hyperledger Fabric. But, the first step is to remove existing Fabric images, if any:  
  ```
  docker container prune
  ```

  15. Next, copy and run:  
  ```
  cd ../
  mkdir fabric
  cd fabric
  ```

  16. Now, by running the following command we will install fabric version 2.5.10 and ca version 1.5.13  
  ```
  curl -sSLO https://raw.githubusercontent.com/hyperledger/fabric/main/scripts/install-fabric.sh && chmod +x install-fabric.sh
  ```
  Now, run:  
  ```
  ./install-fabric.sh
  ```
  This process will take time depending on your internet speed. This will create a folder called “fabric-sample”. Check it, you should see a lot of files inside it. These are some       sample boilerplates.  

#### Setting up files and folders 

  1. First, download the files from [https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution.git](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution.git) and unzip the contents. If you want, you also can clone it. To clone it, open terminal and issue:  
  ```
  git clone https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution.git
  ```
  This will successfully clone the GitHub repository, and now you should have a directory called `blockchain-based-e-mental-healthcare-solution`  
  
  2. Now go to `blockchain-based-e-mental-healthcare-solution` and copy the [e-Mental-App](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/tree/a6d7e066042905cf75bd219ad1bbda59452b854e/e-Mental-App) and [chaincode](https://github.com/faiyaz-masrur/blockchain-based-e-mental-healthcare-solution/tree/a6d7e066042905cf75bd219ad1bbda59452b854e/chaincode) files.  
     
  4. Now, go to the `fabric/fabric-samples` directory and paste the `e-Mental-App` and `chaincode` files. (Before pasting, check if the same files exist in the directory and delete them)

#### Starting the network and server

  1. Now, we will start the network. Open terminal from your code editor and go to the `fabric-samples/e-Mental-App` directory from the terminal and run the command: 
  ```
  ./startFabric.sh javascript
  ```
  This command will invoke the `test-network` and initialize it, and also it will deploy the chaincode available in the `fabMed/chaincode-javascript` directory to the fabric network.  
  
  2. Now, we need to install npm packages. You can find the necessary packages that we are going to install inside the package.json file. It is strongly recommended to use node version `18`. To install, run:   
  ```
  npm i
  ```

  3. Run the command below to enroll admin to organization:
  ```
  node enrollAdmin.js
  ```
  and then run the command to register user to organization:  
  ```
  node registerUser.js
  ```

  4. Finally, we will power up our backend using:
  ```
  npm start
  ```
  You will see the server is running at port `8080`   

  To stop the network, you can use the available script by running  the command:
  ```
  ./networkDown.sh
  ```


