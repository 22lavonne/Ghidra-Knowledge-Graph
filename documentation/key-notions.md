<!-- 
Identify a thorough list of key notions.

    For each key notion, explain the rationale of why it is a key notion.
    For each key notion or set of key notions, identify a pattern which can be used to model them, otherwise indicate that there is no existing pattern.
        Draft an instantiation of the pattern (a module) based on the use-case, where possible.
        For key notions with no pattern, draft a module which would model them.
    Connect the key notion to where the data is coming from. For example, if an Event is a key notion, which piece of the identified datasets are used to populate the module.
        Occasionally there will be controlled vocabularies. These are not technically patterns, but are a list of individuals that are important (and will not change). Indicate which key notions behave as such and their list of individuals.
-->

# Key Notions (Modules)

<!--
* Key Notion
    * Rationale: rationale
    * Connected Pattern: pattern name (pattern source)
    * Source Dataset(s): dataset n, dataset n+1
* Key Notion
    * Rationale: rationale
    * Connected Pattern: pattern name (pattern source)
    * Source Dataset(s): dataset n, dataset n+1
* Key Notion
    * Rationale: rationale
    * Connected Pattern: pattern name (pattern source)
    * Source Dataset(s): dataset n, dataset n+1

-->
## Symbol
### Description
A symbol is a named entity in an executable file that is associated with a specific memory address. A symbol can have one or more references, but only one reference is designated as the primary.

![Symbol](../Schema/schema_diagram_images/symbol_schema.png)
### Axioms
* `Symbol hasReference min 0 Reference` <br />
"A symbol has 0 or more references"
* `Symbol hasPrimaryReference min 0 max 1 Reference` <br />
"A symbol has up to one primary reference"
* `Symbol superClassOf Class` <br />
"A class is a type of symbol"
* `Symbol superClassOf Function` <br />
"A function is a type of symbol"
* `Symbol superClassOf Variable` <br />
"A variable is a type of symbol"
* `Symbol superClassOf Namespace` <br />
"A namespace is a type of symbol"
* `Symbol superClassOf Label` <br />
"A label is a type of symbol"
* `Symbol superClassOf Import` <br />
"An import is a type of symbol"
* `Symbol superClassOf Export` <br />
"An export is a type of symbol"

## Reference
### Description
A reference is where two memory addresses interact in some way with each other, where one address uses another. This is used for things like when a function calls another function or when data is accessed by an instrution. References are 4-tuples, which include the source address, destination address, the type of reference (function call, data being accessed, etc.), and the operand index (which is an int that is either -1, 0, or 1).

![Reference](../Schema/schema_diagram_images/reference_schema.png)
### Axioms
* `Reference hasSourceAddress address exactly 1 sourceAddress` <br />
"A reference has exactly one source address"
* `Reference hasDestinationAddress address exactly 1 destinationAddress` <br />
"A reference has exactly one destination address"
* `Reference hasType xsd:string exactly 1 type` <br />
"A reference has exactly one reference type indicated by a string"
* `Reference hasOperandIndex xsd:integer exactly 1 index` <br />
"A reference has exactly one operand index indicated by an integer"

## Address
### Description
An object that holds the Memory address of a given symbol. It's an object itself so it can point to other objects.

![Address](../Schema/schema_diagram_images/address_schema.png)

### Axioms
* `Address pointsTo Symbol exactly 1 Symbol` <br />
"An address points to exactly one symbol"
* `Address addressOf xsd:string` <br />
"An address refers to a memory address represented by a string"

## Import/Export
### Description
Imports allow files to use outside functions within the current file through dynamic link libraries (DLLs). Exports allow other files to use the functions from the current file through DLLs. The imports and edxports are important to look at to see if anything imported or exported is either vulnerable or is similar to other malware behavior, as they can direclty affect the safety of the other files in the supplu chain.

![Import/Export](../Schema/schema_diagram_images/import_export_schema.png)
### Axioms
* `Import subClassOf Symbol` <br />
"Every import is a symbol"
* `Export subClassOf Symbol` <br />
"Every export is a symbol"
* `Import declares min 0 DLL` <br />
"Every import declares 0 or more DLLs"
* `Export declares min 0 DLL` <br />
"Every export declares 0 or more DLLs"
* `Import hasLabel Label exactly 1 label` <br />
"Every import has exactly one label"
* `Export hasLabel Label exactly 1 label` <br />
"Every export has exactly one label"

