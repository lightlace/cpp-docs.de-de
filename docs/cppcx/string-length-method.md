---
title: "String::Length-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Length"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Length"
ms.assetid: 92376897-1bf2-4b7a-9298-d2d3f05d8d6b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::Length-Methode
Ruft die Anzahl von Zeichen im aktuellen Zeichenfolgenobjekt ab.  
  
## Syntax  
  
```cpp  
  
unsigned int Length()  
```  
  
## Rückgabewert  
 Die Anzahl von Zeichen im aktuellen Zeichenfolgenobjekt.  
  
## Hinweise  
 Die Länge einer Zeichenfolge ohne Zeichen ist null. Die Länge der folgenden Zeichenfolge ist 5:  
  
```  
  
String^ str = "Hello";  
int len = str->Length(); //len = 5  
```  
  
 Das Zeichenarray, das von [String::Data\-Methode](../cppcx/string-data-method.md) zurückgegeben wird, hat ein zusätzliches sogenanntes endgültiges NULL\-Zeichen oder "\\ 0 ". Dieses Zeichen ist ebenfalls zwei Bytes lang.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** vccorlib.h  
  
## Siehe auch  
 [Platform::String\-Klasse](../cppcx/platform-string-class.md)