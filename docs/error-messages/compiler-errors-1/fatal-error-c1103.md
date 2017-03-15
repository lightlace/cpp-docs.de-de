---
title: "Schwerwiegender Fehler C1103 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1103"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1103"
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Schwerwiegender Fehler C1103
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schwerwiegender Fehler beim Importieren der ProgID: "Meldung"  
  
 Der Compiler hat beim Importieren einer Typbibliothek ein Problem festgestellt.  Sie können beispielsweise keine Typbibliothek mit "progid" angeben und gleichzeitig `no_registry` festlegen.  
  
 Weitere Informationen finden Sie unter [\#import\-Direktive](../../preprocessor/hash-import-directive-cpp.md).  
  
 Im folgenden Beispiel wird C1103 generiert:  
  
```  
// C1103.cpp #import "progid:a.b.id.1.5" no_registry auto_search   // C1103  
```