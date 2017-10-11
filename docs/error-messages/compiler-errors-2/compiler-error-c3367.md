---
title: Compilerfehler C3367 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3367
dev_langs:
- C++
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d1d144399ca42ba321d8f3d11425bf2ff8e65891
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3367"></a>Compilerfehler C3367
'static_member_function': Eine statische Funktion kann nicht zum Erstellen eines ungebundenen Delegaten verwendet werden.  
  
Wenn Sie einen ungebundenen Delegaten aufrufen, müssen Sie eine Instanz eines Objekts übergeben. Da eine statische Memberfunktion über den Klassennamen aufgerufen wird, können Sie nur einen ungebundenen Delegaten mit einer Instanzmemberfunktion instanziieren.  
  
Weitere Informationen über ungebundenen Delegaten finden Sie unter [wie: definieren und verwenden Delegaten (C + c++ / CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
Im folgenden Beispiel wird C3367 generiert:  
  
```cpp  
// C3367.cpp  
// compile with: /clr  
ref struct R {  
   void b() {}  
   static void f() {}  
};  
  
delegate void Del(R^);  
  
int main() {  
   Del ^ a = gcnew Del(&R::b);   // OK  
   Del ^ b = gcnew Del(&R::f);   // C3367  
}  
```
