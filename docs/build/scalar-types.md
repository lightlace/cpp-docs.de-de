---
title: "Skalare Typen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Skalare Typen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obwohl Datenzugriffe auf einer beliebigen Ausrichtung basieren können, wird empfohlen, Daten unter Berücksichtigung ihrer natürlichen Begrenzungen \(bzw. nach einem ganzahligen Vielfachen\) auszurichten, um so Leistungeinbußen zu vermeiden.  Enumerationen sind konstante ganze Zahlen und werden als 32\-Bit\-Integerwerte behandelt.  In der folgenden Tabelle werden die Typdefinition und die jeweils empfohlene Speicherung aufgeführt, die sich aus den folgenden Ausrichtungswerten ergibt:  
  
-   Byte \- 8 Bits  
  
-   Word \- 16 Bits  
  
-   Doubleword \- 32 Bits  
  
-   Quadword \- 64 Bits  
  
-   Octaword \- 128 Bits  
  
|||||  
|-|-|-|-|  
|Skalartyp|C\-Datentyp|Speichergröße \(in Byte\)|Empfohlene Ausrichtung|  
|**INT8**|`char`|1|Byte|  
|**UINT8**|`unsigned char`|1|Byte|  
|**INT16**|**short**|2|Word|  
|**UINT16**|**unsigned short**|2|Word|  
|**INT32**|**int, long**|4|Doubleword|  
|**UINT32**|**unsigned int, unsigned long**|4|Doubleword|  
|**INT64**|`__int64`|8|Quadword|  
|**UINT64**|**unsigned \_\_int64**|8|Quadword|  
|**FP32 \(einfache Genauigkeit\)**|**float**|4|Doubleword|  
|**FP64 \(doppelte Genauigkeit\)**|**double**|8|Quadword|  
|**POINTER**|**\***|8|Quadword|  
|`__m64`|**struct \_\_m64**|8|Quadword|  
|`__m128`|**struct \_\_m128**|16|Octaword|  
  
## Siehe auch  
 [Typen und Speicher](../build/types-and-storage.md)