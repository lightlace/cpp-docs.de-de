---
title: Compiler-Fehler C2663 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2663
dev_langs:
- C++
helpviewer_keywords:
- C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f39f516b32aaf1159d47726d01623e253ee8b383
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2663"></a>Compiler-Fehler C2663 generiert
"Function": Anzahl Überladungen haben keine zulässige Konvertierung für den this-Zeiger  
  
 Der Compiler konnte nicht konvertiert werden `this` auf eine der überladenen Versionen der Memberfunktion.  
  
 Dieser Fehler kann verursacht werden, durch den Aufruf einer nicht -`const` Member-Funktion auf einem `const` Objekt.  Folgende Lösungen möglich:  
  
1.  Entfernen Sie die `const` aus der Deklaration des Objekts.  
  
2.  Hinzufügen `const` auf eine der Überladungen der Member-Funktion.  
  
 Im folgende Beispiel wird C2663 generiert:  
  
```  
// C2663.cpp  
struct C {  
   void f() volatile {}  
   void f() {}  
};  
  
struct D {  
   void f() volatile;  
   void f() const {}  
};  
  
const C *pcc;  
const D *pcd;  
  
int main() {  
   pcc->f();    // C2663  
   pcd->f();    // OK  
}  
```