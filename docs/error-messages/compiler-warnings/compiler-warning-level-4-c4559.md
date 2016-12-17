---
title: "Compilerwarnung (Stufe 4) C4559"
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
  - "C4559"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4559"
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4559
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Neudefinition; die Funktion erhält \_\_declspec\(Modifizierer\)  
  
 Eine Funktion wurde neu definiert oder erneut deklariert, und die zweite Definition oder Deklaration hat einen \_\_**declspec**\-Modifizierer \(***Modifizierer***\) hinzugefügt.  Diese Warnung dient zu Informationszwecken.  Löschen Sie eine der Definitionen, um diese Warnung zu vermeiden.  
  
 Im folgenden Beispiel wird C4559 generiert:  
  
```  
// C4559.cpp  
// compile with: /W4 /LD  
void f();  
__declspec(noalias) void f();   // C4559  
```