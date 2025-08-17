# Simple Python Port Scanner
import socket

target = input("Enter target IP or domain: ")
ports = range(1, 1025)  # scanning ports 1-1024

print(f"Scanning {target} for open ports...")

for port in ports:
    sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    sock.settimeout(0.5)  # short timeout
    result = sock.connect_ex((target, port))
    if result == 0:
        print(f"Port {port} is OPEN")
    sock.close()

print("Scan complete.")


# python-network-tools
Beginner-friendly Python scripts for networking and cybersecurity practice. Includes port scanner, ping sweeper, and other utilities to learn and demonstrate networking concepts.
