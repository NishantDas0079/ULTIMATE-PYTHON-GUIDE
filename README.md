# PYTHON PRACTICAL CODES (27/08/25) 
All python codes and notes uploaded here. 



---
```

# Q1. Roots of a quadratic equation :-


import cmath
a, b, c = map(float, input("Enter a, b, c: ").split())
d = (b**2) - (4*a*c)
root1 = (-b + cmath.sqrt(d)) / (2*a)
root2 = (-b - cmath.sqrt(d)) / (2*a)
print("Roots:", root1, root2)
```


---
```

# Q2. Prime Numbers :-

(a) Check if n is prime

n = int(input("Enter n: "))
print("Prime" if n > 1 and all(n % i for i in range(2, int(n**0.5)+1)) else "Not Prime")

(b) Generate all prime numbers till n

n = int(input("Enter n: "))
primes = [x for x in range(2, n+1) if all(x % i for i in range(2, int(x**0.5)+1))]
print("Primes till n:", primes)

(c) Generate first n prime numbers

def isprime(x): return x > 1 and all(x % i for i in range(2, int(x**0.5)+1))
n = int(input("Enter n: "))
primes, num = [], 2
while len(primes) < n:
    if isprime(num): primes.append(num)
    num += 1
print("First n primes:", primes)
```

---
```

# Q3. Pyramid and Reverse Pyramid :-

n = int(input("Enter rows: "))
for i in range(1, n+1): print(" "*(n-i) + "*"*(2*i-1))
for i in range(n-1, 0, -1): print(" "*(n-i) + "*"*(2*i-1))
```

---
```
# Q4. Character Operations :-

ch = input("Enter a character: ")

if ch.isalpha():
    print("Letter - Uppercase" if ch.isupper() else "Letter - Lowercase")
elif ch.isdigit():
    names = ["ZERO","ONE","TWO","THREE","FOUR","FIVE","SIX","SEVEN","EIGHT","NINE"]
    print("Digit:", names[int(ch)])
else:
    print("Special character")
```

---
```
# Q5. String Operations :-

s = input("Enter string: ")
print("Frequency of 'a':", s.count('a'))
print("Replace a by x:", s.replace('a', 'x'))
print("Remove first 'a':", s.replace('a', '', 1))
print("Remove all 'a':", s.replace('a', ''))

```
---
```
# Q6. Swap first n characters of two strings :-

s1, s2, n = "hello", "world", 2
print("After swap:", s2[:n] + s1[n:], s1[:n] + s2[n:])

```
---
```
# Q7. Function to return indices of substring :-

def find_indices(s1, s2):
    return [i for i in range(len(s1)) if s1.startswith(s2, i)] or -1

print(find_indices("banana", "na"))
```

---
```
# Q8. Cubes of Even Integers :-

lst = [1, 2, 3, 4, 5, 6]
print([x**3 for x in lst if isinstance(x, int) and x % 2 == 0])
```

---
```
# Q9. File Operations :-

from collections import Counter

with open("file.txt") as f:
    data = f.read()

print("Characters:", len(data))
print("Words:", len(data.split()))
print("Lines:", data.count("\n")+1)

print("Frequency:", dict(Counter(data)))
print("Words reversed:", " ".join(data.split()[::-1]))

open("File1.txt", "w").writelines(data.splitlines()[1::2])
open("File2.txt", "w").writelines(data.splitlines()[::2])
```

---
```
# Q10. Class Point :-

class Point:
    def __init__(self, x, y):
        self.x, self.y = x, y
    def __str__(self):
        return f"({self.x},{self.y})"
    def dist(self, p):
        return ((self.x - p.x)**2 + (self.y - p.y)**2)**0.5

p1, p2 = Point(1, 2), Point(4, 6)
print(p1, p2, "Distance:", p1.dist(p2))
```

---
```
# Q11. Dictionary {n: n³} :-

print({x: x**3 for x in range(1, 6)})
```

---
```
# Q12. Tuple Operations :-

t1 = (1, 2, 5, 7, 9, 2, 4, 6, 8, 10)

print("Half split:", t1[:len(t1)//2], t1[len(t1)//2:])
print("Even values:", tuple(x for x in t1 if x % 2 == 0))

t2 = (11, 13, 15)
print("Concatenation:", t1 + t2)

print("Max:", max(t1), "Min:", min(t1))
```

