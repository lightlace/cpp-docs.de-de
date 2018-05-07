---
title: Compilerwarnung (Stufe 3) C4800 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4800
dev_langs:
- C++
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ed4b14ae2f3af3218909d6cd4609f1f45d3d7cc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4800"></a>Compilerwarnung (Stufe 3) C4800  
  
> "*Typ*": erzwungen wird Wert Bool 'True' oder 'False' (Leistung Warnung)  
  
Diese Warnung wird generiert, wenn ein Wert, der nicht ist `bool` zugewiesen oder in den Typ umgewandelt `bool`. Diese Meldung wird in der Regel durch Zuweisen verursacht `int` Variablen `bool` Variablen, in denen die `int` Variable enthält nur die Werte **"true"** und **"false"**, werden konnte neu deklariert als Typ `bool`. Wenn Sie den Ausdruck zum Typ schreiben können nicht `bool`, hinzufügen "`!=0`" mit dem Ausdruck, der den Ausdruckstyp bietet `bool`. Den Ausdruck in den Typ umwandeln `bool` nicht die Warnung standardmäßig ist deaktiviert.  
  
Diese Warnung wird nicht mehr in Visual Studio 2017 generiert.  
  
## <a name="example"></a>Beispiel
  
 Im folgende Beispiel wird die C4800 generiert und gezeigt, wie sie diesen Fehler beheben:  
  
```cpp  
// C4800.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
  
   // To fix, instead try:  
   // bool i = 0;  
  
   bool j = i;   // C4800  
   j++;  
}  
```