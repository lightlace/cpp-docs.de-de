---
title: Compilerwarnung (Stufe 1) C4530 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4530
dev_langs: C++
helpviewer_keywords: C4530
ms.assetid: a04dcdb2-84db-459d-9e5e-4e743887465f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adfa006e3b84517601237bbd844ac983115e74ec
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4530"></a>Compilerwarnung (Stufe 1) C4530
C++-Ausnahmehandler verwendet, aber entladungssemantik sind nicht aktiviert. Geben Sie/EHsc  
  
 C++-Ausnahmebehandlung verwendet wurde, aber [/EHsc /](../../build/reference/eh-exception-handling-model.md) wurde nicht ausgewählt.  
  
 Wenn die Option/EHsc / nicht aktiviert wurde, wird ein Objekt mit der automatischen Speicher im Bereich zwischen der Funktion, die auf diese Weise das Auslösen und Abfangen der Throw-Funktion nicht gelöscht werden. Allerdings erstellt ein Objekt mit der automatischen Speicher eine **versuchen Sie es** oder **catch** Block werden gelöscht.  
  
 Im folgenden Beispiel wird C4530 generiert:  
  
```  
// C4530.cpp  
// compile with: /W1  
int main() {  
   try{} catch(int*) {}   // C4530  
}  
```  
  
 Kompilieren Sie das Beispiel mit/EHsc, um die Warnung zu beheben.