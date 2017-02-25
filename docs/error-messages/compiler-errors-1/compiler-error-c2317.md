---
title: "Compilerfehler C2317 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2317"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2317"
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2317
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der try\-Block ab Zeile 'Nummer' besitzt keine catch\-Handler.  
  
 Ein `try`\-Block muss mindestens einen catch\-Handler aufweisen.  
  
 Im folgenden Beispiel wird C2317 generiert:  
  
```  
// C2317.cpp // compile with: /EHsc #include <eh.h> int main() { try { throw "throw an exception"; } // C2317, no catch handler }  
```  
  
 Mögliche Lösung:  
  
```  
// C2317b.cpp // compile with: /EHsc #include <eh.h> int main() { try { throw "throw an exception"; } catch(char*) {} }  
```