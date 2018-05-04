---
title: Übertragung der Steuerung | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- control flow, branching
- control flow, transferring control
ms.assetid: aa51e7f2-060f-4106-b0fe-331f04357423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ee906061c7b51ade818b164c1d371a88ef3d462
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="transfers-of-control"></a>Übertragung der Steuerung
Können Sie die `goto` Anweisung oder eine **Fall** -Bezeichnung in einer `switch` Anweisung, um ein Programm anzugeben, die hinter einem Initialisierer verzweigt. Solcher Code ist nicht zulässig, es sei denn, die Deklaration, die den Initialisierer enthält, befindet sich in einem Block, der von dem Block eingeschlossen wird, in dem die Sprunganweisung auftritt.  
  
 Das folgende Beispiel zeigt eine Schleife, welche die Objekte `total`, `ch` und `i` deklariert und initialisiert. Es gibt auch eine fehlerhafte `goto`-Anweisung, die die Steuerung jenseits eines Initialisierers überträgt.  
  
```  
// transfers_of_control.cpp  
// compile with: /W1  
// Read input until a nonnumeric character is entered.  
int main()  
{  
   char MyArray[5] = {'2','2','a','c'};  
   int i = 0;  
   while( 1 )  
   {  
      int total = 0;  
  
      char ch = MyArray[i++];  
  
      if ( ch >= '0' && ch <= '9' )  
      {  
         goto Label1;  
  
         int i = ch - '0';  
      Label1:  
         total += i;   // C4700: transfers past initialization of i.  
      } // i would be destroyed here if  goto error were not present  
   else  
      // Break statement transfers control out of loop,  
      //  destroying total and ch.  
      break;  
   }  
}  
```  
  
 Im vorherigen Beispiel versucht die `goto`-Anweisung, die Steuerung an der Initialisierung von `i` vorbei zu übergeben. Wenn jedoch `i` zwar deklariert, aber nicht initialisiert ist, wäre die Übertragung gültig.  
  
 Die Objekte `total` und `ch`, deklariert im-Block, der als dient der *Anweisung* von der `while` -Anweisung werden zerstört, wenn dieser Block beendet wird, mit der `break` Anweisung.  
  
