---
title: Compilerfehler C3320 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3320
dev_langs:
- C++
helpviewer_keywords:
- C3320
ms.assetid: 2ef72d9a-1f1d-4b2e-b244-9fd3f3e70cb6
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fbc375682bb42070d49dd08b711926462c17f32b
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
