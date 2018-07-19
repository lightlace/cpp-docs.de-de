---
title: Compiler-Fehler C2614 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2614
dev_langs:
- C++
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a5783abd96e356affb8537f6fec278e368c692a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33229774"
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