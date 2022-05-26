# Digital-Signature-RSA

## Generate Key 
Function              | Variable      | Definitions
--------------------- | ------------- |----------------------
Generate_private_key  | Public_expornent | The public exponent of the new key. Usually one of the small Fermat primes 3, 5, 17, 257, 65537. If in doubt you should use    65537.
-| Key_Size | The length of the modulus in bits. It must not be less than 512.
-| Back_end | Back end return by RSAbackend.

## Signing Document
Function              | Variable      | Definitions
--------------------- | ------------- |----------------------
Load_pem_private_key()  | Data = key_file.read() | The PEM encoded key data.
-| Password = None | The password to use to decrypt the data. Should be None if the private key is not encrypted.
-| Backend = default_backend() | An instance of PEMSerializationBackend.
Private_key.sign()| Payload | Input File
-| mgf | Mask generation from hash SHA256.
-| salt_length | Max length of the salt length.

## Verifying Signature
Function              | Variable      | Definitions
--------------------- | ------------- |----------------------
load_pem_public_key()  | public_key | Load the public key from the “public.pem” file.
public_key.verify()| payload_contents | Content of the file.
-| signature | Content of the signature file.
-| mgf | Mask generation from hash SHA256.
-| salt_length | Max length of the salt length.
