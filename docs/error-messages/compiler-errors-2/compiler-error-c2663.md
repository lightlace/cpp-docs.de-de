---
title: Compiler-Fehler C2663 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2663
dev_langs: C++
helpviewer_keywords: C2663
ms.assetid: 1e93e368-fd52-42bf-9908-9b6df467c8c9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a9c0ded6888855528867ec7993bcc28eac8045c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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