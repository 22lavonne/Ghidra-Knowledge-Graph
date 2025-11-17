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
| 13        | Reference     | hasOperandIndex| index|
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
| 36        | Variable      | localaVariableDefinedIn | Class |
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
| Class disjointness                        |    |    |    |    |    |    |    |    |    |  
| Domain                                    |    |    |    |    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |    |    |    |
| Range                                     |    |    |    |    |    |    |    |    |    |
| Scoped range                              |    |    |    |    |    |    |    |    |    |
| Existential                               |    |    |    |    |    |    |    |    |    |
| Inverse existential                       |    |    |    |    |    |    |    |    |    |
| Functionality                             |    | ✓  |    |    |    |    |    |    |    |
| Qualified functionality                   |    |    |    |    |    |    |    |    |    |
| Scoped functionality                      |    |    |    |    |    |    |    |    |    |
| Qualified scoped functionality            |    |    |    |    |    |    |    |    |    |
| Inverse functionality                     |    |    |    |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |    |    |    |
| Structural tautology                      |    |    |    |    |    |    |    |    |    |
|                                           |    |    |    |    |    |    |    |    |    |
| For the Property                          |    |    |    |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |    |    |    |
| Asymmetry                                 |    |    |    |    |    |    |    |    |    |
| Transitivity                              |    |    |    |    |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |    |    |    |    |
| irreflexivity                             |    |    |    |    |    |    |    |    |    |

### Reference and Address

|                                           | 10 | 11 | 12 | 13 | 14 | 15 | 
| ---------                                 |----|----|----|----|----|----|
| Class disjointness                        |    |    |    |    |    |    |
| Domain                                    |    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |
| Range                                     |    |    |    |    |    |    |
| Scoped range                              |    |    |    |    |    |    |
| Existential                               |    |    |    |    |    |    |
| Inverse existential                       |    |    |    |    |    |    |
| Functionality                             | ✓ |  ✓ |  ✓ | ✓  | ✓ |  ✓ |
| Qualified functionality                   |    |    |    |    |    |    |
| Scoped functionality                      |    |    |    |    |    |    |
| Qualified scoped functionality            |    |    |    |    |    |    |
| Inverse functionality                     |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |
| Structural tautology                      |    |    |    |    |    |    |
|                                           |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |
| Asymmetry                                 |    |    |    |    |    |    |
| Transitivity                              |    |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |    |
| irreflexivity                             |    |    |    |    |    |    |

### Import and Export

|                                           | 16 | 17 | 18 | 19 | 20 | 21 | 
| ---------                                 |----|----|----|----|----|----|
| Class disjointness                        |    |    |    |    |    |    |
| Domain                                    |    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |
| Range                                     |    |    |    |    |    |    |
| Scoped range                              |    |    |    |    |    |    |
| Existential                               |    |    |    |    |    |    |
| Inverse existential                       |    |    |    |    |    |    |
| Functionality                             |    |    |    |    |  ✓  |  ✓  |
| Qualified functionality                   |    |    |    |    |    |    |
| Scoped functionality                      |    |    |    |    |    |    |
| Qualified scoped functionality            |    |    |    |    |    |    |
| Inverse functionality                     |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |
| Structural tautology                      |    |    |    |    |    |    |
|                                           |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |
| Asymmetry                                 |    |    |    |    |    |    |
| Transitivity                              |    |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |    |
| irreflexivity                             |    |    |    |    |    |    |


### Functions

|                                           | 22 | 23 | 24 | 25 | 26 | 27 | 28 | 29 | 30 | 31 | 32 |
| ---------                                 |----|----|----|----|----|----|----|----|----|----|----|
| Class disjointness                        |    |    |    |    |    |    |    |    |    |    |    |  
| Domain                                    |    |    |    |    |    |    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |    |    |    |    |    |
| Range                                     |    |    |    |    |    |    |    |    |    |    |    |
| Scoped range                              |    |    |    |    |    |    |    |    |    |    |    |
| Existential                               |    |    |    |    |    |    |    |    |    |    |    |
| Inverse existential                       |    |    |    |    |    |    |    |    |    |    |    |
| Functionality                             |    |  ✓ | ✓ | ✓  |    |    |    |    |  ✓ |    |    |
| Qualified functionality                   |    |    |    |    |    |    |    |    |    |    |    |
| Scoped functionality                      |    |    |    |    |    |    |    |    |    |    |    |
| Qualified scoped functionality            |    |    |    |    |    |    |    |    |    |    |    |
| Inverse functionality                     |    |    |    |    |    |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |    |    |    |    |    |
| Structural tautology                      |    |    |    |    |    |    |    |    |    |    |    |
|                                           |    |    |    |    |    |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |    |    |    |    |    |
| Asymmetry                                 |    |    |    |    |    |    |    |    |    |    |    |
| Transitivity                              |    |    |    |    |    |    |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |    |    |    |    |    |    |
| irreflexivity                             |    |    |    |    |    |    |    |    |    |    |    |

### Variable and Data Type

