---
title: "Compilerfehler C2006"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2006"
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
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