---
title: "raw_native_types | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "raw_native_types"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "raw_native_types-Attribut"
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# raw_native_types
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**C\+\+\-spezifisch**  
  
 Deaktiviert die Verwendung COM\-Unterstützungsklassen in den Wrapperfunktionen auf hoher Ebene und erzwingt stattdessen die Verwendung von Datentypen auf niedriger Ebene.  
  
## Syntax  
  
```  
raw_native_types  
```  
  
## Hinweise  
 Standardmäßig verwenden die Fehlerbehandlungsmethoden auf hoher Ebene die COM\-Unterstützungsklassen [\_bstr\_t](../cpp/bstr-t-class.md) und [\_variant\_t](../cpp/variant-t-class.md) anstelle von `BSTR`\- und **VARIANT**\-Datentypen und unformatierten COM\-Schnittstellenzeigern.  Diese Klassen kapseln die Details der Zuordnung und Freigabe des Arbeitsspeichers für diese Datentypen und vereinfachen die Typumwandlungs\- und Konvertierungsoperationen erheblich.  
  
 **Ende C\+\+\-spezifisch**  
  
## Siehe auch  
 [\#import\-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import\-Direktive](../preprocessor/hash-import-directive-cpp.md)