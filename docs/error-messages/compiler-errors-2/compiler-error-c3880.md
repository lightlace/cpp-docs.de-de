---
title: Compilerfehler C3880 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3880
dev_langs:
- C++
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 5e86108e0ab2608f7f59f160d9f7a849b83ef71a
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3880"></a>Compilerfehler C3880
"Var": nicht mit ein literal-Datenmember  
  
 Der Typ des eine [literal](../../windows/literal-cpp-component-extensions.md) Attribut sein muss, oder der Zeitpunkt der Kompilierung konvertierbar auf einen der folgenden Typen:  
  
-   Ganzzahltyp  
  
-   string  
  
-   Aufzählung mit der eine ganze Zahl oder einen zugrunde liegenden Typ  
  
 Im folgende Beispiel wird C3880 generiert:  
  
```  
// C3880.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal System::Decimal staticConst1 = 10;   // C3880  
   literal int staticConst2 = 10;   // OK  
};  
```
