---
title: Compiler-Fehler C2764 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2764
dev_langs:
- C++
helpviewer_keywords:
- C2764
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd07a00e701804a56f74c86e8a0aedf67e470320
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33236445"
---
# <a name="compiler-error-c2764"></a>Compiler-Fehler C2764 generiert
'Param': Template-Parameter nicht verwendet oder in die teilweise Spezialisierung "Spezialisierung" ableitbar  
  
 Ein Template-Parameter wird nicht in eine teilweise Spezialisierung verwendet. Dadurch wird die teilweise Spezialisierung kann nicht verwendet werden, da die Vorlagenparameter nicht abgeleitet werden kann.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2764 generiert:  
  
```  
// C2764.cpp  
#include <stdio.h>  
template <class T1, class T2>  
struct S  {  
   int m_i;  
};  
  
template <class T1, class T2>  
struct S<int, T2*> {   // C2764  
// try the following line instead  
// struct S<T1(*)(T2), T2*> {  
   char m_c;  
};  
  
int main() {  
   S<int, char> s1;  
   S<void (*)(short), short *> s2;  
   s2.m_c = 10;  
   s1.m_i = s2.m_c;  
   printf_s("%d\n", s1.m_i);  
}  
```