---
```

# Q13. Exception Handling :-

try:
    name = input("Enter your name: ")
    if not name.isalpha():
        raise ValueError("Name must contain only alphabets!")
    print("Hello,", name)
except ValueError as e:
    print("Error:", e)
```



# PYTHON BASICS (20/08/25 to 1/09/25) 

🐍 Python Basics 

---

🔹 1. Python Overview

High-level, Interpreted, Object-Oriented

Dynamic typing → no type declaration needed

Extension: .py



---

🔹 2. Variables & Data Types

Primitive: int, float, str, bool, complex

Collections: list, tuple, set, dict, array, deque

Special: bytes, bytearray, frozenset


x = 10        # int
y = 3.14      # float
z = "Hello"   # str


---

🔹 3. Operators

Arithmetic → + - * / % // **

Comparison → == != > < >= <=

Logical → and or not

Membership → in, not in

Identity → is, is not



---

🔹 4. Control Flow

if cond: ...
elif cond: ...
else: ...

for i in range(n): ...
while cond: ...
break, continue, pass


---

🔹 5. Functions

def func(a, b=0, *args, **kwargs):
    return a+b


---

🔹 6. Strings

Immutable, ordered

Slicing → s[0:5], s[::-1]

Methods → .upper(), .lower(), .split(), .replace()



---

🔹 7. Core Data Structures

✅ List

Mutable, ordered, allows duplicates


lst = [1, 2, 3]
lst.append(4)

✅ Tuple

Immutable, ordered, allows duplicates


tup = (1, 2, 3)

✅ Set

Mutable, unordered, unique elements


s = {1, 2, 3}
s.add(4)

✅ Dictionary

Key-Value pairs, mutable, ordered (Py 3.7+)


d = {"a": 1, "b": 2}
d["c"] = 3


---

🔹 8. Other Python Data Structures

✅ Array (from array module)

Stores homogeneous data (all same type).


import array
arr = array.array('i', [1, 2, 3])

✅ Deque (from collections)

Double-ended queue, fast appends/pops.


from collections import deque
dq = deque([1, 2, 3])
dq.appendleft(0)

✅ Stack (via list or deque)

LIFO (Last In First Out).


stack = []
stack.append(1)
stack.pop()

✅ Queue (via deque or queue module)

FIFO (First In First Out).


from collections import deque
q = deque([1,2])
q.popleft()

✅ Priority Queue (heapq)

Implements min-heap.


import heapq
pq = [3, 1, 4]
heapq.heapify(pq)
heapq.heappop(pq)  # smallest

✅ Linked List (manual class implementation)

Not built-in → created using Node class.


✅ Graphs / Trees

Implemented using dict (adjacency list) or classes.



---

🔹 9. File Handling

with open("file.txt","r") as f:
    data = f.read()


---

🔹 10. Exception Handling

try:
    x = 1/0
except Exception as e:
    print(e)
finally:
    print("Done")


---


# FUNCTIONS

📘 Python Functions & Variable Scope

🔹 Python Function

Definition: Block of reusable code to perform a specific task.

Syntax:

def function_name(parameters):
    # body
    return value

Advantages: Code reuse, modularity, readability.

Types:

Built-in functions (len(), print())

User-defined functions




---

🔹 Call by Value

Concept: Function gets a copy of the variable’s value.

Effect: Changes inside function do not affect original variable.

Python Note:

Immutable objects (int, float, str, tuple) behave like call by value.



Example:

def modify(x):
    x = x + 10
a = 5
modify(a)
print(a)  # Output: 5 (unchanged)


---

🔹 Call by Reference

Concept: Function gets reference (address) of variable.

Effect: Changes inside function affect original variable.

Python Note:

Mutable objects (list, dict, set) behave like call by reference.



Example:

def modify(lst):
    lst.append(10)
a = [1,2,3]
modify(a)
print(a)  # Output: [1, 2, 3, 10]


---

🔹 Static Scoping (Lexical Scoping)

Definition: Scope of a variable is determined at compile-time by its lexical (code) structure.

Python follows static scoping.

LEGB Rule: Local → Enclosing → Global → Built-in.


Example:

x = 10
def outer():
    x = 20
    def inner():
        print(x)  # Refers to x=20 (enclosing scope, not global)
    inner()
outer()


---

🔹 Dynamic Scoping

Definition: Scope of a variable determined by runtime call sequence (not lexical structure).

