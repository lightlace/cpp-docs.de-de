---
title: "ArrayReference::operator=-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::operator="
dev_langs: 
  - "C++"
ms.assetid: 131a4612-d66b-48e4-90af-c665ccc0cce4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# ArrayReference::operator=-Operator
Weist dem aktuellen [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md)\-Objekt unter Verwendung der Verschiebesemantik das angegebene Objekt zu.  
  
## Syntax  
  
```cpp  
  
ArrayReference& operator=(ArrayReference&& __otherArg);  
  
```  
  
#### Parameter  
 `__ otherArg`  
 Das zum aktuellen `ArrayReference`\-Objekt verschobene Objekt.  
  
## Rückgabewert  
 Ein Verweis auf ein Objekt des Typs `ArrayReference`.  
  
## Hinweise  
 `Platform::ArrayReference` ist eine Standard\-C\+\+\-Klassenvorlage, keine Verweisklasse.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::ArrayReference\-Klasse](../cppcx/platform-arrayreference-class.md)