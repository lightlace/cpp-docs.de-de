---
title: Compilerfehler C2373 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2373
dev_langs:
- C++
helpviewer_keywords:
- C2373
ms.assetid: 7a08bf0b-852d-48be-ba75-70df9f4b5951
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 93e9538b53b278f12af0a3b50566f444d5289362
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2373"></a>Compilerfehler C2373
"Bezeichner": Neudefinition; unterschiedliche Typmodifizierer  
  
 Der Bezeichner wurde bereits mit einem anderen Typmodifizierer deklariert.  
  
 Im folgenden Beispiel wird C2373 generiert:  
  
```  
// C2373.h  
void __clrcall func( void );  
const int i = 20;  
```  
  
 Und anschließend:  
  
```  
// C2373.cpp  
// compile with: /c  
#include "C2373.h"  
extern void __cdecl func( void );   // C2373  
extern void __clrcall func( void );   // OK  
  
extern int i;   // C2373  
extern const int i;   // OK  
```
