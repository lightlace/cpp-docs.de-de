---
title: Compiler-Fehler C2786 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2786
dev_langs: C++
helpviewer_keywords: C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d78b5664fa2853a3fe8f7934cba9ce5b8b3f782a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2786"></a>Compiler-Fehler C2786 generiert
'Typ': Ungültiger Operand für __uuidof  
  
 Die [__uuidof](../../cpp/uuidof-operator.md) -Operator hat einen benutzerdefinierten Typ mit einer GUID verbundenen oder ein Objekt eines solchen benutzerdefinierten Typs.  Mögliche Ursachen:  
  
1.  Das Argument ist kein benutzerdefinierten Typ.  
  
2.  `__uuidof`die GUID kann nicht aus dem Argument registriert werden.  
  
 Im folgende Beispiel wird C2786 generiert:  
  
```  
// C2786.cpp  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
  
int main() {  
   __uuidof(int);   // C2786  
   __uuidof(int *);   // C2786  
   __uuidof(A **);   // C2786  
  
   // no error  
   __uuidof(A);  
   __uuidof(A *);  
   __uuidof(A &);  
   __uuidof(A[]);  
  
   int i;  
   int *pi;  
   A **ppa;  
  
   __uuidof(i);      // C2786  
   __uuidof(pi);     // C2786  
   __uuidof(ppa);    // C2786  
}  
```