Python does NOT use dynamic scoping (languages like Lisp can).


Example (hypothetical dynamic scoping):

x = 10
def f():
    print(x)   # Would look up variable in caller’s scope at runtime
def g():
    x = 20
    f()        # Would print 20 in dynamic scoping, but prints 10 in Python
g()


---

🔹 Global Variable

Defined outside all functions, accessible everywhere.

Use global keyword to modify inside a function.


Example:

x = 5
def func():
    global x
    x = 10
func()
print(x)  # Output: 10


---

🔹 Local Variable

Declared inside function.

Accessible only within that function.


Example:

def func():
    y = 100  # local
    print(y)
func()
print(y)  # Error: y not defined


---

✅ Quick Recap Keywords:

Python Function → reusable block, defined using def.

Call by Value → Immutable (int, str, tuple).

Call by Reference → Mutable (list, dict, set).

Static Scoping → Python default, uses LEGB rule.

Dynamic Scoping → Runtime lookup (not in Python).

Global Variable → Declared outside, use global.

Local Variable → Declared inside, scope limited to function.


---







# Comprehensive Tech Notes (5/08/25 to 1/09/25) 

1. Computing Devices

Mobile, Desktop, Server – Fundamentally similar in core principles:

Hardware – Physical components like CPU, GPU, storage devices, network cards.

Software – Operating systems, applications, and system utilities that control hardware.

Computation – Processing of instructions via processors (CPU, GPU, etc.).

Storage – Persistent memory (HDD, SSD) and volatile memory (RAM).

Network – Communication via wired/wireless connections.




---

2. Processing Units

CPU (Central Processing Unit) – General-purpose processor for logic, arithmetic, and control operations.

GPU (Graphics Processing Unit) – Highly parallel processor for rendering graphics and accelerating AI/ML tasks.

IPU (Intelligence Processing Unit) – Optimized for AI workloads and graph-based computations.

TPU (Tensor Processing Unit) – Google’s custom chip for machine learning.

NPU (Neural Processing Unit) – Accelerates AI/ML inference on devices.

DPU (Data Processing Unit) – Handles data movement, storage, and networking tasks.

QPU (Quantum Processing Unit) – Executes quantum algorithms using qubits.

Smart NIC (Network Interface Card) – Network adapter with its own processor for offloading network tasks.



---

3. Chip & Architecture

Architecture – Instruction set and design of processors.

x86 – Common in desktops/servers, by Intel & AMD.

8085 – 8-bit microprocessor, used in early computing.

ARM – Energy-efficient architecture, dominant in mobile devices.

RISC-V – Open-source instruction set architecture.

CISC – Complex Instruction Set Computing (fewer instructions, more complex operations).

RISC – Reduced Instruction Set Computing (simpler instructions, faster execution).


Major Companies:

Intel, AMD – x86 processors.

TSMC, Samsung – Semiconductor manufacturing.

ASML – Lithography machines for chip production.

IBM – Research & enterprise systems.

Canonical – Maintains Ubuntu Linux.




---

4. Operating Systems

Closed Source – Proprietary software (e.g., Windows by Microsoft).

Open Source – Publicly available source code (e.g., Linux).

Ubuntu – User-friendly Linux distro by Canonical.

Red Hat – Enterprise Linux distribution.




---

5. Networking Basics

LAN – Local Area Network (small area).

MAN – Metropolitan Area Network (city-wide).

WAN – Wide Area Network (global, e.g., Internet).

Intranet – Private network for internal use.

Internet – Global interconnection of networks.

NICs – Network Interface Cards.

ISP – Internet Service Provider.

Packets – Units of data sent over a network.

APIPA – Automatic Private IP Addressing (169.254.x.x when DHCP fails).



---

6. IP Addressing

IP – Internet Protocol.

Private IP Range (IPv4) –

Class A: 10.0.0.0 – 10.255.255.255

Class B: 172.16.0.0 – 172.31.255.255

Class C: 192.168.0.0 – 192.168.255.255


Public IP – Globally routable IP assigned by ISPs.

Localhost – 127.0.0.1 (loopback address).

IPv4 – 32-bit addresses (e.g., 192.168.1.1).

IPv6 – 128-bit addresses (e.g., 2001:db8::1).



---

7. OSI Model (7 Layers)

1. Application – User interaction (HTTP, FTP, SMTP).


2. Presentation – Data translation, encryption, compression.


