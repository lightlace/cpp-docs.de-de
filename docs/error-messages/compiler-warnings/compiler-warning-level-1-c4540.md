---
title: Compilerwarnung (Stufe 1) C4540 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4540
dev_langs: C++
helpviewer_keywords: C4540
ms.assetid: 8085e748-5f4d-43c2-b06d-eaf794edbf72
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aaaef1edaa6af093ae03fe69231a9686e3d087a7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4540"></a>Compilerwarnung (Stufe 1) C4540
Dynamic_cast zum Konvertieren in nicht zugegriffen werden kann oder mehrdeutige Basisklasse; Laufzeittest fehl ("Typ1" in "Typ2")  
  
 Sie verwendet `dynamic_cast` von einem Typ in einen anderen konvertieren. Der Compiler bestimmt, dass die Umwandlung immer fehlschlägt (zurückgeben **NULL**) ist eine Basisklasse kann nicht zugegriffen werden (`private`, z. B.) oder mehrdeutig (mehrmals in der Klassenhierarchie für die Instanz).  
  
 Das folgende Beispiel zeigt ein Beispiel für diese Warnung. Klasse **B** Klasse abgeleitet ist **ein**. Die Anwendung verwendet `dynamic_cast` von Klasse umgewandelt **B** (der abgeleiteten Klasse) Klasse **ein**, dem schlägt immer fehl, da Klasse **B** ist `private` und somit kann nicht zugegriffen werden. Ändern den Zugriff des **ein** auf **öffentlichen** die Warnung aufgelöst wird.  
  
```  
// C4540.cpp  
// compile with: /W1  
  
struct A {   
   virtual void g() {}  
};  
  
struct B : private A {  
   virtual void g() {}  
};  
  
int main() {  
   B b;  
   A * ap = dynamic_cast<A*>(&b);   // C4540  
}  
```