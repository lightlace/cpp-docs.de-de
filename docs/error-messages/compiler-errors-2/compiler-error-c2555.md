---
title: Compilerfehler C2555 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2555
dev_langs:
- C++
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 64f66bf80e8e4b6ba7477691cb9675cec347807d
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2555"></a>Compilerfehler C2555
"Class1:: function1": Überschreiben der virtuellen Funktion-Rückgabetyp unterscheidet sich und ist nicht von "Class2:: function2" kovariant  
  
 Eine virtuelle Funktion und die abgeleiteten überschreibenden Funktion haben identische Parameterlisten jedoch unterschiedliche Rückgabetypen. Eine überschreibende Funktion in einer abgeleiteten Klasse kann nicht von einer virtuellen Funktion in einer Basisklasse nur durch ihren Rückgabetyp unterscheiden.  
  
 Zum Beheben dieses Fehlers umgewandelt zurückgegeben, nachdem die virtuelle Funktion aufgerufen wurde.  
  
 Dieser Fehler kann auch angezeigt, wenn Sie mit "/ CLR" kompiliert.   Z. B. Visual C++, die folgende C#-Deklaration entspricht:  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 ist  
  
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
