---
title: "Compilerwarnung (Stufe 1) C4806 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4806"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4806"
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4806
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"operation": unsichere Operation: kein Wert vom Typ "type" erweitert auf Typ "type" kann mit der angegebenen Konstante übereinstimmen  
  
 Diese Meldung warnt Sie vor Code wie `b == 3`, wobei `b` Typ `bool` aufweist. Aufgrund der Erweiterungsregeln wird `bool` auf `int` erweitert. Dies ist zulässig, es kann aber nie **true** sein. Im folgenden Beispiel wird C4806 generiert:  
  
```  
// C4806.cpp // compile with: /W1 int main() { bool b = true; // try.. // int b = true; if (b == 3)   // C4806 { b = false; } }  
```