3. Session – Manages sessions (start, maintain, end).


4. Transport – Reliable delivery (TCP, UDP).


5. Network – Logical addressing, routing (IP).


6. Data Link – Error detection, framing (Ethernet, MAC).


7. Physical – Hardware, cables, signals, bits.



Purpose: Standardizes network communication.



---

8. Advanced Computing

Quantum Computer – Uses qubits for parallel computation.

SoC (System on Chip) – Combines CPU, GPU, memory, and other components on one chip.

Bare Metal System – OS runs directly on hardware (no virtualization layer).

Cloud Computing – On-demand computing resources via internet.

Private Cloud – Exclusive to one organization.

Public Cloud – Shared over the internet.




---

9. Virtualization & Development

Virtual Machine – Emulates a full computer system.

VirtualBox – Open-source virtualization tool.

Hypervisor:

Type 1 – Runs directly on hardware.

Type 2 – Runs on host OS.


User Space – Where applications run.

Kernel Space – Where OS kernel executes.

Frontend Development – User interface (HTML, CSS, JS).

Backend Development – Server-side logic (databases, APIs).

API – Application Programming Interface.

DevOps – Combines software development & IT operations.



---

10. Networking Tools

DNS – Domain Name System (maps domain to IP).

VPN – Virtual Private Network (secure connection over public networks).

DSL – Digital Subscriber Line (internet over phone lines).

DPDK – Data Plane Development Kit (fast packet processing).

SR-IOV – Single Root I/O Virtualization (sharing PCI devices).



---

11. Emerging Technologies

Blockchain – Distributed ledger technology.

Cryptocurrency – Digital currency (e.g., Bitcoin).

BRAVE Software – Privacy-focused browser.

Latency – Delay in data transmission.

Throughput – Amount of data transferred per unit time.



1. CERN – The Birthplace

In 1989–1990, at CERN (the European Organization for Nuclear Research in Switzerland), a scientist named Tim Berners-Lee proposed a system for sharing research documents over the internet.
This system became the World Wide Web.


---

2. The Web – The Big Idea

The World Wide Web is not the same as the internet.

Internet = global network of connected computers.

Web = an information system on top of the internet, using documents linked by hyperlinks.


The Web needed two main technologies to work:


---

3. HTML – The Language

HTML (HyperText Markup Language) is the document format of the Web.

It describes the structure of a web page (headings, paragraphs, links, images, etc.).

Berners-Lee created the first version of HTML at CERN.



---

4. HTTP – The Protocol

HTTP (HyperText Transfer Protocol) is the set of rules for how a browser requests a web page from a server, and how the server sends it back.

It’s like the postal system for HTML pages.

Berners-Lee also created the first version of HTTP at CERN.



---

📌 In short:

CERN: Where Tim Berners-Lee invented the Web.

Web: The system for linking & sharing documents online.

HTML: The format of those documents.

HTTP: The protocol for transferring those documents between browsers and servers.



---

Virtual Machines (VMs)

Definition: Software emulation of a physical computer.

Runs on: Hypervisor (VMware, VirtualBox).

Key Features:

Isolation (each VM separate)

Flexibility (multiple OS on same hardware)

Portability (move VMs across systems)


Uses: Testing, server virtualization, running legacy software.



---

🔹 VirtualBox

Type: Open-source hypervisor by Oracle.

Function: Runs multiple guest OS on a single host machine.

Key Points:

Cross-platform (Windows, macOS, Linux, Solaris).

Supports snapshots (restore points).

Example use: Run Linux on Windows without dual boot.




---



Containers

Definition: Lightweight, isolated environments for applications.

Difference from VM: Share host OS kernel (not full OS).

Popular Tool: Docker, Kubernetes.

Advantages:

Faster startup (no full OS boot).

Portable (same container runs anywhere).

Efficient (less resource usage).


Use Case: Microservices deployment, DevOps.



---

🔹 Digital Signal Processing (DSP)

Definition: Processing signals (audio, video, sensor data) using digital computers.

Operations: Sampling, Filtering, Compression, Fourier Transform.

Applications:

Audio processing (MP3, noise reduction).

Image processing (JPEG, medical imaging).

Communications (modulation, error correction).




Data Structures & Algorithms (DSA)

Data Structure: Way of organizing data.

Types:

Linear (Array, Linked List, Stack, Queue)

Non-linear (Tree, Graph, Hash Table)



