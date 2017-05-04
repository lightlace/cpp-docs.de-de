---
title: "ArrayReference::operator()-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::operatorArray^"
dev_langs: 
  - "C++"
ms.assetid: 48726344-82bb-4c1d-b246-ed74b895f99b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# ArrayReference::operator()-Operator
Konvertiert das aktuelle [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md)\-Objekt in eine [Platform::Array](../cppcx/platform-array-class.md)\-Klasse zurück.  
  
## Syntax  
  
```cpp  
  
Array<__TArg>^ operator ();  
  
```  
  
## Rückgabewert  
 Ein Handle für das Objekt des Typs `Array<__TArg>^`  
  
## Hinweise  
 [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) und [Platform::Array](../cppcx/platform-array-class.md) sind Standard\-C\+\+\-Klassenvorlagen, keine Verweisklassen.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::ArrayReference\-Klasse](../cppcx/platform-arrayreference-class.md)