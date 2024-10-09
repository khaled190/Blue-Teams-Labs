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

![4 1](https://github.com/user-attachments/assets/911c60af-32cb-4631-931f-775488a5e9a4)


















