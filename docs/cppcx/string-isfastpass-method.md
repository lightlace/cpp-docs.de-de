---
title: "String::IsFastPass-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::IsFastPass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::IsFastPass"
ms.assetid: 0a8c2db7-e44f-45fe-9570-3dc82fbbacdd
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::IsFastPass-Methode
Gibt an, ob das aktuelle String\-Objekt an einem *Fast\-Pass*\-Vorgang teilnimmt. Bei einem Fast\-Pass\-Vorgang wird die Verweiszählung angehalten.  
  
## Syntax  
  
```cpp  
  
bool IsFastPass();  
```  
  
## Rückgabewert  
 `true`, wenn das aktuelle String\-Objekt FAST\-PASS ist; andernfalls `false`.  
  
## Hinweise  
 Beim Aufruf einer Funktion, bei der ein Objekt mit Verweiszählung ein Parameter ist und die aufgerufene Funktion nur dieses Objekt liest, kann der Compiler die Verweiszählung sicher anhalten und die Aufrufleistung verbessern. Es gibt nichts nützliches, das Ihr Code mit dieser Eigenschaft ausführen kann. Das System behandelt alle Details.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** vccorlib.h  
  
## Siehe auch  
 [Platform::String\-Klasse](../cppcx/platform-string-class.md)