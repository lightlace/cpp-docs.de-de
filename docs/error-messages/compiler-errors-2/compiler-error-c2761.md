---
title: Compiler-Fehler C2761 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2761
dev_langs:
- C++
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 62c505b5219cb76ad83c3b6ece13e7d10f16e555
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2761"></a>Compiler-Fehler C2761 generiert
'Funktion': Member-Funktion Neudeklaration nicht zulässig  
  
 Sie können keine Memberfunktion zu deklarieren. Sie können definieren, jedoch nicht zu deklarieren.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2761 generiert.  
  
```  
// C2761.cpp  
class a {  
   int t;  
   void test();  
};  
  
void a::a;     // C2761  
void a::test;  // C2761  
  
```  
  
## <a name="example"></a>Beispiel  
 Nicht statische Member einer Klasse oder Struktur können nicht definiert werden.  Im folgende Beispiel wird C2761 generiert.  
  
```  
// C2761_b.cpp  
// compile with: /c  
struct C {  
   int s;  
   static int t;  
};  
  
int C::s;   // C2761  
int C::t;   // OK  
```