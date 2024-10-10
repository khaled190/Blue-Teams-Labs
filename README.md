# Cyberdefenders-Malware Traffic Analysis 1

### The exercises gives a person knowledge on:

- How network traffic flow occurs between a client and a server.
- How certain protocols work and their purpose.
- Type and signature of several malwares.

### Objective:
The challenge contains set of questions which I will cover and explain in this post.

### Note:
Usually the pcaps are monitored and analysed using a free and open-source packet analyzer called wireshark which gives user GUI experience.

But here we will be using combination of several tools to understand the concept in a better way.

The challenges can be downloaded [here](https://cyberdefenders.org/blueteam-ctf-challenges/?search_query=malware), protected by a password “cyberdefenders.org”.

## Let’s start to answer the questions !!!
### 1. What is the IP address of the Windows VM that gets infected?
### Answer:  

ip is [ 172.16.165.165 ] 

- To find the IP we should analyse the traffic flow.
- We usually use wireshark for it, but to feel a CLI, we use Tshark.

![1](https://github.com/user-attachments/assets/ff875623-7264-4a4c-add7-229cd10dc309)

![1 1](https://github.com/user-attachments/assets/af9629d1-6414-42a1-9dd3-6765780e1c91)


### 2. What is the hostname of the Windows VM that gets infected?
### Answer:  
Hostname is [ K34EN6W3N-PC ]

![2](https://github.com/user-attachments/assets/cbdff7f3-2a09-4ee5-8c2d-6b637c40c516)

or
By Zui Tool and write following Query { _path=="dhcp" | client_addr 172.16.165.165 }

![2 1](https://github.com/user-attachments/assets/3bb34aaf-ccec-4add-9e6e-2b8543a55ec3)


### 3. What is the MAC address of the infected VM?
### Answer:  

the MAC address of the host is [ f0:19:af:02:9b:f1 ]

sudo tshark -r mta1.pcap -T fields -e eth.src -e ip.src -e eth.dst -e ip.dst | sort | uniq -c

![3](https://github.com/user-attachments/assets/55ac7af3-b778-4909-8bbb-26148ac4ecd5)


### 4. What is the IP address of the compromised web site?
### Answer:  

the compromised web site is [ciniholland.nl] and its ip_Address is [82.150.140.30]

![4 1](https://github.com/user-attachments/assets/cf19c8dd-ea32-41d9-a594-0cffb632b795)
![4 2](https://github.com/user-attachments/assets/dd2045b2-ce18-46c5-a2a1-1bf594c5a749)
![4 3](https://github.com/user-attachments/assets/3691f7b6-72e3-49f7-84db-2e577e98098c)


### 5. What is the FQDN of the compromised website?

### Answer:

You can determine the FQDN of the compromised website from question number 4.
FQDN = Hostname + Domain Name.
FQDN = "ciniholland.nl"

### Q(6) What is the IP address of the server that delivered the exploit kit and malware?

### Answer:

IP addressis  37.200.69.143

![6 0](https://github.com/user-attachments/assets/6f9a5efb-60cf-42ca-9b88-398530705e39)
![6 1](https://github.com/user-attachments/assets/2b47e4b6-73da-4d7b-9e6e-35200037c4d9)
![6 3](https://github.com/user-attachments/assets/fd790b52-bd94-47f4-ab95-316f1e3650a4)


### 7. What is the FQDN that delivered the exploit kit and malware?

### Answer:

From the previous analysis we can conclude that the compromised site’s FQDN is stand.trustandprobaterealty.com


### 8. What is the redirect URL that points to the exploit kit (EK) landing page?

### Answer:

the redirect URL is #http://24corp-shop.com

![8 0](https://github.com/user-attachments/assets/575bed49-94ff-4af6-bb29-a714bbd4e8cd)




























