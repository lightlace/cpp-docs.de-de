---
title: while-Anweisung (C) | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- while
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: e383ae0646bdf15c38f6537de0adec9bb9468486
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="while-statement-c"></a>while-Anweisung (C)
Mit der `while`-Anweisung können Sie eine Anweisung solange wiederholen, bis ein angegebener Ausdruck den Wert "false" aufweist.  
  
## <a name="syntax"></a>Syntax  
 *iteration-statement*:  
 **while (**  *expression*  **)**  *statement*  
  
 Der *Ausdruck* muss einen arithmetischen Typ oder einen Zeigertyp aufweisen. Die Ausführung erfolgt folgendermaßen:  
  
1.  Der *Ausdruck* wird ausgewertet.  
  
2.  Wenn der *Ausdruck* zu Beginn den Wert „false“ hat, wird der Text der `while`-Anweisung nicht ausgeführt, und das Steuerelement wird von der `while`-Anweisung an die nächste Anweisung im Programm übergeben.  
  
     Wenn der *Ausdruck* den Wert „true“ hat (ungleich null), wird der Text der Anweisung ausgeführt und der Prozess ab Schritt 1 wiederholt.  
  
 Die `while`-Anweisung kann auch beendet werden, wenn eine **break**-, `goto`- oder `return`-Anweisung im Anweisungstext ausgeführt wird. Verwenden Sie die **continue**-Anweisung, um eine Iteration zu beenden, ohne die `while`-Schleife zu beenden. Die **continue**-Anweisung übergibt das Steuerelement an die nächste Iteration der `while`-Anweisung.  
  
 In diesem Beispiel wird die `while`-Anweisung veranschaulicht:  
  
```  
while ( i >= 0 )   
{  
    string1[i] = string2[i];  
    i--;  
}  
```  
  
 In diesem Beispiel werden Zeichen aus `string2` nach `string1` kopiert. Wenn `i` größer als oder gleich 0 ist, wird `string2[i]` an `string1[i]` zugewiesen und `i` dekrementiert. Wenn `i` 0 erreicht oder niedriger ist, wird die Ausführung der `while`-Anweisung beendet.  
  
## <a name="see-also"></a>Siehe auch  
 [while-Anweisung (C++)](../cpp/while-statement-cpp.md)