|                                           | 33 | 34 | 35 | 36 | 37 | 38 | 39 |
| ---------                                 |----|----|----|----|----|----|----|
| Class disjointness                        |    |    |    |    |    |    |    |
| Domain                                    |    |    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |    |
| Range                                     |    |    |    |    |    |    |    |
| Scoped range                              |    |    |    |    |    |    |    |
| Existential                               |    |    |    |    |    |    |    |
| Inverse existential                       |    |    |    |    |    |    |    |
| Functionality                             |    |    |  ✓ |    | ✓ | ✓  | ✓ |
| Qualified functionality                   |    |    |    |    |    |    |    |
| Scoped functionality                      |    |    |    |    |    |    |    |
| Qualified scoped functionality            |    |    |    |    |    |    |    |
| Inverse functionality                     |    |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |    |
| Structural tautology                      |    |    |    |    |    |    |    |
|                                           |    |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |    |
| Asymmetry                                 |    |    |    |    |    |    |    |
| Transitivity                              |    |    |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |    |    |
| irreflexivity                             |    |    |    |    |    |    |    |

### Class
|                                           | 40 | 41 | 42 | 43 | 44 |
| ---------                                 |----|----|----|----|----|
| Class disjointness                        |    |    |    |    |    |
| Domain                                    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |
| Range                                     |    |    |    |    |    |
| Scoped range                              |    |    |    |    |    |
| Existential                               |    |    |    |    |    |
| Inverse existential                       |    |    |    |    |    |
| Functionality                             |    |    |  ✓  |    |    |
| Qualified functionality                   |    |    |    |    |    |
| Scoped functionality                      |    |    |    |    |    |
| Qualified scoped functionality            |    |    |    |    |    |
| Inverse functionality                     |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |
| Structural tautology                      |    |    |    |    |    |
|                                           |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |
| Asymmetry                                 |    |    |    |    |    |
| Transitivity                              |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |
| irreflexivity                             |    |    |    |    |    |

### Label
|                                           | 45 | 46 | 47 |
| ---------                                 |----|----|----|
| Class disjointness                        |    |    |    |
| Domain                                    |    |    |    |
| Scoped domain                             |    |    |    |
| Range                                     |    |    |    |
| Scoped range                              |    |    |    |
| Existential                               |    |    |    |
| Inverse existential                       |    |    |    |
| Functionality                             |    | ✓  | ✓  |
| Qualified functionality                   |    |    |    |
| Scoped functionality                      |    |    |    |
| Qualified scoped functionality            |    |    |    |
| Inverse functionality                     |    |    |    |
| Inverse qualified functionality           |    |    |    |
| Inverse scoped functionality              |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |
| Structural tautology                      |    |    |    |
|                                           |    |    |    |
| Symmetry                                  |    |    |    |
| Asymmetry                                 |    |    |    |
| Transitivity                              |    |    |    |
| Reflexivity                               |    |    |    |
| irreflexivity                             |    |    |    |

### Namespace
|                                           | 48 | 49 | 50 | 51 |
| ---------                                 |----|----|----|----|
| Class disjointness                        |    |    |    |    |
| Domain                                    |    |    |    |    |
| Scoped domain                             |    |    |    |    |
| Range                                     |    |    |    |    |
| Scoped range                              |    |    |    |    |
| Existential                               |    |    |    |    |
| Inverse existential                       |    |    |    |    |
| Functionality                             |    |    |    |  ✓ |
| Qualified functionality                   |    |    |    |    |
| Scoped functionality                      |    |    |    |    |
| Qualified scoped functionality            |    |    |    |    |
| Inverse functionality                     |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |
| Structural tautology                      |    |    |    |    |
|                                           |    |    |    |    |
| Symmetry                                  |    |    |    |    |
| Asymmetry                                 |    |    |    |    |
| Transitivity                              |    |    |    |    |
| Reflexivity                               |    |    |    |    |
| irreflexivity                             |    |    |    |    |

### Instruction

|                                           | 52 | 53 | 54 | 55 | 56 | 57 | 58 |
| ---------                                 |----|----|----|----|----|----|----|
| Class disjointness                        |    |    |    |    |    |    |    |
| Domain                                    |    |    |    |    |    |    |    |
| Scoped domain                             |    |    |    |    |    |    |    |
| Range                                     |    |    |    |    |    |    |    |
| Scoped range                              |    |    |    |    |    |    |    |
| Existential                               |    |    |    |    |    |    |    |
| Inverse existential                       |    |    |    |    |    |    |    |
| Functionality                             |  ✓ |    | ✓  |    |    |    |    |
| Qualified functionality                   |    |    |    |    |    |    |    |
| Scoped functionality                      |    |    |    |    |    |    |    |
| Qualified scoped functionality            |    |    |    |    |    |    |    |
| Inverse functionality                     |    |    |    |    |    |    |    |
| Inverse qualified functionality           |    |    |    |    |    |    |    |
| Inverse scoped functionality              |    |    |    |    |    |    |    |
| Inverse qualified scoped functionality    |    |    |    |    |    |    |    |
| Structural tautology                      |    |    |    |    |    |    |    |
|                                           |    |    |    |    |    |    |    |
| Symmetry                                  |    |    |    |    |    |    |    |
| Asymmetry                                 |    |    |    |    |    |    |    |
| Transitivity                              |    |    |    |    |    |    |    |
| Reflexivity                               |    |    |    |    |    |    |    |
| irreflexivity                             |    |    |    |    |    |    |    |