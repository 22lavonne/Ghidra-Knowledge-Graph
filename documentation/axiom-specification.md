<!--     
TODO:
For all the relations assigned as functionality, determine if they are
- Qualified Functionality
- Scoped functionality
- Qualified scoped functionality
- inverse functionality
- inverse qualified functionality
- inverse scoped functionality
- inverse qualified scoped
-->

## List of Axioms

| Number    | Subject       | Relationship      | Object        |
| --------- | --------      | -----------       | -----------   |
| 1         | Symbol        | hasReference      | Reference |
| 2         | Symbol        | hasPrimaryReference | Reference|
| 3         | Symbol        | superClassOf| Class|
| 4         | Symbol        | superClassOf| Function|
| 5         | Symbol        | superClassOf| Variable|
| 6         | Symbol        | superClassOf| Namespace|
| 7         | Symbol        | superClassOf| Label|
| 8         | Symbol        | superClassOf| Import|
| 9         | Symbol        | superClassOf| Export|
| 10        | Reference     | hasSourceAddress| Address|
| 11        | Reference     | hasDestinationAddress| Address|
| 12        | Reference     | hasType| xsd:string|
| 13        | Reference     | hasOperandIndex| xds:integer|
| 14        | Address       | pointsTo| Symbol|
| 15        | Address       | addressOf | xsd:string|
| 16        | Import        | subClassOf | Symbol |
| 17        | Export        | subClassOf | Symbol |
| 18        | Import        | declares | DLL|
| 19        | Export        | declares | DLL|
| 20        | Import        | hasLabel | Label |
| 21        | Export        | hasLabel | Label |
| 22        | Function      | subClassOf | Symbol |
| 23        | Function      | hasLabel | Label |
| 24        | Function      | hasReturnType | DataType |
| 25        | Function      | returns | Variable  |
| 26        | Function      | declaresLocalVariable | Variable |
| 27        | Function      | hasParameter | Variable |
| 28        | Function      | calls | Function |
| 29        | Function      | calledBy | Function |
| 30        | Function      | definedIn | Class |
| 31        | Function      | definedIn | Namespace |
| 32        | Function      | containsInstruction | Instruction |
| 33        | Variable      | subClassOf | Symbol |
| 34        | Variable      | definedIn | Namespace |
| 35        | Variable      | definedInGlobalNamespace | Namespace |
| 36        | Variable      | localVariableDefinedIn | Class |
| 37        | Variable      | hasLabel | Label |
| 38        | Variable      | hasDataType | Datatype |
| 39        | Data Type     | hasDataTypeName | xsd:string|
| 40        | Class         | subClassOf | Symbol |
| 41        | Class         | definesFunction | Function |
| 42        | Class         | hasLabel | Label |
| 43        | Class         | definesLocalVariable | Variable |
| 44        | Class         | definedIn | Namespace |
| 45        | Label         | subClassOf | Symbol |
| 46        | Label         | hasName | xsd:string|
| 47        | Label         | hasAddress | Address |
| 48        | Namespace     | subClassOf | Symbol |
| 49        | Namespace     | declares| Symbol|
| 50        | Symbol        | declaredBy| Namespace|
| 51        | Namespace     | hasName | xsd:string |
| 52        | Instruction   | hasOpcode | Opcode |
| 53        | Instruction   | hasSourceOperand | Operand |
| 54        | Instruction   | hasDestinationOperand | Operand |
| 55        | Address       | performsRole | Operand |
| 56        | Register      | performsRole | Operand |
| 57        | ImmediateOperand| performsRole | Operand |
| 58        | Symbol        | performsRole | Operand |



## Axiom Selection

### Symbol

|                                           | 1  | 2  | 3  | 4  | 5  | 6  | 7  | 8  | 9  | 
| ---------                                 |----|----|----|----|----|----|----|----|----|
| Subclass                                  |    |    |    |    |    |    |    |    |    |
| Class disjointness                        |    |    |    |    |    |    |    |    |    |  
| Domain                                    |    |    |    |    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |    |    |    |
| Range                                     |    |    |    |    |    |    |    |    |    |
| Scoped range                              |    |    |    |    |    |    |    |    |    |
| Existential                               |    |    |    |    |    |    |    |    |    |
| Inverse existential                       |    |    |    |    |    |    |    |    |    |
| Functionality                             |    | x  |    |    |    |    |    |    |    |
| Qualified functionality                   |    |    |    |    |    |    |    |    |    |
| Scoped functionality                      |    |    |    |    |    |    |    |    |    |
| Qualified scoped functionality            |    | x  |    |    |    |    |    |    |    |
| Inverse functionality                     |    |    |    |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |    |    |    |
| Structural tautology                      | x  | x  |    |    |    |    |    |    |    |
|                                           |    |    |    |    |    |    |    |    |    |
| For the Property                          |    |    |    |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |    |    |    |
| Asymmetry                                 | x  | x  | x  | x  | x  | x  | x  | x  | x  |
| Transitivity                              | x  | x  | x  | x  | x  | x  | x  | x  | x  |
| Reflexivity                               |    |    |    |    |    |    |    |    |    |
| irreflexivity                             | x  | x  | x  | x  | x  | x  | x  | x  | x  |

