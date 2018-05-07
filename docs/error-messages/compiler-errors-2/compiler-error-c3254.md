---
title: Compilerfehler C3254 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3254
dev_langs:
- C++
helpviewer_keywords:
- C3254
ms.assetid: 93427b10-fa72-4e43-80d1-1a6e122f9f40
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e58976b1562e6cca9aa343401b5d2c3f856de1a9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3254"></a>Compilerfehler C3254
"explizite Override": Klasse enthält explizites Überschreiben "Override" jedoch nicht von einer Schnittstelle, die die Funktionsdeklaration enthält  
  
 Wenn Sie [explizit überschreiben](../../cpp/explicit-overrides-cpp.md) eine Methode, Klasse, die die Außerkraftsetzung enthält leiten, direkt oder indirekt, überschreiben Sie aus dem Typ, der die Funktion enthält.  
  
 Im folgende Beispiel wird C3254 generiert:  
  
```  
// C3254.cpp  
__interface I  
{  
   void f();  
};  
  
__interface I1 : I  
{  
};  
  
struct A /* : I1 */  
{  
   void I1::f()  
   {   // C3254, uncomment : I1 to resolve this C3254  
   }  
};  
  
int main()  
{  
}  
```