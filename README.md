Digital Signature

This program is a reduced version of a digital signature using SHA-256 as the hashing algorithm (the receiver compares the sender's hash
with his/her own hash to verify the signature) and RSA to create the signature. I have uploaded a picture of the building blocks (bb.png).

Design and Implementation

Signing process:
1. Bob generates a message (user input)
2. Bob generates hash value for the message (SHA-256 with arbitrary length input.
3. Bob uses the hash value together with a private key as input for RSA algorithm.
4. Bob sends the message with RSA signature attached.
Verification process:
1. Alice receives the message with signature.
2. Alice calculates a hash value for the received message, just as Bob did in step 2 of the signing process (SHA-256 with arbitrary length
input).
3. Alice provides the received encryption and Bob’s public key as input for decryption.
4. Alice compares the RSA decryption with her calculated hash value for the received message. If the algorithm returns the result that the 
signature is valid (which in this case it is, because Alice’s decrypted hash matches Bob’s original hash), Alice is assured that the 
message has been signed by Bob, because nobody else has his private key, so nobody else could have created a signature for this message 
that could be verified for this message using Bob’s key.

How to Run - Input:

String (message signed by Alice and sent from Alice to Bob)

Test Results

Input (message): test, gives the following output:
Bob's hash in String: 9F86D081884C7D659A2FEAA0C55AD015A3BF4F1B2B0B822CD15D6C15B0F00A08
Encrypting Bob's hash: 9F86D081884C7D659A2FEAA0C55AD015A3BF4F1B2B0B822CD15D6C15B0F00A08
Bob's hash in Bytes: 5770565468485649565652675568545357655070696565486753536568484953655166705270496650664866565050676849536854674953664870
4848654856
Bob's encrypted Hash: 6D02F9384B4A7936ADD6EBE9914FD5E51CCC42A4872A7E376E557D291EBA59AD7077C48072DE1F30B5794A3CFF241553DEE1240510DDCE1BDCC57
A8D83C29E15E0208F72EA187A2C7026A1706071A75BA19C37BCBAA64CA7BC67BAE9D852AD74B6ED87E62256E4320CFC2151B86DF4ECAFFFD75CA97973B91F3E2EE1497A4
8C700CB0A714D02E67C1C03FE09FB9CB4784441A2DC833EDD5BA53BA16CBF0723153057834487CA0AF79BC44CBD757AC8738115306229E88C491BC10263D0B535482BCB9
7F7AA4397314D0DD69C24EA2A3C64F135E1C5025A2A45906D754D68942FF5DA3FDF4B3ACA3C8C699D3362EC3F700BE272C1CA10A0608B391B779ED1C0E0
Alices' hash in String: 9F86D081884C7D659A2FEAA0C55AD015A3BF4F1B2B0B822CD15D6C15B0F00A08
Alices' decrypted Hash in bytes: 5770565468485649565652675568545357655070696565486753536568484953655166705270496650664866565050676849536
8546749536648704848654856
Alices' decrypted Hash in String: 9F86D081884C7D659A2FEAA0C55AD015A3BF4F1B2B0B822CD15D6C15B0F00A08
Verification successfull! Alices' decryption matches her calculated hash -> The message is signed by Bob!
