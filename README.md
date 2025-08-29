# ULTIMATE-PYTHON-GUIDE
All python codes and notes uploaded here. 



---

Q1. Roots of a quadratic equation

import cmath
a, b, c = map(float, input("Enter a, b, c: ").split())
d = (b**2) - (4*a*c)
root1 = (-b + cmath.sqrt(d)) / (2*a)
root2 = (-b - cmath.sqrt(d)) / (2*a)
print("Roots:", root1, root2)


---

Q2. Prime Numbers

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


---

Q3. Pyramid and Reverse Pyramid

n = int(input("Enter rows: "))
for i in range(1, n+1): print(" "*(n-i) + "*"*(2*i-1))
for i in range(n-1, 0, -1): print(" "*(n-i) + "*"*(2*i-1))


---

Q4. Character Operations

ch = input("Enter a character: ")

if ch.isalpha():
    print("Letter - Uppercase" if ch.isupper() else "Letter - Lowercase")
elif ch.isdigit():
    names = ["ZERO","ONE","TWO","THREE","FOUR","FIVE","SIX","SEVEN","EIGHT","NINE"]
    print("Digit:", names[int(ch)])
else:
    print("Special character")


---

Q5. String Operations

s = input("Enter string: ")
print("Frequency of 'a':", s.count('a'))
print("Replace a by x:", s.replace('a', 'x'))
print("Remove first 'a':", s.replace('a', '', 1))
print("Remove all 'a':", s.replace('a', ''))


---

Q6. Swap first n characters of two strings

s1, s2, n = "hello", "world", 2
print("After swap:", s2[:n] + s1[n:], s1[:n] + s2[n:])


---

Q7. Function to return indices of substring

def find_indices(s1, s2):
    return [i for i in range(len(s1)) if s1.startswith(s2, i)] or -1

print(find_indices("banana", "na"))


---

Q8. Cubes of Even Integers

lst = [1, 2, 3, 4, 5, 6]
print([x**3 for x in lst if isinstance(x, int) and x % 2 == 0])


---

Q9. File Operations

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


---

Q10. Class Point

class Point:
    def __init__(self, x, y):
        self.x, self.y = x, y
    def __str__(self):
        return f"({self.x},{self.y})"
    def dist(self, p):
        return ((self.x - p.x)**2 + (self.y - p.y)**2)**0.5

p1, p2 = Point(1, 2), Point(4, 6)
print(p1, p2, "Distance:", p1.dist(p2))


---

Q11. Dictionary {n: n³}

print({x: x**3 for x in range(1, 6)})


---

Q12. Tuple Operations

t1 = (1, 2, 5, 7, 9, 2, 4, 6, 8, 10)

print("Half split:", t1[:len(t1)//2], t1[len(t1)//2:])
print("Even values:", tuple(x for x in t1 if x % 2 == 0))

t2 = (11, 13, 15)
print("Concatenation:", t1 + t2)

print("Max:", max(t1), "Min:", min(t1))


---







# Comprehensive Tech Notes
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

1. Physical


2. Data Link


3. Network


4. Transport


5. Session


6. Presentation


7. Application




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
