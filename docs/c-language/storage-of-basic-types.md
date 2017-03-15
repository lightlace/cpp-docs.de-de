---
title: "Speicherung von einfachen Typen | Microsoft Docs"
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
helpviewer_keywords: 
  - "Arithmetische Operationen [C++], Typen"
  - "Datentypen [C], Bezeichner"
  - "Datentypen [C], Speicher"
  - "double-Datentyp, Speicher"
  - "Gleitkommazahlen, Speicher"
  - "int-Datentyp"
  - "Ganzzahlige Typen"
  - "Ganzzahlige Typen, Speicher"
  - "long double-Schlüsselwort [C], Speicher"
  - "long-Schlüsselwort [C]"
  - "short-Datentyp"
  - "Typen mit Vorzeichen [C++], Speicher"
  - "Spezifizierer [C++], Typ"
  - "Speicherung [C++], Typen"
  - "Speichern von Typen [C++]"
  - "Typspezifizierer [C++], Größen"
  - "Typen [C], Arithmetisch"
  - "Typen ohne Vorzeichen [C++], Speicher"
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Speicherung von einfachen Typen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der folgenden Tabelle wird der Speicher zusammengefasst, welcher jedem Basistyp zugeordnet ist.  
  
### Größen von grundlegenden Typen  
  
|Typ|Speicher|  
|---------|--------------|  
|`char`, `unsigned char`, **signed char**|1 Byte|  
|**short**, **unsigned short**|2 Bytes|  
|`int`, `unsigned int`|4 Bytes|  
|**long**, `unsigned long`|4 Bytes|  
|**float**|4 Bytes|  
|**double**|8 Bytes|  
|`long double`|8 Bytes|  
  
 Die C\-Datentypen fallen in allgemeine Kategorien.  Die "ganzzahligen Typen" enthalten `char`, `int`, **short**, **long**, **signed**, `unsigned` und `enum`.  Die "Gleitkommatypen" enthalten **float**, **double** und `long double`.  Die "arithmetischen Typen" umfassen alle Gleitkomma\- und Ganzzahltypen.  
  
## Siehe auch  
 [Deklarationen und Typen](../c-language/declarations-and-types.md)