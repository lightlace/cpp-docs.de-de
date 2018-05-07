---
title: Compilerfehler C2929 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2929
dev_langs:
- C++
helpviewer_keywords:
- C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7a6069060541f884bfbeb298845f5001b35d561
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2929"></a>Compilerfehler C2929
"Bezeichner": Explizite Instanziierung; Instanziierung eines Elements einer Vorlagenklasse kann nicht explizit erzwungen und unterdrückt werden  
  
 Sie können einen Bezeichner nicht explizit instanziieren und gleichzeitig verhindern, dass er instanziiert wird.  
  
 Im folgenden Beispiel wird C2929 generiert:  
  
```  
// C2929.cpp  
// compile with: /c  
template<typename T>  
class A {  
public:  
   A() {}  
};  
  
template A<int>::A();  
  
extern template A<int>::A();   // C2929  
```