---
title: Compilerfehler C2959 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2959
dev_langs:
- C++
helpviewer_keywords:
- C2959
ms.assetid: d66bb2a8-70c3-4209-a358-b0c47f111a50
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce13a340812bce7cd6e5a0e4f8b2601b530fd3a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2959"></a>Compilerfehler C2959
eine generische Klasse oder Funktion möglicherweise nicht Mitglied einer Vorlage  
  
 Weitere Informationen finden Sie unter [Windows-Runtime und verwaltete Vorlagen](../../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md) und [Generika](../../windows/generics-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2959 generiert.  
  
```  
// C2959.cpp  
// compile with: /clr /c  
template <class T> ref struct S {  
   generic <class U> ref struct GR1;   // C2959  
};  
```