## Function
### Description
Keeps track of all the aspects of a function, including the variables passed in (parameters), the local variables defined in the function, the return type of the function, the return variable of the function, and the label that the function has.

![Function](../Schema/schema_diagram_images/function_schema.png)

### Axioms
* `Function subClassOf Symbol` <br />
"Every function is a symbol"
* `Function hasLabel Label exactly 1 label` <br />
"Every function has exactly one label"
* `Function hasReturnType DataType min 0 max 1 datatype` <br />
"Every function has either no return type (void) or one return type"
* `Function returns min 0 max 1 variable` <br />
"Every function returns either no variables or one variable"
* `Function declaresLocalVariable min 0 Variable` <br />
"A function can declare 0 or more local variables"
* `Function hasParameter min 0 variable` <br />
"A function can pass in 0 or more parameters"
* `Function calls min 0 Function` <br />
"A function can call 0 or more other functions"
* `Function calledBy min 0 Function` <br />
"A function can be called by 0 or more other functions"
* `Function definedIn class exactly 1 Class` <br />
"A function is defined in exactly one class"
* `Function definedIn namespace min 1 Namespace` <br />
"A function is defined in one or more namespaces"

## Variable
### Description
Keeps track of all the informtion about a variable, including what kind of variable it is (parameter vs local variable vs global variable), what label it has, and its data type.

![Variable](../Schema/schema_diagram_images/variable_schema.png)
### Axioms
* `Variable subClassOf Symbol` <br />
"Every variable is a symbol"
* `Variable definedIn Namespace min 1 Namespace` <br />
"Every variable is defined in at least one namespace"
* `Variable definedInGlobalNamespace extactly 1 Namespace` <br />
"Every variable is defined in the global namespace"
* `Variable localaVariableDefinedIn Class exactly 1 Class` <br />
"Every local variable is defined in a class"
* `Variable hasLabel Label exactly 1 Label` <br />
"Every variable has exactly one label"
* `Variable hasDataType DataType exactly 1 Datatype` <br />
"Every variable has exactly one data type"

## Data Type
### Description
An object that signifies the data type of a variable, or the return type of a function.

![DataType](../Schema/schema_diagram_images/datatype_schema.png)

### Axioms
* `Data Type hasDataTypeName xsd:string exactly 1 name` <br />
"Data type has exactly one data type name indicated by a string"

## Class
### Description

![Class](../Schema/schema_diagram_images/class_schema.png)

### Axioms
* `Class subClassOf Symbol` <br />
"Every class is a symbol"
* `Class definesFunction Function min 0 Function` <br />
"Every class defines 0 or more functions"
* `Class hasLabel Label exactly 1 Label` <br />
"Every class has exactly one label"
* `Class definesLocalVariable variable min 0 variable` <br />
"Every class defines 0 or more local variables"
* `Class definedIn Namespace min 1 Namespace` <br />
"Every class is defined in at least one namespace"


## Label
### Description
Contains a human readable label for a symbol (function, variable, etc.). Contains the string of the name of the label and the memory address the label points to.

![Label](../Schema/schema_diagram_images/label_schema.png)
### Axioms
* `Label subClassOf Symbol` <br />
"Every label is a symbol"
* `Label hasName xsd:string exactly 1 name` <br />
"Every label has exactly one name indicated as xsd:string"
* `Label hasAddress Address exactly 1 address` <br />
"Every label has exactly one memory address"

## Namespace
### Description
Namespaces group together symbols like functions and classes to make sure there is no naming conflicts within the same scope. Namespaces can hold functions, variables, classes, and other namespaces. Namespaces cannot share names, and classes cannot share names with namespaces.

![Namespace](../Schema/schema_diagram_images/namespace_schema.png)
### Axioms
* `Namespace subClassOf Symbol` <br />
"Every namespace is a symbol"
* `Namespace contains min 0 Symbol` <br />
"Every name space contains at least 0 or more symbols"
* `Namespace hasName xsd:string exactly 1 name` <br />
"Every namespace has exactly one name indicated by xsd:string"

## Overall Schema Diagram
![Schema](../Schema/schema_diagram_images/schema.png)