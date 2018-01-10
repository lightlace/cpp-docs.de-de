---
title: Compilerwarnung (Stufe 4) C4706 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4706
dev_langs: C++
helpviewer_keywords: C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 824028fb7fd6d563a7f49017eb6b35d1443490bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4706"></a>Compilerwarnung (Stufe 4) C4706
Zuordnung im Bedingungsausdruck  
  
 Das Testintervall in einem bedingten Ausdruck war das Ergebnis einer Zuweisung.  
  
 Eine Zuweisung hat einen Wert (der Wert auf der linken Seite der Zuweisung), der gesetzlich in einem anderen Ausdruck, z. B. einem Testausdruck verwendet werden kann.  
  
 Im folgenden Beispiel wird C4706 generiert:  
  
```  
// C4706a.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a  = b ) // C4706  
   {  
   }  
}  
```  
  
 Die Warnung wird auch auftreten, wenn Sie die Klammern um die testbedingung doppelklicken:  
  
```  
// C4706b.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a  =  b ) ) // C4706  
   {  
   }  
}  
```  
  
 Wenn Sie beabsichtigen, eine Beziehung zu testen und nicht zu einer Zuordnung verwenden die `==` Operator. Z. B. folgende Zeile wird getestet, ob ein und b sind gleich:  
  
```  
// C4706c.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( a == b )  
   {  
   }  
}  
```  
  
 Wenn Sie beabsichtigen, den Test mit dem Wert des Ergebnis einer Zuweisung vornehmen, testen Sie, um sicherzustellen, dass die Zuordnung nicht 0 (null) oder nicht null ist. Der folgende Code generiert diese Warnung z. B. nicht:  
  
```  
// C4706d.cpp  
// compile with: /W4  
int main()  
{  
   int a = 0, b = 0;  
   if ( ( a = b ) != 0 )  
   {  
   }  
}  
```