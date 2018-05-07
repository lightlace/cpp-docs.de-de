---
title: Compilerfehler C2879 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2879
dev_langs:
- C++
helpviewer_keywords:
- C2879
ms.assetid: ac92b645-2394-49de-8632-43d44e0553ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba1738da7d349ecafd9f10f31d8f05ac1f12df0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2879"></a>Compilerfehler C2879
'Symbol': nur ein vorhandener Namespace mit einem Namespace Aliasdefinition ein alternativer Name gegeben werden kann  
  
 Sie können nicht erstellt werden ein [Namespacealias](../../cpp/namespaces-cpp.md#namespace_aliases) auf ein Symbol, das einen Namespace.  
  
 Im folgende Beispiel wird C2879 generiert:  
  
```  
// C2879.cpp  
int main() {  
   int i;  
   namespace A = i;   // C2879 i is not a namespace  
}  
```