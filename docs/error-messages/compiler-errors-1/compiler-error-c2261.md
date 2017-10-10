---
title: Compilerfehler C2261 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2261
dev_langs:
- C++
helpviewer_keywords:
- C2261
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8269b891ed899501625973b81c1823d4db2d56c8
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2261"></a>Compilerfehler C2261
"Zeichenfolge": Assemblyverweis ist ungültig und kann nicht aufgelöst werden  
  
 Ein Wert war ungültig.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>Dient zum Angeben einer Friend-Assembly. Z. B. wenn a.dll b.dll als Friend-Assembly angeben möchte, würden Sie angeben (in a.dll): InternalsVisibleTo("b"). Der Laufzeit ermöglicht dann b.dll auf alles in a.dll (mit Ausnahme der private Typen).  
  
 Weitere Informationen über die richtige Syntax beim Angeben von Friend-Assemblys finden Sie unter [Friend-Assemblys (C++)](../../dotnet/friend-assemblies-cpp.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2261 generiert.  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```
