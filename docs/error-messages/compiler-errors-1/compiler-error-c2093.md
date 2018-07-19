---
title: Compiler-Fehler C2093 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2093
dev_langs:
- C++
helpviewer_keywords:
- C2093
ms.assetid: 17529a70-9169-46b5-9fc6-57a5ce224e6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11419a7df335bd87077759228be1256c92d09caa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170712"
---
# <a name="compiler-error-c2093"></a>Compiler-Fehler C2093 generiert
'variable1': kann nicht mit der Adresse der automatischen Variablen 'variable2' initialisiert werden  
  
 Beim Kompilieren mit ["/ Za"](../../build/reference/za-ze-disable-language-extensions.md), das Programm versucht, die Adresse einer automatischen Variablen als Initialisierer zu verwenden.  
  
 Im folgende Beispiel wird C2093 generiert:  
  
```  
// C2093.c  
// compile with: /Za /c  
void func() {  
   int li;   // an implicit auto variable  
   int * s[]= { &li };   // C2093 address is not a constant  
  
   // OK  
   static int li2;  
   int * s2[]= { &li2 };  
}  
```