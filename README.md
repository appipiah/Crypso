# Crypso
30-30 python challenge ( CHALLENGE 19)
SOURCE CODE:

print("CRYPSO")
print("SOFTWARE ENCRYPTION \n...Offers high level protection for data!")
choice = int(input("\n\t\tFor Encryption, enter (1)\n\t\tFor Decryption, enter (2): "))


def encryption():
    code = input("\nEnter four digit password: ")
    if (len(code) != 4) or (code.isnumeric() is not True):

# Comparison to True should be 'if condition is not True'- HINT I GOT

        print("\n\tError! Code to be encrypted must be numeric and 4 digits long!")
        exit()
    code_list = [int(i) for i in code]
    code_list = [(i + 7) % 10 for i in code_list]
    code_list[0], code_list[2] = code_list[2], code_list[0]
    code_list[1], code_list[3] = code_list[3], code_list[1]
    print("\nEncrypted code: ", "".join(str(i) for i in code_list))


def decryption():
    code = input("\nEnter four digit password: ")
    if (len(code) != 4) or (code.isnumeric() is not True):
        print("Error! Code to be decrypted must be numeric and 4 digits long!")
        exit()
    code_int = [int(x) for x in code]
    code_list = []
    for number in code_int:
        if number >= 7:
            code_list.append(number - 7)
        else:
            code_list.append(number + 10 - 7)
    code_list[0], code_list[2] = code_list[2], code_list[0]
    code_list[1], code_list[3] = code_list[3], code_list[1]
    print("\nDecrypted code: ", "".join(str(x) for x in code_list))

if choice == 1:
    encryption()
elif choice == 2:
    decryption()
exit()


RESULT(S):

1.

CRYPSO
SOFTWARE ENCRYPTION 
...Offers high level protection for data!

		For Encryption, enter (1)
		For Decryption, enter (2): 1

Enter four digit password: 1234

Encrypted code:  0189

Process finished with exit code 0

2.

CRYPSO
SOFTWARE ENCRYPTION 
...Offers high level protection for data!

		For Encryption, enter (1)
		For Decryption, enter (2): 1

Enter four digit password: 00

	Error! Code to be encrypted must be numeric and 4 digits long!

Process finished with exit code 0


3.

CRYPSO
SOFTWARE ENCRYPTION 
...Offers high level protection for data!

		For Encryption, enter (1)
		For Decryption, enter (2): 2

Enter four digit password: 0189

Decrypted code:  1234

Process finished with exit code 0
