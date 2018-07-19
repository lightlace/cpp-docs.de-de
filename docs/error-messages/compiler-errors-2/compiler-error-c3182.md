---
title: Compilerfehler Fehler C3182 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3182
dev_langs:
- C++
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 503ad6d17b197392967681bfdf4e921aa21dc3e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33254621"
---
# <a name="compiler-error-c3182"></a>Compilerfehler Fehler C3182
'Klasse': eine using-Deklaration oder Zugriffsdeklaration für Member ist innerhalb eines verwalteten oder WinRTtype nicht zulässig  
  
 Ein [mit](../../cpp/using-declaration.md) -Deklaration ist in sämtlichen verwalteten Klassen unzulässig.  
  
 Im folgenden Beispiel wird C3182 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C3182a.cpp  
// compile with: /clr /c  
ref struct B {  
   void mf(int) {  
   }  
};  
  
ref struct D : B {  
   using B::mf;   // C3182, delete to resolve  
   void mf(char) {  
   }  
};  
```  
