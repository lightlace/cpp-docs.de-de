---
title: "\"void\" (C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- void_cpp
dev_langs:
- C++
helpviewer_keywords:
- void keyword [C++]
- functions [C++], void
- pointers, void
ms.assetid: d203edba-38e6-4056-8b89-011437351057
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: dea06f16979fab9aa4494b172d6d95193a9f3727
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="void-c"></a>void (C++)
Wenn es als Funktionsrückgabetyp verwendet wird, legt das `void`-Schlüsselwort fest, dass die Funktion keinen Wert zurückgibt. Wenn es für die Parameterliste einer Funktion verwendet wird, gibt "void" an, dass die Funktion keine Parameter akzeptiert. Bei Verwendung in der Deklaration eines Zeigers gibt "void" an, dass der Zeiger "universal" ist.  
  
 Wenn der Typ eines Zeigers ist **"void" \* **, der Zeiger auf jede Variable, die nicht mit deklariert wird verweisen die **const** oder `volatile` Schlüsselwort. Ein void-Zeiger kann nicht dereferenziert werden, es sei denn, er wird in einen anderen Typ umgewandelt. Ein void-Zeiger kann in jeden anderen Datenzeigertyp konvertiert werden.  
  
 Ein void-Zeiger kann auf eine Funktion, jedoch nicht auf einen Klassenmember in C++ zeigen.  
  
 Eine Variable vom Typ "void" kann nicht deklariert werden.  
  
## <a name="example"></a>Beispiel  
  
```  
// void.cpp  
void vobject;   // C2182  
void *pv;   // okay  
int *pint; int i;  
int main() {  
   pv = &i;  
   // Cast optional in C required in C++  
   pint = (int *)pv;  
}   
```  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Grundlegende Typen](../cpp/fundamental-types-cpp.md)