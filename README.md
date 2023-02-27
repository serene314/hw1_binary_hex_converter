# hw1_binary_hex_converter
num_decimal = int(input("Enter a number from 0 to 255: "))
num_binary = 0
a = 0
b = 0
hex_two = 0
hex_one = 0

for i in range(8):
    if num_decimal // 2**(7-i) == 1:
       num_binary += 10**(7-i)
       num_decimal -= 2**(7-i)

binary_bef = num_binary // 10000
binary_aft = num_binary % 10000

for j in range(4):
    if binary_bef // 10**(3-j) == 1:
        a += 2**(3-j)
        binary_bef -= 10**(3-j)
if a == 10:
    hex_two = 'A'
elif a == 11:
    hex_two = 'B'
elif a == 12:
    hex_two = 'C'
elif a == 13:
    hex_two = 'D'
elif a == 14:
    hex_two = 'E'
elif a == 15:
    hex_two = 'F'
else:
    hex_two = a

for k in range(4):
    if binary_aft // 10**(3-k) == 1:
        b += 2**(3-k)
        binary_aft -= 10**(3-k)
if b == 10:
    hex_one = 'A'
elif b == 11:
    hex_one = 'B'
elif b == 12:
    hex_one = 'C'
elif b == 13:
    hex_one = 'D'
elif b == 14:
    hex_one = 'E'
elif b == 15:
    hex_one = 'F'
else:
    hex_one = b

print("binary: %d" %num_binary)

if hex_two == 0:
    print("hex: %s" %hex_one)
else:
    print("hex: %s%s" %(hex_two, hex_one))
