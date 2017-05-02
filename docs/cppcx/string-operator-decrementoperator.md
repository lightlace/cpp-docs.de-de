---
title: "String::operator+-Operator | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator+"
dev_langs: 
  - "C++"
ms.assetid: 919b5ba4-3d3b-47a4-9893-9a9ce51fb9c8
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::operator+-Operator
Gibt an, ob zwei angegebene [Zeichenfolgen](../cppcx/platform-string-class.md)\-Objekte denselben Wert haben.  
  
## Syntax  
  
```cpp  
  
bool String::operator+( String^ str1,  
                         String^ str2)  
  
```  
  
#### Parameter  
 `str1`  
 Das erste `String`\-Objekt.  
  
 `str2`  
 Das zweite `String`\-Objekt, dessen Inhalt `str1` angefügt wird.  
  
## Rückgabewert  
 `true`, wenn `str1` und `str2` gleich sind, andernfalls `false`.  
  
## Hinweise  
 Dieser Operator erstellt ein `String^`\-Objekt mit den Daten aus den zwei Operanden. Verwenden Sie es zur Vereinfachung, wenn nicht unbedingt extreme Leistung gefordert ist. Einige Aufrufe von "`+`" in einer Funktion werden sich wahrscheinlich nicht bemerkbar machen. Wenn Sie jedoch große Objekte oder Textdaten in einer kurzen Schleife bearbeiten, sollten Sie die standardmäßigen C\+\+\-Mechanismen und \-typen verwenden.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** vccorlib.h  
  
## Siehe auch  
 [Platform::String\-Klasse](../cppcx/platform-string-class.md)