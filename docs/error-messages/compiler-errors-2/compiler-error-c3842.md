---
title: Compilerfehler C3842 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3842
dev_langs:
- C++
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c29878f7d64bfe1ed444130c77461dece6d20302
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3842"></a>Compilerfehler C3842
Die Qualifizierer 'function': 'const' und 'volatile' in Memberfunktionen von WinRT oder verwalteten Typen werden nicht unterstützt.  
  
 [const](../../cpp/const-cpp.md) und [volatile](../../cpp/volatile-cpp.md) werden in Memberfunktionen von WinRT oder verwalteten Typen nicht unterstützt.  
  
 Im folgenden Beispiel wird C3842 generiert:  
  
```  
// C3842a.cpp  
// compile with: /clr /c  
public ref struct A {  
   void f() const {}   // C3842  
   void f() volatile {}   // C3842  
  
   void f() {}  
};  
```