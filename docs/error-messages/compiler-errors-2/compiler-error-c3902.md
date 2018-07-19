---
title: Compilerfehler C3902 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3902
dev_langs:
- C++
helpviewer_keywords:
- C3902
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0430ab95ae4884c420a3f7153fbbbbc4f7931675
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278196"
---
# <a name="compiler-error-c3902"></a>Compilerfehler C3902
'Accessor': Typ des letzten Parameters muss 'Type'  
  
 Der Typ des letzten Parameters mindestens eine Set-Methode muss dem Typ der Eigenschaft entsprechen. Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3902 generiert:  
  
```  
// C3902.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String ^Name {  
      void set(int);   // C3902  
      // try the following line instead  
      // void set(String^){}  
   }  
  
   property double values[int,int] {  
      void set(int, int, float);   // C3902  
      // try the following line instead  
      // void set(int, int, double){}  
   }  
};  
```