---
title: Compilerwarnung (Stufe 3) C4800 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4800
dev_langs:
- C++
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 687b0dab996bfbfe2ce30d65b86196383c02b914
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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