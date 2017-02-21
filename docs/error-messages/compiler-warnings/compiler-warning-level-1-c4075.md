---
title: "Compilerwarnung (Stufe 1) C4075 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4075"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4075"
ms.assetid: 19a700b6-f210-4b9d-a2f2-76cfe39ab178
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4075
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Initialisierungen stehen in nicht erkanntem Initialisierungsbereich  
  
 In einem [\#pragma init\_seg](../../preprocessor/init-seg.md) wird ein unbekannter Abschnittsname verwendet. Der Compiler ignoriert den **pragma**\-Befehl.  
  
 Im folgenden Beispiel wird C4075 generiert:  
  
```  
// C4075.cpp // compile with: /W1 #pragma init_seg("mysegg")   // C4075 // try.. // #pragma init_seg(user) int main() { }  
```