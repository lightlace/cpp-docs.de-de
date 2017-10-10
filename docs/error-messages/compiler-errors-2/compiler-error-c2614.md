---
title: Compiler-Fehler C2614 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2614
dev_langs:
- C++
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 077762fef5474b3761c504224c58de83d82bdb12
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2614"></a>Compiler-Fehler C2614 generiert
'Klasse1': Unzulässiger Memberinitialisierung: "Klasse2" ist nicht an eine Basis oder ein Member  
  
 Nur Member oder Basisklassen können in der Initialisierungsliste für eine Klasse oder Struktur angezeigt werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C2614 generiert.  
  
```  
// C2614.cpp  
// compile with: /c  
struct A {  
   int i;  
   A( int ia ) : B( i ) {};   // C2614 B is not a member of A  
};  
  
struct A2 {  
   int B;  
   int i;  
   A2( int ia ) : B( i ) {};   // OK  
};  
```
