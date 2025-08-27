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


