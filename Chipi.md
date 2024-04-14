Chipi is the scripting language that will be used to expend the functionality of the Texty editor. Code written in Chipi will be [[Interpreters|interpreted]] by the Texty program and executed at cretin event via hooks.

# Chipi version 1 design
Here are the design principles of Chipi:
* Functional.
* Expression only.
* Configurable memory management modes.

## Into Chipi
### Functions
every function in Chipi is comprised out of 3 parts:
* input parameters
* output parameters
* name
here is an example for a Chipi function:
```
func[in]->[out]
func[in]->[out1,out2]
func[in1,in2]->[out1,out2]
```
#### Out parameter grouping handling
In Chipi if you wish to group 2 parameters together under a shared structure in the return value you may declare a structure in the return values.
```
func[in1,in2]->[out:(out1,out2)]
```
In this example a struct is defined in the return arguments and is comprised out of 2 fields "out1" and "out2".

#### Optional values and error handling
In order to handle errors in Chipi will implement optional value return values.
Optional return values are denoted with the '|' character.
```
func[in1,in2]->[out1|out2]
func[in1,in2]->[err|out]
func[in1,in2]->[err|out:(out1,out2)]
```