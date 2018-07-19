---
title: Compilerfehler Fehler C2071 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2071
dev_langs:
- C++
helpviewer_keywords:
- C2071
ms.assetid: f8c09255-a5c4-47e3-8089-3d875ae43cc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: faee56023d14e9b010d1c691af654ffcbc31dc78
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169204"
---
# <a name="compiler-error-c2071"></a>Compilerfehler Fehler C2071
'Bezeichner': Ungültige Speicherklasse  
  
 `identifier` wurde mit einem ungültigen deklariert [Speicherklasse](../../c-language/c-storage-classes.md). Dieser Fehler kann verursacht werden, wenn mehr als eine Speicherklasse für einen Bezeichner angegeben ist oder wenn die Definition mit der Speicherklassen-Deklaration nicht kompatibel ist.  
  
 Verstehen Sie zur Behebung dieses Problems die beabsichtigte Speicherklasse des Bezeichners – z. B. `static` oder `extern`–, und korrigieren Sie die Deklaration zur Übereinstimmung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2071 generiert.  
  
```  
// C2071.cpp  
// compile with: /c  
struct C {  
   extern int i;   // C2071  
};  
struct D {  
   int i;   // OK, no extern on an automatic  
};  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C2071 generiert.  
  
```  
// C2071_b.cpp  
// compile with: /c  
typedef int x(int i) { return i; }   // C2071  
typedef int (x)(int);   // OK, no local definition in typedef  
```