### Reference and Address

|                                           | 10 | 11 | 12 | 13 | 14 | 15 | 
| ---------                                 |----|----|----|----|----|----|
| Subclass                                  |    |    |    |    |    |    |
| Class disjointness                        |    |    |    |    |    |    |
| Domain                                    |    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |
| Range                                     | x  |    |    |    |    |    |
| Scoped range                              |    |    |    |    |    |    |
| Existential                               | x  | x  |    | x  |    |    |
| Inverse existential                       |    |    |    |    |    |    |
| Functionality                             | x  | x  | x  | x  | x  | x  |
| Qualified functionality                   |    |    |    |    |    |    |
| Scoped functionality                      |    |    | x  | x  |    | x  |
| Qualified scoped functionality            | x  | x  |    |    | x  |    |
| Inverse functionality                     |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |
| Structural tautology                      |    |    |    |    | x  | x  |
|                                           |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |
| Asymmetry                                 | x  | x  | x  | x  | x  | x  |
| Transitivity                              |    |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |    |
| irreflexivity                             | x  | x  | x  | x  | x  | x  |

### Import and Export

|                                           | 16 | 17 | 18 | 19 | 20 | 21 | 
| ---------                                 |----|----|----|----|----|----|
| Subclass                                  | x  | x  |    |    |    |    |
| Class disjointness                        |    |    |    |    |    |    |
| Domain                                    |    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |
| Range                                     |    |    |    |    | x  | x  |
| Scoped range                              |    |    | x  | x  |    |    |
| Existential                               |    |    |    |    |    |    |
| Inverse existential                       |    |    |    |    |    |    |
| Functionality                             |    |    |    |    | x  | x  |
| Qualified functionality                   |    |    |    |    | x  | x  |
| Scoped functionality                      |    |    |    |    |    |    |
| Qualified scoped functionality            |    |    |    |    | ?  | ?  |
| Inverse functionality                     |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |
| Structural tautology                      |    |    |    |    | x  | x  |
|                                           |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |
| Asymmetry                                 | x  | x  | x  | x  | x  | x  |
| Transitivity                              |    |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |    |
| irreflexivity                             | x  | x  | x  | x  | x  | x  |


### Function

|                                           | 22 | 23 | 24 | 25 | 26 | 27 | 28 | 29 | 30 | 31 | 32 |
| ---------                                 |----|----|----|----|----|----|----|----|----|----|----|
| Subclass                                  | x  |    |    |    |    |    |    |    |    |    |    |
| Class disjointness                        |    |    |    |    |    |    |    |    |    |    |    |  
| Domain                                    |    |    |    |    |    |    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |    |    |    |    |    |
| Range                                     |    | x  | x  | x  | x  | x  |    |    |    |    | x  |
| Scoped range                              |    |    |    |    |    |    |    |    |    |    |    |
| Existential                               |    |    |    |    | x  | x  |    |    |    |    | x  |
| Inverse existential                       |    |    |    |    |    |    |    |    |    |    |    |
| Functionality                             |    | x  | x  | x  |    |    |    |    | x  |    |    |
| Qualified functionality                   |    | x  | x  | x  |    |    |    |    |    |    |    |
| Scoped functionality                      |    |    |    |    |    |    |    |    |    |    |    |
| Qualified scoped functionality            |    | ?  | ?  | ?  |    |    |    |    |    |    |    |
| Inverse functionality                     |    |    |    |    |    |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |    |    |    |    |    |
| Structural tautology                      |    | x  | x  | x  |    |    | x  | x  | x  | x  | x  |
|                                           |    |    |    |    |    |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |    |    |    |    |    |
| Asymmetry                                 | x  | x  | x  | x  | x  | x  | x  | x  | x  | x  | x  |
| Transitivity                              |    |    |    |    |    |    |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |    | x  | x  |    |    |    |
| irreflexivity                             | x  | x  | x  | x  | x  | x  |    |    | x  | x  | x  |

### Variable and Data Type

|                                           | 33 | 34 | 35 | 36 | 37 | 38 | 39 |
| ---------                                 |----|----|----|----|----|----|----|
| Subclass                                  | x  |    |    |    |    |    |    |
| Class disjointness                        |    |    |    |    |    |    |    |
| Domain                                    |    |    |    | x  |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |    |
| Range                                     |    |    | x  |    | x  | x  |    |
| Scoped range                              |    |    |    |    |    |    |    |
| Existential                               |    |    |    |    |    |    |    |
| Inverse existential                       |    |    |    | x  |    |    |    |
| Functionality                             |    |    | x  |    | x  | x  | x  |
| Qualified functionality                   |    |    | x  |    | x  | x  |    |
| Scoped functionality                      |    |    |    |    |    |    |    |
| Qualified scoped functionality            |    |    |    |    | ?  | ?  |    |
| Inverse functionality                     |    |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |    |
| Structural tautology                      |    | x  | x  | x  | x  | x  |    |
|                                           |    |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |    |
| Asymmetry                                 | x  | x  | x  | x  | x  | x  | x  |
| Transitivity                              |    |    |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |    |    |
| irreflexivity                             | x  | x  | x  | x  | x  | x  | x  |