Algorithm: Step-by-step procedure to solve a problem.

Importance: Optimizes memory, time, performance.



---

🔹 Some Basic Algorithms & Applications

1. Sorting Algorithms:

Bubble Sort → Simple, educational use.

Merge Sort → Efficient O(n log n), used in databases.

Quick Sort → Fast average case, used in system libraries.

Heap Sort → Priority queue applications.



2. Searching Algorithms:

Linear Search → Small datasets.

Binary Search → Large sorted datasets (O(log n)).


3. Graph Algorithms:

Dijkstra’s Algorithm → Shortest path (maps, routing).

Kruskal’s / Prim’s Algorithm → Minimum spanning tree (network design).

BFS & DFS → Pathfinding, AI, web crawling.



4. Dynamic Programming (DP):

Fibonacci Sequence → Efficient computation.

Knapsack Problem → Resource optimization.



5. Greedy Algorithms:

Huffman Coding → Data compression.

Activity Selection → Scheduling.



6. Divide and Conquer:

Merge Sort, Quick Sort → Efficient problem solving.

Binary Search → Fast searching.



---
🔹 1. What is System Design?

Definition: Process of defining architecture, components, interfaces, and data flow for building scalable systems.

Goal: Handle scalability, reliability, maintainability, performance.



---

🔹 2. Key Concepts

Scalability → Handle growth (horizontal vs vertical).

Reliability → System continues to work under failures.

Availability → % of time system is up (e.g., 99.9%).

Latency → Delay in response.

Throughput → Requests/sec system can handle.

Fault Tolerance → Ability to recover from failures.



---

🔹 3. System Components

Client → Frontend (browser, mobile).

Server → Backend services.

Database → SQL (structured) vs NoSQL (unstructured, scalable).

Cache → Redis, Memcached (reduce latency).

Load Balancer → Distributes traffic across servers.

Message Queue → Kafka, RabbitMQ (async processing).

CDN (Content Delivery Network) → Speeds up static content delivery.



---

🔹 4. Design Principles

Modularity → Break into services (Microservices).

Loose Coupling → Services interact but are independent.

High Cohesion → Each module does one job well.

Consistency vs Availability (CAP Theorem):

Consistency → Same data everywhere.

Availability → System responds always.

Partition Tolerance → Works despite network failures.




---

🔹 5. Steps in System Design (Interview/Planning)

1. Clarify requirements → Functional & non-functional.


2. Estimate scale → QPS, storage size, peak traffic.


3. Choose architecture → Monolith / Microservices.


4. Database design → SQL, NoSQL, sharding, replication.


5. Caching → Where to reduce latency.


6. Load balancing → Single point of entry.


7. Data flow diagram → High-level interactions.


8. Security → Authentication, Authorization, Encryption.


9. Monitoring → Logs, alerts, metrics.




---

🔹 6. Common System Design Examples

URL Shortener (TinyURL) → Hashing + DB + Cache.

Chat App (WhatsApp) → Real-time, message queue, pub-sub.

E-commerce System (Amazon) → Catalog, Cart, Payment, Recommendation.

Video Streaming (YouTube/Netflix) → CDN, Chunking, Distributed Storage.



---

✅ Quick Recap (Keywords)

Scalability, Reliability, Latency, Throughput, Fault tolerance

Components → Client, Server, DB, Cache, Load Balancer, Queue, CDN

Principles → Modularity, Loose Coupling, CAP Theorem

Steps → Clarify, Estimate, Architecture, DB, Cache, Load balancing, Security, Monitoring

Examples → URL shortener, Chat app, E-commerce, Video streaming


---







# Cloud Computing (19/08/25 to 2/09/25) 
# Creating VM in AWS

Step-by-Step Guide to Launching a VM (EC2 Instance)
​Sign in to the AWS Management Console: First, you need an AWS account. If you don't have one, you can create one. AWS offers a free tier that allows you to use certain resources for a limited time at no cost.


​Navigate to the EC2 Dashboard: From the AWS Management Console, find and select the EC2 service. You can use the search bar at the top for a quick search.


​Launch a New Instance: On the EC2 dashboard, click the "Launch Instance" button. This will start the configuration wizard.


​Name and Configure Your Instance:
​Name: Give your instance a descriptive name.


​Application and OS Images (AMI): Choose an Amazon Machine Image (AMI), which is a template containing the operating system and other software you need. Look for those labeled "Free tier eligible" if you're using a free account.


