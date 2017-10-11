---
title: Compilerfehler C3218 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3218
dev_langs:
- C++
helpviewer_keywords:
- C3218
ms.assetid: 0eea19e0-503e-4e07-ae8b-2cb2e95922cd
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 69ee49ece7354ce713fcfb86368aaca35b06cda7
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3218"></a>Compilerfehler C3218
'Typ': Typ nicht als Einschränkung zulässig.  
  
 Für einen Typ, eine Einschränkung muss er entweder ein Werttyp oder ein Verweis auf eine verwaltete Klasse oder Schnittstelle sein.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3218 generiert.  
  
```  
// C3218.cpp  
// compile with: /clr /c  
class A {};  
ref class B {};  
  
// Delete the following 3 lines to resolve.  
generic <class T>  
where T : A   // C3218  
ref class C {};  
  
// OK  
generic <class T>  
where  T : B  
ref class D {};  
```
