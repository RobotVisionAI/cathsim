## Overview
This project provides a simulation for a MuJoCo guidewire model, specifically focusing on creating an XML representation of the model. MuJoCo stands for "Multi-Joint dynamics with Contact," and it's a physics engine for detailed, efficient rigid body simulations with contacts.

## Features
### Guidewire Model Representation
The core of this project is the `GuidewireModel` class. It serves to represent the MuJoCo guidewire model and comes with methods for creating and saving its XML representation.

### Static Constants
The `GuidewireModel` class consists of various constants representing parameters of the guidewire, like its scale, density, length, and so on. These parameters are used to create a detailed XML representation of the model.

### Environmental Options
The model also takes into account certain properties of human blood, such as density and viscosity, which are represented as environment options.

### XML Representation
The primary method, `create_guidewire`, is responsible for generating an XML structure that describes the guidewire model with its elasticity properties. This XML structure integrates the MuJoCo elasticity plugin to realistically simulate the behaviour of the guidewire.

### Prettify XML
The `prettify_xml` static method makes the XML string more readable by beautifying it.

### XML File Creation
Once the XML representation is generated and prettified, it can be saved into a file using the `create_xml_file` method.

## How to Use
Simply run the script. Upon execution, the XML representation of the guidewire model will be generated. If successful, the representation will be printed to the console and saved into an XML file named `guidewire_model.xml`.

## Error Handling
The script comes with basic error handling. If any unexpected issues occur during XML generation, prettification, or file writing, an error message will be printed to the console.

## Contributions
Please ensure that any changes or improvements made adhere to the structure and constants established in the `GuidewireModel` class. Submit a pull request with detailed comments on your changes.

## License
Please feel free to copy, distribute, display, perform, or remix our work but for non-commercial proposes only.