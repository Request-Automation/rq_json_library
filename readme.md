# ReQuest Json Library Documentation

Documentaizione ed esempi libreria JSON C++ e FB per PLC next engeneer

Documentation and example JSON library FB plus C++ for PLC Next Engeneer

[comment]: <> (non-breaking space)
&nbsp;
&nbsp;

## Index - Indice
 - Installazione / Installation hint
 - general information (cosa è un json)
 - change notes (copiare la tabella di esempio)
 - function block (list)	(block, description, version, supported article, licence)
 - function block X (input, output, in/out) per Ogni function block
 - supported target

[comment]: <> (non-breaking space)
&nbsp;
&nbsp;

## Installation hint
If you did not specify a different directory during library installation all data in the MSI file will be unpacked to:

> c:\Users\Public\Documents\Phoenix Contact Libraries\PLCnext Engineer
> (former: PC Worx Engineer)

Please copy the library data to your PLCnext Engineer (former: PC Worx Engineer) working library directory.
If you did not specify a different directory during PLCnext Engineer installation the default PLCnext Engineer working library directory is:

> c:\Users\Public\Documents\PLCnext Engineer\Libraries (former: PC Worx
> Engineer\Libraries)

[comment]: <> (non-breaking space)
&nbsp;
&nbsp;

## General Information
**JSON**  (JavaScript Object Notation) is a lightweight data-interchange format. It is easy for humans to read and write. It is easy for machines to parse and generate.
 JSON is a text format that is completely language independent but uses conventions that are familiar to programmers.

more info at https://www.json.org/

[comment]: <> (non-breaking space)
&nbsp;
&nbsp;

## Change notes

[comment]: <> (non-breaking space)
&nbsp;
&nbsp;

## Function Blocks List
|Function block 	|Description 	| Version	| Licence |
|----------|-------|-------------------|------------------|
|RQ_Json_Read_manager |This function block manage the execution of the library | 1| none |
|RQ_Json_Read_Bool | This function block read a boolean value in the JSON file  | 1 | none |
|RQ_Json_Read_Int  | This function block read a integer value in the JSON file | 1| none |
|RQ_Json_Read_Real | This function block read a real value in the JSON file | 1| none |
|RQ_Json_Read_String | This function block read a string value in the JSON file| 1| none |

[comment]: <> (non-breaking space)
&nbsp;
&nbsp;

## RQ_Json_Read_Manager
### Input Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|xRequest  | BOOL | JSON read request |
|sFilePath | STRING | Absolute file path (ex. */opt/plcnext/projects/RQ_Json/...*) |

### Output Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|xDone  | BOOL | Request is sent and response is successfully received. |
|iAmountKeyRequested | UINT | number of key requested  |
|xError | BOOL | if TRUE: An error has occurred. For details refer to wDiagCode |
|xDiagCode | WORD | diagnosis error codes (see wDiagCode table  |

### InOut Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|udtJsonReadManager  | udtJsonReadManager_type | Management communication structure of the block family |

### Diagnosis
| wDiagCode      |ERROR TYPE				 |
|----------------|-------------------------------|
|16#0000         |`File not present /Read error` |
|16#0001         |`JSON not valid`              |

[comment]: <> (non-breaking space)
&nbsp;
&nbsp;

## RQ_Json_Read_Bool
### Input Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|sKeyPath  | STRING | JSON key path |

### Output Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|xDone  | BOOL | Request is sent and response is successfully received. |
|xValue | BOOL | key value  |
|xError | BOOL | if TRUE: An error has occurred. For details refer to wDiagCode |
|xDiagCode | WORD | diagnosis error codes (see wDiagCode table  |

### InOut Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|udtJsonReadManager  | udtJsonReadManager_type | Management communication structure of the block family |
|arrJsonReadData | arrJsonReadData_type |  Data communication structure of the block family |

### Diagnosis
| wDiagCode      |ERROR TYPE				 |
|----------------|-------------------------------|
|16#0000         |`Data type different then expected` |
|16#0001         |`key not found`             |
|16#0002         |`reserved (datatype not valid)` |

[comment]: <> (non-breaking space)
&nbsp;
&nbsp;

## RQ_Json_Read_Int
### Input Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|sKeyPath  | STRING | JSON key path |

### Output Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|xDone  | BOOL | Request is sent and response is successfully received. |
|iValue | INT | key value  |
|xError | BOOL | if TRUE: An error has occurred. For details refer to wDiagCode |
|xDiagCode | WORD | diagnosis error codes (see wDiagCode table  |

### InOut Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|udtJsonReadManager  | udtJsonReadManager_type | Management communication structure of the block family |
|arrJsonReadData | arrJsonReadData_type |  Data communication structure of the block family |

### Diagnosis
| wDiagCode      |ERROR TYPE				 |
|----------------|-------------------------------|
|16#0000         |`Data type different then expected` |
|16#0001         |`key not found`             |
|16#0002         |`reserved (datatype not valid)` |

[comment]: <> (non-breaking space)
&nbsp;
&nbsp;

## RQ_Json_Read_Real
### Input Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|sKeyPath  | STRING | JSON key path |

### Output Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|xDone  | BOOL | Request is sent and response is successfully received. |
|rValue | REAL | key value  |
|xError | BOOL | if TRUE: An error has occurred. For details refer to wDiagCode |
|xDiagCode | WORD | diagnosis error codes (see wDiagCode table  |

### InOut Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|udtJsonReadManager  | udtJsonReadManager_type | Management communication structure of the block family |
|arrJsonReadData | arrJsonReadData_type |  Data communication structure of the block family |

### Diagnosis
| wDiagCode      |ERROR TYPE				 |
|----------------|-------------------------------|
|16#0000         |`Data type different then expected` |
|16#0001         |`key not found`             |
|16#0002         |`reserved (datatype not valid)` |

[comment]: <> (non-breaking space)
&nbsp;
&nbsp;

## RQ_Json_Read_String
### Input Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|sKeyPath  | STRING | JSON key path |

### Output Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|xDone  | BOOL | Request is sent and response is successfully received. |
|sValue | STRING | key value  |
|xError | BOOL | if TRUE: An error has occurred. For details refer to wDiagCode |
|xDiagCode | WORD | diagnosis error codes (see wDiagCode table  |

### InOut Parameters
|NAME 	|TYPE 	| DESCRIPTION	|
|----------|-------|-------------------|
|udtJsonReadManager  | udtJsonReadManager_type | Management communication structure of the block family |
|arrJsonReadData | arrJsonReadData_type |  Data communication structure of the block family |

### Diagnosis
| wDiagCode      |ERROR TYPE				 |
|----------------|-------------------------------|
|16#0000         |`Data type different then expected` |
|16#0001         |`key not found`             |
|16#0002         |`reserved (datatype not valid)` |

