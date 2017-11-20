---
title: Compilerwarnung (Stufe 3) C4414 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4414
dev_langs: C++
helpviewer_keywords: C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 90644170953976d0fb661f1491b59915d5dd3667
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4414"></a>Compilerwarnung (Stufe 3) C4414
'Funktion': short-Sprung zur Funktion konvertiert in near  
  
 Kurze Sprünge erzeugen compact Anweisung, welche in eine Adresse in einen begrenzten Bereich von der Anweisung Verzweigungen. Die Anweisung enthält einen kurze Offset, der den Abstand zwischen den Sprung und die Zieladresse der Definition der Funktion darstellt. Während der Verknüpfung möglicherweise eine Funktion verschoben werden oder Link-Time-Optimierungen, die dazu führen, dass die Funktion außerhalb des Bereichs erreichbar aus einem kurzen Offset verschoben werden. Der Compiler muss einen speziellen Datensatz für den Sprung generieren erfordert die Anweisung jmp NAHER oder ganz sein. Der Compiler versucht, die Konvertierung.  
  
 Im folgende Code wird z. B. C4414 generiert:  
  
```  
// C4414.cpp  
// compile with: /W3 /c  
// processor: x86  
int DoParityEven();  
int DoParityOdd();  
unsigned char global;  
int __declspec(naked) DoParityEither()  
{  
   __asm  
   {  
      test global,0  
      jpe SHORT DoParityEven  // C4414  
      jmp SHORT DoParityOdd   // C4414  
   }  
}  
```