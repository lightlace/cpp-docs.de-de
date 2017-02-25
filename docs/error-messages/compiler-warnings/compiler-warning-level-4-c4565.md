---
title: "Compilerwarnung (Stufe 4) C4565 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4565"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4565"
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4565
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Neudefinition; das Symbol wurde zuvor mit \_\_declspec\(Modifizierer\) deklariert  
  
 Ein Symbol wurde neu definiert oder erneut deklariert, und die zweite Definition oder Deklaration hat im Gegensatz zur ersten Definition oder Deklaration keinen `__declspec`\-Modifizierer \(***modifier***\).  Diese Warnung dient zu Informationszwecken.  Löschen Sie eine der Definitionen, um diese Warnung zu vermeiden.  
  
 Im folgenden Beispiel wird C4565 generiert:  
  
```  
// C4565.cpp  
// compile with: /W4 /LD  
__declspec(noalias) void f();  
void f();   // C4565  
```