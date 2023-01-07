#networking 
#transport
#protocols 

## Transport Layer
The transport layer is a layer in the OSI (Open Systems Interconnection) model that is responsible for providing end-to-end communication and reliability between devices on a network. Here are some key points to understand about the transport layer:
- Transport Layer Characteristics: The transport layer has several key characteristics, including:
	- **End-to-end communication**: The transport layer provides communication between two devices, from the sender to the receiver. It is responsible for breaking down data into smaller units (called segments) and reassembling them at the destination.
	- **Multiplexing**: The transport layer allows multiple applications on a device to share the same network connection by multiplexing their data together.
	- **Connection-oriented communication**: The transport layer establishes a logical connection between the sender and receiver before transmitting data. This connection allows for the reliable transmission of data and for flow control to prevent the sender from overwhelming the receiver.

-   Transport Layer Session Establishment: In order to establish a transport layer session, the following steps typically occur:
	1.  The sender sends a request to the receiver to establish a connection.
	2.  The receiver sends a response to the sender to confirm the connection.
	3.  The sender and receiver exchange additional information to negotiate the parameters of the connection, such as the maximum size of the data segments that will be transmitted.
	4.  The sender and receiver establish the connection and begin transmitting data.

-   Transport Layer Reliability: The transport layer is responsible for ensuring the reliable transmission of data between devices. It does this by using various mechanisms such as:
	- **Flow control**: The transport layer can regulate the rate at which data is transmitted to prevent the sender from overwhelming the receiver.
	- **Error checking**: The transport layer can use checksums or other techniques to detect errors in the transmitted data and request retransmission of any corrupted segments.
	- **Sequence numbering**: The transport layer can assign a sequence number to each segment of data and include an acknowledgement (ACK) in the response to indicate which segments have been received successfully. This allows the sender to determine which segments have been lost and to request retransmission as needed.

By providing these and other services, the transport layer ensures that data is transmitted reliably between devices on a network.

## Network Services
- **DHCP: DHCP (Dynamic Host Configuration Protocol)** is a network service that is used to assign IP addresses to devices on a network automatically. DHCP servers maintain a pool of available IP addresses and assign them to devices as needed. This allows network administrators to manage IP addresses more efficiently and reduces the need for manual configuration of IP addresses on individual devices.
- **DNS: DNS (Domain Name System)** is a network service that is used to translate domain names (such as [www.example.com](http://www.example.com/)) into IP addresses. DNS servers maintain a database of domain names and their corresponding IP addresses and respond to queries from client devices to resolve domain names to IP addresses. This allows users to access websites and other resources using human-readable domain names rather than IP addresses.
- **NAT: NAT (Network Address Translation)** is a network service that is used to allow devices on a private network to communicate with the internet using a shared public IP address. NAT allows devices on the private network to use private IP addresses, which are not unique on the internet, and translates them to a unique public IP address when communicating with the internet. This conserves public IP addresses and provides an additional layer of security by hiding the private IP addresses of devices on the network.
- **File Transfer and Sharing Services**: There are several types of network services that are used to transfer and share files, including FTP (File Transfer Protocol), SFTP (Secure File Transfer Protocol), and SMB (Server Message Block). These services allow users to upload and download files, share files with others, and access shared file storage.
- **Email**: Email is a network service that allows users to send and receive electronic messages over the internet. Email servers maintain mailbox accounts for users and facilitate the delivery of messages between users.
- **HTTP: HTTP (Hypertext Transfer Protocol)** is a network service that is used to transfer web pages and other resources over the internet