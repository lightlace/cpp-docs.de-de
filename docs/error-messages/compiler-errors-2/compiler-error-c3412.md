---
title: Compilerfehler C3412 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3412
dev_langs:
- C++
helpviewer_keywords:
- C3412
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c5b2c86b91160eb7ae342b39ea6a63ffad364bb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3412"></a>Compilerfehler C3412
'Template': Vorlage im aktuellen Bereich kann nicht spezialisiert  
  
 Eine Vorlage kann nicht auf Gültigkeitsbereich der Klasse, sondern nur im globalen oder Namespacebereich spezialisiert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3412 generiert.  
  
```  
// C3412.cpp  
template <class T>  
struct S {  
   template <>  
   struct S<int> {};   // C3412 in a class  
};  
```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine mögliche Lösung.  
  
```  
// C3412b.cpp  
// compile with: /c  
template <class T>  
struct S {};  
  
template <>  
struct S<int> {};  
```