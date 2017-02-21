---
title: "Compilerwarnung (Stufe 4) C4764 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4764"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4764"
ms.assetid: 7bd4296f-966b-484c-bf73-8dbc8e85b4a9
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung (Stufe 4) C4764
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Ausrichtung von catch\-Objekten kann nicht mehr als 16 Bytes betragen.  
  
 Es wurde eine Ausrichtung angegeben, die mehr als 16 Bytes beträgt. Auf einigen Plattformen erzwingt der Stapel jedoch eine Ausrichtung von nicht mehr als 16 Bytes, wenn die Funktion eine Ausnahme auslöst.  
  
## Beispiel  
 Im folgenden Beispiel wird C4764 generiert.  
  
```  
// C4764.cpp // compile with: /W4 /EHsc // processor: x64 IPF #include <stdio.h> class A { public: int x; }; typedef __declspec(align(32)) A ALIGNEDA; int main() { ALIGNEDA a; try { a.x = 15; throw a; } catch (ALIGNEDA b) // can’t align b to > 16 bytes { printf_s("%d\n", b.x); } }   // C4764  
```