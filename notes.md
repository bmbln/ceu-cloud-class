# 2021-11-03
IP: ca. 40 billion combination possible -> we keep creating min-internet universes  

TCP : important that it arrives and we dont lose information.  
UDP communicaiton: doesn't care if it arrives. Video streaming and conference is classic example  

Port (on servers): virtual for a given task. Webserver (standard or secure), etc. Numbered, consensus what port to use for which service. 
80: HTTP
443: HTTPS

DNS servers: in hierarchies, roots know things (bottlenck), which DNS server might know more - playing around among rooters. You need to find the DNS that knows it and gives you the IP.  
Unnecessary if you know the IP address directly.  

Check a whole lot of stuff by Inspect and click network
Cookies: when connecting to website, it stores some information about you. Some are necessary to operate the website smoothly (basic cookies)

How HTTPS works?   
- No one is going to understand what happens between you and the server
- rather new standard

???

# 2021-11-10
Storage solutions on Amazon  
Create computers in the cloud  

Cloud solutions: IaaS PaaS SaaS 
IaaS: 
PaaS: dev.azure.com , GitHub Actions , //Data Warehouse Services// OpenShift , Cloudera , Snowflake , BigQuery 
SaaS: GoogleDrive , iDrive , Zoom , DropBox , Gmail  

Mostly pricing by use, what effor they need to do. 

Jenkins is good for CI/CD: Continous Integration and Continous Delivery - a pipeline  

S3 we gonna experiment with: PaaS or IaaS or something inbetween 

DataWarehouse: a database organized and indexed so it is optimized for analytic  


Amazon is the largest player. Roots of could: Amazon needed a lot of servers to serve peaks but had immense unused capacities outside of peak periods that they started renting out. 
Netflix started on cloud from the beginning on AWS. Big opensource contributors. https://github.com/Netflix


Playing around in SWA. Shitton of services
- make sure choosing Ireland (most services are available here)
- For Computing, EC2: Elastic Computing. Create computers, networks, firewalls, etc. Very standard IaaS
- Lambda is fun, serverless solution. Create a script, upload, http provided. Paid per sec
- Image recognition

Storage we usually work with:
- EBS: when we create a computer, an independent storage disk created 
- S3: upload then download files simply. But ON A SCALE it's practically infinite in size and in speed (a.k.a. bandwidth)
- Glacier: similar to S3 but sooooo cheap

S3: 
backets - top level folders, but everyone shares the same backet space so no name duplicates
blocked from public access by default 
File uploading: by default private, paying is based on properties. 

Object properties:
- S3 URI for accessing from anywhere, it has also a public URL 
- HW documentation in a .doc save as .pdf then upload to our SW3 

==================
Create a computer and access via SSH
1. Create a PKI Keypair 
2. Firewall: Create a security group
3. Create an EC2 instance (=Computer) 
4. Connect to the Computer - this is going to be different on Mac and Windows
5. Install a web server

Processor types with regards to architecture 
- x86: AMD, Intel (most computers and laptops)
- ARM: Phones and tablets. But recently Apple introduced M1 for laptops! it's an important shift, we might see an industry-wide change soon. 

on EC: m5.xlarge is similar to a laptop. Windows is 2x expensive because of licences. Still not a bad deal though. 
Practically you can buy a very cheap laptop and rent a virtual computer on Amazon with high performance and pay as you go. 

1. Create key pair on EC2. On MAC keep it in pem, ppk is for Win, RSA is needed
2. Firewall: Security Group. VPC is virtual private cloud, too technical, leave default. In/outbound rules. What kind of traffic is allowed in or out. Port: 2345 (SSH Server) in our case because of CEU Firewall, otherwise it would be Port:22 in Custom TCP
3. Create computer, a.k.a. instance. Now we are doing My AMI, Amazon Machine Image - computer configuration created for us, the SSH is changed in it. We have only right to t4g.nano. Configure Instance Detail, we won't change but we can finetune otherwise. Add storage adds a root which shall be paid on top of the other storage we created. Configure Security group and choose yours!!!
4. Copy IP address 54.170.120.202 use it in some commands. 
5. 'sudo apt install nginx' this creates a web server, but won't work at the moment because of SSH


