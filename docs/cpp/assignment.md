---
title: Zuweisung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27e78f7429c4d2a0f83ff7184460eb2ae69df129
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960985"
---
# <a name="assignment"></a>Zuweisung
Der Zuweisungsoperator (**=**) ist strenggenommen ein binärer Operator. Seine Deklaration ist mit jedem anderen binären Operator identisch, mit den folgenden Ausnahmen:  
  
-   Es muss eine nicht statische Memberfunktion sein. Keine **Operator =** kann als nichtmemberfunktion deklariert werden.  
  
-   Es wird nicht von abgeleiteten Klassen geerbt.  
  
-   Eine standardmäßige **Operator =** Funktion kann vom Compiler für Klassentypen generiert werden, wenn keiner vorhanden ist.  
  
 Das folgende Beispiel veranschaulicht, wie Sie einen Zuweisungsoperator deklarieren:  
  
```cpp 
// assignment.cpp  
class Point  
{  
public:  
   Point &operator=( Point & );  // Right side is the argument.  
   int _x, _y;  
};  
  
// Define assignment operator.  
Point &Point::operator=( Point &ptRHS )  
{  
   _x = ptRHS._x;  
   _y = ptRHS._y;  
  
   return *this;  // Assignment operator returns left side.  
}  
  
int main()  
{  
}  
```  
  
 Beachten Sie, dass das angegebene Argument die rechte Seite des Ausdrucks ist. Der Operator gibt das Objekt zurück, um das Verhalten des Zuweisungsoperators beizubehalten, der den Wert des linken Rands zurückgibt, nachdem die Zuweisung abgeschlossen ist. So können Anweisungen geschrieben werden wie:  
  
```cpp 
pt1 = pt2 = pt3;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorüberladung](../cpp/operator-overloading.md)