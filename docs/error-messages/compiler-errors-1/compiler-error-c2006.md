---
title: "Compilerfehler C2006 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2006"
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Direktive': Dateiname erwartet, aber 'Token' gefunden  
  
 Für Direktiven, wie [\#include](../../preprocessor/hash-include-directive-c-cpp.md) oder [\#import](../../preprocessor/hash-import-directive-cpp.md), ist ein Dateiname erforderlich.  Um den Fehler zu beheben, sollten Sie sicherstellen, dass *token* ein gültiger Dateiname ist.  Darüber hinaus sollten Sie den Dateinamen in doppelte Anführungszeichen oder spitze Klammern einschließen.  
  
 Im folgenden Beispiel wird C2006 generiert:  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 Mögliche Lösung:  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```