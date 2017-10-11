---
title: Compilerfehler C3463 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3463
dev_langs:
- C++
helpviewer_keywords:
- C3463
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 2c5f79f76329277fa24e90eaa0ab32209cafe6c0
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3463"></a>Compilerfehler C3463
"Typ": Der Typ ist im implements-Attribut nicht zulässig.  
  
 Ein ungültiger Typ wurde an das [implements](../../windows/implements-cpp.md) -Attribut übergeben. Beispielsweise können Sie eine Schnittstelle an `implements`übergeben, Sie können aber keinen Zeiger an eine Schnittstelle übergeben.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3463 generiert:  
  
```  
// C3463.cpp  
// compile with: /c  
#include <windows.h>  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface X {};  
  
typedef X* PX;  
  
[ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=PX) ]   // C3463  
// try the following line instead  
// [ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=X) ]  
class CMyClass : public X {};  
```
