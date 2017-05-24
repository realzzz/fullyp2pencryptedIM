# fullyp2pencryptedIM
A fully encrypted p2p communication IM design. 


 Basic idea is using the asymmetric encryption, same idea as the digital signature. 
 


# Bascially: 
1. Server has a unique public/private key pair for every user.
2. All client has its public/private key, run as a user.

# Scenario:

## Register
For first time/renew key case - generate the public/private key and send to server for register, client send over a message that is given by server + generated random string (encrypt by client private key then server public key), Server needs to verify if this public key is actually yours ( By decrypt the message and check message and comfirm by encrypt client ramdom string first using server private key then using client public key)

## Query for other client key
For client key check case, for each client id -> all other client may ask for there public key. (Transfer is encrypted)

## Client talk
After client gets other client's public key, they may start talking - this most likely done in p2p, but server transfer may also be a good choice to hide client's information

## Images/Videos
By consideration of efficiency these may be encrypted via a common password negoticated through the talk. Or it can be splited into different pieces to transfer. 



# More consideration of security:
These only consider p2p case, well we can certainly run the same sceario through a longer chain. Here is an example:

A talks to B, but after A's message encrypted using both A And B's keys, the data needs to go through C, D, E, ... user firstly. (By encrpted using C,D,E's public key) then run to B. These message transfer makes a centerless communication network which shall be hard to be tracked. 


# More to come. 
