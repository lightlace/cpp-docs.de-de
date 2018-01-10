---
title: Compilerwarnung (Stufe 1) C4020 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4020
dev_langs: C++
helpviewer_keywords: C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8baceb4b0ad81b62a4be2bd0edc6bf4b95a4e48a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4020"></a>Compilerwarnung (Stufe 1) C4020 generiert
'Funktion': zu viele aktuelle Parameter  
  
 Die Anzahl der tatsächlichen Parameter in einem Funktionsaufruf überschreitet die Anzahl der formalen Parameter im Funktionsprototyp oder Definition. Der Compiler übergibt die zusätzlichen Parameter entsprechend der Aufrufkonvention der Funktion.  
  
 Im folgende Beispiel wird C4020 generiert:  
  
```  
// C4020.c  
// compile with: /W1 /c  
void f(int);  
int main() {  
   f(1,2);   // C4020  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C4020b.c  
// compile with: /c  
void f(int);  
int main() {  
   f(1);  
}  
```