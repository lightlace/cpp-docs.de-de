---
title: Compilerfehler C2951 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2951
dev_langs:
- C++
helpviewer_keywords:
- C2951
ms.assetid: c6f95aa2-c894-425b-a51c-d40d70c8daa1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0883b0942fdfbe3d55a540fbed35a0affc73be5b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2951"></a>Compilerfehler C2951
Deklarationen von Typen dürfen nur im globalen, Namespace- oder Klassengültigkeitsbereich  
  
 Eine generische oder Vorlagenklasse außerhalb des globalen oder Namespacebereich nicht deklariert werden. Wenn Sie die generische oder Vorlagenklasse Deklarationen in einer Includedatei vornehmen, stellen Sie sicher, dass die Include-Datei im globalen Gültigkeitsbereich ist.  
  
 Im folgenden Beispiel wird C2951 generiert:  
  
```  
// C2951.cpp  
template <class T>  
class A {};  
  
int main() {  
   template <class T>   // C2951  
   class B {};  
}  
```  
  
 C2951 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2951b.cpp  
// compile with: /clr /c  
  
// OK  
generic <class T>   
ref class GC { };  
  
int main() {  
   generic <class T> ref class GC2 {};   // C2951  
}  
```