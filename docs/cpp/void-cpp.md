---
title: "\"void\" (C++) | Microsoft-Dokumentation"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dbb46302c2ae8834ab9a2a626a3bfb77c41996a2
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461477"
---
# <a name="void-c"></a>void (C++)
Wenn als Rückgabetyp einer Funktion verwendet die **"void"** -Schlüsselwort Gibt an, dass die Funktion keinen Wert zurückgibt. Wenn es für die Parameterliste einer Funktion verwendet wird, gibt "void" an, dass die Funktion keine Parameter akzeptiert. Bei Verwendung in der Deklaration eines Zeigers gibt "void" an, dass der Zeiger "universal" ist.  
  
 Ist der Typ eines Zeigers `void *`, der Zeiger auf eine beliebige Variable, die nicht mit deklariert ist zeigen kann die **const** oder **flüchtige** Schlüsselwort. Ein void-Zeiger kann nicht dereferenziert werden, es sei denn, er wird in einen anderen Typ umgewandelt. Ein void-Zeiger kann in jeden anderen Datenzeigertyp konvertiert werden.  
  
 Ein void-Zeiger kann auf eine Funktion, jedoch nicht auf einen Klassenmember in C++ zeigen.  
  
 Eine Variable vom Typ "void" kann nicht deklariert werden.  
  
## <a name="example"></a>Beispiel  
  
```cpp 
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