---
title: Compilerfehler C3291 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3291
dev_langs:
- C++
helpviewer_keywords:
- C3291
ms.assetid: ed2e9f89-8dbc-4387-bc26-cc955e840858
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: da6145b3a3aecd5f550a58c009020fb24280349e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3291"></a>Compilerfehler C3291
"default": Kann nicht der Name einer trivial-Eigenschaft sein.  
  
 Eine trivial-Eigenschaft kann nicht als `default`benannt werden. Weitere Informationen finden Sie unter [property](../../windows/property-cpp-component-extensions.md) .  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3291 generiert:  
  
```  
// C3291.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String ^ default;   // C3291  
   property System::String ^ Default;   // OK  
};  
```
