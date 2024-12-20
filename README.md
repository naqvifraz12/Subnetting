#quick code I wrote to practice python again
#allows you to enter an ip address with the network portion to calculate number of subnets and hosts
#you will have to make sure input is valid, as input validation was not coded for
#thank you for viewing



ip_address = input("Enter IP Address: ");
subnet_mask = input("Enter Subnet Mask as CIDR integer: ");

network = 0

octets = ip_address.split(".")
first_octet = int(octets[0])

subnet_mask_int = int(subnet_mask)

if 1 <= first_octet <= 127:
        network = 8
elif 128 <= first_octet <= 191:
         network = 16
elif 192 <= first_octet <= 223:
         network = 24
elif 124 <= first_octet <= 239:
         network = 0
elif 240 <= first_octet <= 255:
         network = 0
        
subnets = subnet_mask_int - network
 
if subnets == 0:
    subnets = 1
elif subnets == 1:
     subnets = 2
elif subnets > 1:
    subnets = subnets*subnets 
        
counter = 32 - subnet_mask_int

hosts = counter*counter



print(f"IP Address: " + ip_address)
print(f"Subnet Mask " + str(subnet_mask_int))
print(f"Number of Subnets: " + str(subnets))
print(f"Number of Hosts " + str(hosts))
