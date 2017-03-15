---
title: "check_stack | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.check_stack"
  - "check_stack_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "check_stack-Pragma"
  - "Pragmas, check_stack"
  - "Pragmas, check_stack-Verwendungstabelle"
ms.assetid: f18e20cc-9abb-48b7-ad62-8d384875b996
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# check_stack
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Weist den Compiler an, Stapelüberprüfungen zu deaktivieren, wenn **off** \(oder **–**\) angegeben ist, bzw. Stapelüberprüfungen zu aktivieren, wenn **on** \(oder **\+**\) angegeben ist.  
  
## Syntax  
  
```  
  
      #pragma check_stack([ {on | off}] )  
#pragma check_stack{+ | –}  
```  
  
## Hinweise  
 Wird kein Argument angegeben ist, werden Stapelüberprüfungen gemäß der Standardeinstellung behandelt.  Dieses Pragma tritt mit der ersten Funktionsdefinition in Kraft, nachdem das Pragma angezeigt wird.  Stapelüberprüfungen sind weder ein Bestandteil von Makros noch von Funktionen, die inline generiert werden.  
  
 Wenn Sie kein Argument für das **check\_stack**\-Pragma angeben, stellt die Stapelüberprüfung das Verhalten wieder her, das in der Befehlszeile angegeben ist.  Weitere Informationen finden Sie unter [Compiler\-Verweis](../build/reference/compiler-options.md).  Die Interaktion von **\#pragma check\_stack** und der [\/Gs](../build/reference/gs-control-stack-checking-calls.md)\-Option ist in der folgenden Tabelle zusammengefasst.  
  
### Verwenden des check\_stack\-Pragmas  
  
|Syntax|Kompiliert mit der<br /><br /> \/Gs\-Option?|Aktion|  
|------------|------------------------------------------|------------|  
|**\#pragma check\_stack\( \)** oder<br /><br /> **\#pragma check\_stack**|Ja|Deaktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|  
|**\#pragma check\_stack\( \)** oder<br /><br /> **\#pragma check\_stack**|Nein|Aktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|  
|**\#pragma check\_stack\(on\)**<br /><br /> oder **\#pragma check\_stack \+**|"Ja" oder "Nein"|Aktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|  
|**\#pragma check\_stack\(off\)**<br /><br /> oder **\#pragma check\_stack –**|"Ja" oder "Nein"|Deaktiviert die Stapelüberprüfung für Funktionen, die Folgendem folgen|  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)