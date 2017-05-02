---
title: "StringReference::StringReference-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::StringReference::StringReference"
dev_langs: 
  - "C++"
ms.assetid: 87dd9201-e638-4913-b37c-7091ae3f91ea
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# StringReference::StringReference-Konstruktor
Initialisiert eine neue Instanz der `StringReference`\-Klasse.  
  
## Syntax  
  
```cpp  
  
    StringReference();  
  
   StringReference(const StringReference& __fstrArg)  
  
StringReference(const ::default::char16* __strArg)  
  
StringReference(const ::default::char16* __strArg, size_t __lenArg)  
```  
  
#### Parameter  
 `__fstrArg`  
 Der `StringReference`, dessen Daten zum Initialisieren der neuen Instanz verwendet werden.  
  
 `__strArg`  
 Zeiger auf ein char16\-Wertearray, das zum Initialisieren der neuen Instanz verwendet wird.  
  
 `__lenArg`  
 Die Anzahl von Elementen in `__strArg`.  
  
## Hinweise  
 Die erste Version dieses Konstruktors ist der Standardkonstruktor. Die zweite Version initialisiert eine neue `StringReference`\-Instanzklasse aus dem Objekt, das durch den `__fstrArg`\-Parameter spezifiziert wird. Die dritten und vierten Überladungen initialisieren eine neue `StringReference`\-Instanz aus einem char16\-Wertearray. char16 stellt ein 16\-Bit\-UNICODE\-Textzeichen dar.  
  
## Anforderungen  
 **Unterstützter Client \(Min.\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Min.\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Platform::StringReference\-Klasse](../cppcx/platform-stringreference-class.md)