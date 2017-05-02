---
title: "ArrayReference::ArrayReference-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::ArrayReference"
dev_langs: 
  - "C++"
ms.assetid: 9fc7dfcf-47af-40ba-a697-da476fb90efc
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# ArrayReference::ArrayReference-Konstruktor
Initialisiert eine neue Instanz der [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md)\-Klasse.  
  
## Syntax  
  
```cpp  
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);  
ArrayReference(ArrayReference&& otherArg)  
  
```  
  
#### Parameter  
 `dataArg`  
 Ein Zeiger auf die Arraydaten.  
  
 `sizeArg`  
 Die Anzahl von Elementen im Quellarray.  
  
 `otherArg`  
 Ein `ArrayReference`\-Objekt, dessen Daten zum Initialisieren der neuen Instanz verschoben werden.  
  
## Hinweise  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::ArrayReference\-Klasse](../cppcx/platform-arrayreference-class.md)   
 [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)