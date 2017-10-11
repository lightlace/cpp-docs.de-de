---
title: Compilerwarnung (Stufe 1 und Stufe 4) C4700 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4700
dev_langs:
- C++
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f41e519a9dbcff3cc5ad4b718003e5964bfc3e85
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>Compilerwarnung (Stufe 1 und Stufe 4) C4700
nicht initialisierten lokalen Variablen 'Name' verwendet  
  
 Sie verwendet die lokale Variable *Namen* ohne ersten Zuweisen eines Werts, was zu unvorhersehbaren Ergebnissen führen kann.  
  
 Im folgenden Beispiel wird C4700 generiert:  
  
```  
// C4700.cpp  
// compile with: /W1  
int main() {  
   int i;  
   return i;   // C4700  
}  
```  
  
 Klicken Sie unter [/CLR: safe](../../build/reference/clr-common-language-runtime-compilation.md) Dies ist eine Warnung der Stufe 4.  Im folgenden Beispiel wird C4700 generiert:  
  
```  
// C4700b.cpp  
// compile with: /W4 /clr:safe /c  
using namespace System;  
int main() {  
   Int32^ bi;  
   return *bi;   // C4700  
}  
```
