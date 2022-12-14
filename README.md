
# Hectarea's Pizza Encryption Standard


Pizza Encryption Standard is an encryption algorithm made by [Hectarea](https://hectarea.netlify.app) and [Qrab & Nell](https://qrabnell.netlify.app), based on the steps that you need to make a pizza.

The password is the Sauce, the Initial Value is the ingredients like cheese, pepperoni, peppers, and onion, and the Plain Text is the Pizza Dough

# The steps are simple

### Encryption
* The Initial Value and the Password obfuscate each byte of the plain text
* The Password randomly switches the position between pairs of Bytes inside the Byte Array
* The Password encrypts the individual bytes of the mixed-up Byte Array
* The Frozen Pizza is ready to deliver

### Decryption
* The Password decrypts individual bytes of the Frozen Pizza
* The Password switches the pairs of bytes back into their original position
* Finally the Initial Value and the Password de-obfuscate the CipherText into the original Byte Array


## Installation

```bash
pip install HectareaPES
```

# Basic Example

```python
from HectareaPES import PaneraPizza

#Encoded Plain Text
PizzaDough = b"How Big Are Panera's Flatbread Pizzas? Panera's pizzas are square-shaped and they're the perfect size for a personal pizza. They're about 11-inches long by 4-inches wide, and they're usually cut into 6 small squares, which makes it easy for portioning."

#Encoded Initial Value
Ingredients = b'Pepperoni Initial Value'

#Encoded Password
Sauce = b'Random Password'



#Encription

RolledDough = PaneraPizza.RollingPin(PizzaDough, Sauce, Ingredients)


SeasonedPizza = PaneraPizza.Mix(RolledDough, Sauce)


FrozenPizza = PaneraPizza.Freezer(SeasonedPizza, Sauce)


print("\nCipherText: \n"+str(FrozenPizza))




#Decryption

BakedPizza = PaneraPizza.Oven(FrozenPizza, Sauce)


PizzaSlices = PaneraPizza.Cutter(BakedPizza, Sauce)


PizzaSlice = PaneraPizza.Turner(PizzaSlices, Sauce, Ingredients)


print("\nPlainText: \n"+str(PizzaSlice))
```
# Result
```
CipherText: 
bytearray(b"\x88\x96\xa3\xa5ca\x17\xa4\x96\xa2x\xba\x85\xabX<l\xc3\x9f\x97\xb5\x16.\xa0\x94\xbf|\xb2\xb9Ejsi\x9b\xa8f\x0fq{\xb8\xa2\xd0\xc6\xb7\x8b2CI\x9e\xa4\xa4\'H\x85go\xb2\xb7\xc2\xa80\xa3a\xaf\xb1\xb9,p\x98g\xa6\xa9\x99mZ~\x88\xa9\xa8nK\x1f\x0bP\xb0g\xc2\x8c\xaaPM\x90\xb9\xa4\x99\x9a\xd0p\x86\xc6\xbdv\xb1e\xbf~\x9a\x92\xa3\xa6\xb3l\x88\x8c\xbd\xb9.\x14\xa0~8\xa5\x8c`\xbe\\q{\x92\xc2\xc1\xb7R\xbdQ\x90]x\x98_\x8b\x13\x82\xab\xac\xbdzt\x9cI\x85\x97a\xa5\x1ew\x19s\x9d\xb9\xc9\xca\xc3\x99\x8b{\x97eX\xa8\x1a\xca.\x9d\xaez\xa6s\xc7\x9b\x80\x8f\xafE\xaf\x1a\xea|\x93\xc3\xd1\xb7\xa1}\xa2w\x93q1\xbc\xb4\x11|\x99u\xb3\xbf_x\xa0{\x90\xc4\xa9N|\x80i\x88\xc7\xb8\xbf\xbf\xbc\x9c\x89\x98\xc0I_o\x80`\x88\xbd\xbe\xbf\xac\xbd]e\x93\xbbZ\xb2\x9e\xc5u\xa0\xd1\xb5}")


PlainText: 
bytearray(b"How Big Are Panera\'s Flatbread Pizzas? Panera\'s pizzas are square-shaped and they\'re the perfect size for a personal pizza. They\'re about 11-inches long by 4-inches wide, and they\'re usually cut into 6 small squares, which makes it easy for portioning.")
```
