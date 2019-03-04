# py4e-assignment9.4

name = input("Enter file:")
if len(name) < 1 : name = "mbox-short.txt"
handle = open(name)
counts = dict()
# preparations end here. 
# dict() should be done at the first stage

for line in handle:
    line = line.rstrip()
    if not line.startswith('From '):
        continue
    else:
        words = line.split()
        address = words[1]
# directly attach address to counts
# to make a dictionary
        counts[address] = counts.get(address, 0) +1
        # print('Counts', counts)

bigname = None
bigcount = None
for key,value in counts.items():
    if bigcount is None or value > bigcount:
        bigname = key
        bigcount = value
print(bigname, bigcount)
