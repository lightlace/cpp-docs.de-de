---
title: Compilerfehler C2513 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2513
dev_langs:
- C++
helpviewer_keywords:
- C2513
ms.assetid: ab5b21d3-61e2-4df7-8eea-6f14d6ba8620
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 704e5d71301886d46c8a2ce08d7ea34ef1f8275a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33228257"
---
# <a name="compiler-error-c2513"></a>Compilerfehler C2513
'Typ': keine Variable vor '=' deklariert  
  
 Der Typspezifizierer wird in der Deklaration mit keine Variablenbezeichner angezeigt.  
  
 Im folgenden Beispiel wird C2513 generiert:  
  
```  
// C2513.cpp  
int main() {  
   int = 9;   // C2513  
   int i = 9;   // OK  
}  
```  
  
 Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Compiler für Visual Studio .NET 2003 durchgeführt generiert werden: die Initialisierung einer typedef, die nicht mehr erlaubt. Die Initialisierung einer TypeDef ist gemäß dem Standard nicht zulässig und wird nun ein Compilerfehler generiert.  
  
```  
// C2513b.cpp  
// compile with: /c  
typedef struct S {  
   int m_i;  
} S = { 1 };   // C2513  
// try the following line instead  
// } S;  
```  
  
 Eine Alternative wäre löschen `typedef` zum Definieren einer Variablen mit aggregierter Initialisiererliste angezeigt, aber dies werden nicht empfohlen, da erstellt es eine Variable mit dem gleichen Namen wie der Typ und den Typnamen ausblenden.