​Instance Type: Select the instance type, which determines the VM's hardware (CPU, memory, storage). For free-tier users, the t2.micro or t3.micro instance types are often recommended.


​Key Pair: A key pair is essential for securely connecting to your instance. You can create a new key pair or use an existing one. Make sure you download and save the private key file (.pem or .ppk) in a secure location, as you won't be able to download it again.


​Network Settings:
​Firewall (Security Group): Configure a security group, which acts as a virtual firewall for your instance. You'll set inbound rules to specify what traffic is allowed to reach your VM (e.g., SSH for Linux or RDP for Windows).


​Configure Storage:
​Storage: Specify the size of the root volume (the main disk for the OS). The free tier typically includes up to 30 GB of Amazon Elastic Block Store (EBS) storage.

​Review and Launch:


​Review all your selections to ensure they meet your requirements.


​Click "Launch instance" to create your VM. The instance will take a few minutes to boot up and become ready.


​Connect to Your Instance:
​Once the instance status is "running," you can connect to it. Select your instance and click the "Connect" button at the top.




# Use of PuTTy in connecting VM

​1. Connect to your instance using PuTTY
​To connect, you'll need the Public IPv4 address of your EC2 instance and the .ppk file you created from your private key.


​In PuTTY, enter the Public IPv4 address of your instance in the Host Name (or IP address) field.
​Navigate to Connection > SSH > Auth.


​Click Browse and select your .ppk key file.


​Click Open. When prompted, enter the username for your instance (e.g., ec2-user for Amazon Linux).


​2. Install a web server
​Once you are connected to the instance's command line, you need to install a web server. The following commands are for Amazon Linux 2.

# Commands to follow while creating "hello world" webpage
1. sudo apt install apache2
2. cd /var/www/html/
3. ls
4. sudo rm index.html
5. sudo vi index.html
6. Press Shift 'i'
7. <html>
        hello world
   </html>
8. Press ctrl+c and then write :wq
9. Refresh the webpage


# Mapping the server with Domain Name


🌐 Mapping Domain Name with AWS VM (EC2) – With Elastic IP

🔹 1. Register Domain

Register from Route 53, GoDaddy, Namecheap, etc.
---

🔹 2. Launch & Configure EC2 (VM)

Start an EC2 instance (Linux/Windows).

Assign an Elastic IP (static public IP → won’t change after reboot).

Go to EC2 → Elastic IPs → Allocate → Associate with EC2 instance.




---

🔹 3. Configure Security Group (Firewall)

Open necessary ports in EC2 Security Group:

80 (HTTP)

443 (HTTPS)

22 (SSH) for Linux OR 3389 (RDP) for Windows (only for admin).




---

🔹 4. Web Server Setup

Install a server (if needed):

Linux: Apache (sudo apt install apache2), Nginx, etc.

Windows: IIS.


Test by entering Elastic IP in browser → should load default server page.



---

🔹 5. Configure DNS (Domain → Elastic IP)

Case A: Using AWS Route 53

1. Go to Route 53 → Hosted Zones → Create Hosted Zone.


2. Add a Record Set:

Type: A Record

Name: @ (for root domain) or www (for subdomain).

Value: Elastic IP of EC2.



3. Copy NS (Name Server) records from Route 53.


4. Update domain registrar with these NS records.




# Creating/Adding Containers in AWS VM server

1. Pre-requisites

AWS EC2 VM (Ubuntu recommended)

sudo access

Update packages:

sudo apt update && sudo apt upgrade -y



---

2. Install Docker

sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker $USER

✅ Verify: docker --version
✅ Test: docker run hello-world




---

3. Install VirtualBox

sudo apt install -y virtualbox virtualbox-ext-pack

✅ Verify: vboxmanage --version


---

4. Install Minikube

curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

✅ Verify: minikube version


---

5. Start Minikube (with Docker driver inside AWS VM)

minikube start --driver=docker

(If Docker not supported, fallback to VirtualBox)

minikube start --driver=virtualbox

✅ Verify cluster:

kubectl get nodes


---

6. Install kubectl (K8s CLI)

sudo snap install kubectl --classic

✅ Verify: kubectl version --client


---

7. Quick Flow

Container Runtime → Docker

VM Option → VirtualBox

Cluster Orchestration → Minikube (single-node K8s on AWS VM)



---





