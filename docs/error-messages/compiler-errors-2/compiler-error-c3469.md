---
title: Compilerfehler C3469 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3469
dev_langs:
- C++
helpviewer_keywords:
- C3469
ms.assetid: e23b0e5c-c704-4e67-a868-bf02c2055d85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f9ddd172678ea9895bb5daa32e7a325ed8eaa01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3469"></a>Compilerfehler C3469
'typ': Eine generische Klasse kann nicht weitergeleitet werden.  
  
 Typweiterleitung kann nicht für generische Klassen verwendet werden.  
  
 Weitere Informationen finden Sie unter [Typweiterleitung (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Komponente erstellt:  
  
```  
// C3469.cpp  
// compile with: /clr /LD  
generic<typename T>  
public ref class GR {};  
  
public ref class GR2 {};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3466 generiert:  
  
```  
// C3469_b.cpp  
// compile with: /clr /c  
#using "C3469.dll"  
[assembly:TypeForwardedTo(GR::typeid)];   // C3469  
[assembly:TypeForwardedTo(GR2::typeid)];   // OK  
```