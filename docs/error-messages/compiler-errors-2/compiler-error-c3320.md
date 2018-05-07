---
title: Compilerfehler C3320 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3320
dev_langs:
- C++
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 08810d38b74081cfb8573d1e33ea3a8ec4dabd4c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3320"></a>Compilerfehler C3320
'Typ': Typ kann nicht den gleichen Namen besitzen wie die name-Moduleigenschaft.  
  
Ein exportierter benutzerdefinierten Typ (UDT), die eine Struktur, Klasse, Enumeration oder Union sein könnte, kann nicht denselben Namen aufweisen, wie der Parameter, die an die [Modul](../../windows/module-cpp.md) Name-Eigenschaft des Attributs.  
  
## <a name="example"></a>Beispiel  
Im folgenden Beispiel wird C3320 generiert:  
  
```cpp  
// C3320.cpp  
#include "unknwn.h"  
[module(name="xx")];  
  
[export] struct xx {   // C3320  
// Try the following line instead  
// [export] struct yy {  
   int i;  
};  
```