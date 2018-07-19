---
title: Compilerfehler Fehler C2652 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2652
dev_langs:
- C++
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 576aef31268c0cdce09162fc367358e0ed044429
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232198"
---
# <a name="compiler-error-c2652"></a>Compilerfehler Fehler C2652
'Bezeichner': Unzulässiger Kopierkonstruktor: erster Parameter darf nicht 'Bezeichner' sein  
  
 Der erste Parameter in der Kopierkonstruktor hat denselben Typ wie die Klasse, Struktur oder Union, die für die es definiert ist. Der erste Parameter kann einen Verweis auf den Typ, aber nicht den Typ selbst sein.  
  
 Im folgenden Beispiel wird C2651 generiert:  
  
```  
// C2652.cpp  
// compile with: /c  
class A {  
   A( A );   // C2652 takes an A  
};  
class B {  
   B( B& );   // OK, reference to B  
};  
```