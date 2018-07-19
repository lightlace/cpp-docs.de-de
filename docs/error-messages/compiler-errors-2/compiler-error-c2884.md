---
title: Compilerfehler C2884 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2884
dev_langs:
- C++
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41bacfc53f8b1f14a9b7409a43db39fd943739e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33261467"
---
# <a name="compiler-error-c2884"></a>Compilerfehler C2884
"Name": von using-Deklaration steht in Konflikt mit lokalen Funktion 'Funktion' eingeführt  
  
 Sie haben versucht, eine Funktion mehr als einmal zu definieren. Die erste Definition ist eine lokale Definition. Die zweite besteht aus einem Namespace mit einem `using` Deklaration.  
  
 Im folgende Beispiel wird C2884 generiert:  
  
```  
// C2884.cpp  
namespace A {  
   void z(int);  
}  
  
void f() {  
   void z(int);  
   using A::z;   // C2884 z is already defined  
}  
```