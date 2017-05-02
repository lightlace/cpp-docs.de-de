---
title: "String::Concat-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Concat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Concat"
ms.assetid: 68052d22-3df0-4777-828d-fc3a8e8a3ab7
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Concat-Methode
Verkettet die Werte von zwei Zeichenfolgenobjekten.  
  
## Syntax  
  
```cpp  
  
String^ Concat( String ^ str1,   
String ^ str2  
)  
  
```  
  
#### Parameter  
 `str1`  
 Das erste Zeichenfolgenobjekt oder `null`.  
  
 `str2`  
 Das zweite Zeichenfolgenobjekt oder `null`.  
  
## Rückgabewert  
 Ein neues Zeichenfolgen^\-Objekt, dessen Wert die Verkettung der Werte von `str1` und `str2` ist.  
  
 Wenn `str1``null` und `str2` ungleich null ist, wird `str1`  zurückgegeben. Wenn `str2``null` und `str1` ungleich null ist, wird `str2` zurückgegeben. Wenn `str1` und `str2` beide `null` sind, wird die leere Zeichenfolge \(L ""\) zurückgegeben.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** vccorlib.h  
  
## Siehe auch  
 [Platform::String\-Klasse](../cppcx/platform-string-class.md)