### Class
|                                           | 40 | 41 | 42 | 43 | 44 |
| ---------                                 |----|----|----|----|----|
| Subclass                                  | x  |    |    |    |    |
| Class disjointness                        |    |    |    |    |    |
| Domain                                    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |
| Range                                     |    | x  |    |    |    |
| Scoped range                              |    |    |    |    |    |
| Existential                               |    | x  | x  | x  |    |
| Inverse existential                       |    |    |    |    |    |
| Functionality                             |    |    | x  |    |    |
| Qualified functionality                   |    |    | x  |    |    |
| Scoped functionality                      |    |    |    |    |    |
| Qualified scoped functionality            |    |    | ?  |    |    |
| Inverse functionality                     |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |
| Structural tautology                      |    | x  | x  | x  | x  |
|                                           |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |
| Asymmetry                                 | x  | x  | x  | x  | x  |
| Transitivity                              |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |
| irreflexivity                             | x  | x  | x  | x  | x  |

### Label
|                                           | 45 | 46 | 47 |
| ---------                                 |----|----|----|
| Subclass                                  | x  |    |    |
| Class disjointness                        |    |    |    |
| Domain                                    |    |    |    |
| Scoped domain                             |    |    |    |
| Range                                     |    |    | x  |
| Scoped range                              |    |    |    |
| Existential                               |    |    | x  |
| Inverse existential                       |    |    |    |
| Functionality                             |    |    | x  |
| Qualified functionality                   |    |    | x  |
| Scoped functionality                      |    |    |    |
| Qualified scoped functionality            |    |    | ?  |
| Inverse functionality                     |    |    |    |
| Inverse qualified functionality           |    |    |    |
| Inverse scoped functionality              |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |
| Structural tautology                      |    |    | x  |
|                                           |    |    |    |
| Symmetry                                  |    |    |    |
| Asymmetry                                 | x  | x  | x  |
| Transitivity                              |    |    |    |
| Reflexivity                               |    |    |    |
| irreflexivity                             | x  | x  | x  |

### Namespace
|                                           | 48 | 49 | 50 | 51 |
| ---------                                 |----|----|----|----|
| Subclass                                  | x  |    |    |    |
| Class disjointness                        |    |    |    |    |
| Domain                                    |    |    |    |    |
| Scoped domain                             |    |    |    |    |
| Range                                     |    |    |    |    |
| Scoped range                              |    |    |    |    |
| Existential                               |    |    |    |    |
| Inverse existential                       |    |    |    |    |
| Functionality                             |    |    |    | x  |
| Qualified functionality                   |    |    |    |    |
| Scoped functionality                      |    |    |    |    |
| Qualified scoped functionality            |    |    |    |    |
| Inverse functionality                     |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |
| Structural tautology                      |    | x  | x  |    |
|                                           |    |    |    |    |
| Symmetry                                  |    |    |    |    |
| Asymmetry                                 | x  | x  | x  | x  |
| Transitivity                              |    |    |    |    |
| Reflexivity                               |    |    |    |    |
| irreflexivity                             | x  | x  | x  | x  |

### Instruction

|                                           | 52 | 53 | 54 | 55 | 56 | 57 | 58 |
| ---------                                 |----|----|----|----|----|----|----|
| Subclass                                  |    |    |    |    |    |    |    |
| Class disjointness                        |    |    |    |    |    |    |    |
| Domain                                    |    |    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |    |
| Range                                     | x  | x  | x  | x  | x  | x  | x  |
| Scoped range                              |    |    |    |    |    |    |    |
| Existential                               | x  | x  | x  |    |    |    |    |
| Inverse existential                       | x  | x  | x  |    |    |    |    |
| Functionality                             | x  |    | x  |    |    |    |    |
| Qualified functionality                   | x  |    | x  |    |    |    |    |
| Scoped functionality                      |    |    |    |    |    |    |    |
| Qualified scoped functionality            | ?  |    | ?  |    |    |    |    |
| Inverse functionality                     |    |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |    |
| Structural tautology                      | x  | x  | x  | x  | x  | x  | x  |
|                                           |    |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |    |
| Asymmetry                                 | x  | x  | x  | x  | x  | x  | x  |
| Transitivity                              |    |    |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |    |    |
| irreflexivity                             | x  | x  | x  | x  | x  | x  | x  |