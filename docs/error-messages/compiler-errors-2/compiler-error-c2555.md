---
title: Compilerfehler C2555 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d2d1a710177e2c8c72b0afeff662dddf1c22ef5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230583"
---
# <a name="compiler-error-c2555"></a>Compilerfehler C2555
"Class1:: function1": Überschreiben der virtuellen Funktion-Rückgabetyp unterscheidet sich und ist nicht von "Class2:: function2" kovariant  
  
 Eine virtuelle Funktion und die abgeleiteten überschreibenden Funktion haben identische Parameterlisten jedoch unterschiedliche Rückgabetypen. Eine überschreibende Funktion in einer abgeleiteten Klasse kann nicht von einer virtuellen Funktion in einer Basisklasse nur durch ihren Rückgabetyp unterscheiden.  
  
 Zum Beheben dieses Fehlers umgewandelt zurückgegeben, nachdem die virtuelle Funktion aufgerufen wurde.  
  
 Dieser Fehler kann auch angezeigt, wenn Sie mit "/ CLR" kompiliert.   Z. B. Visual C++, die folgende C#-Deklaration entspricht:  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 echt  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 Weitere Informationen zu C2555 finden Sie in der Knowledge Base-Artikel Q240862.  
  
 Im folgenden Beispiel wird C2555 generiert:  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```