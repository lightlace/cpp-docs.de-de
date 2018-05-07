---
title: Compilerfehler C2075 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2075
dev_langs:
- C++
helpviewer_keywords:
- C2075
ms.assetid: 8b1865d2-540b-4117-b982-e7a58a0b6cf7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 689cce77da2193cf4864e46df050287d98b6e46e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2075"></a>Compilerfehler C2075
"Bezeichner": für die Initialisierung eines Arrays sind geschweifte Klammern erforderlich  
  
 Der angegebene Arrayinitialisierer war nicht in geschweifte Klammern eingeschlossen.  
  
 Im folgenden Beispiel wird C2075 generiert:  
  
```  
// C2075.c  
int main() {  
   int i[] = 1, 2, 3 };   // C2075  
}  
```  
  
 Mögliche Lösung:  
  
```  
// C2075b.c  
int main() {  
   int j[] = { 1, 2, 3 };  
}  
```