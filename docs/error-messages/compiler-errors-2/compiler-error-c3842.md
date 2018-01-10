---
title: Compilerfehler C3842 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3842
dev_langs: C++
helpviewer_keywords: C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ee13fc3bf1ecface79550ca8ccad2d45b8e4a03e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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