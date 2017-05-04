---
title: "String::String-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::String"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::String"
ms.assetid: 80b6461a-5b12-4dcb-9323-f2c5f310bbc6
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::String-Konstruktor
Initialisiert eine neue Instanz der Zeichenfolgenklasse mit einer Kopie der Eingabezeichenfolgendaten.  
  
## Syntax  
  
```cpp  
  
String();  
  
String(  
  char16* s  
)  
  
String(  
  char16* s,   
  unsigned int n  
)  
```  
  
## Parameter  
 `s`  
 Eine Reihe von Breitzeichen, die die Zeichenfolge initialisieren. char16  
  
 `n`  
 Eine Zahl, die die Länge der Zeichenfolge angibt.  
  
## Hinweise  
 Wenn die Leistung kritisch ist und Sie die Lebensdauer der Quellzeichenfolge kontrollieren, können Sie anstelle von "String" [Platform::StringReference](../cppcx/platform-stringreference-class.md) verwenden.  
  
## Beispiel  
  
```  
String^ s = L”Hello!”;  
```  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** vccorlib.h  
  
## Siehe auch  
 [Platform::String\-Klasse](../cppcx/platform-string-class.md)