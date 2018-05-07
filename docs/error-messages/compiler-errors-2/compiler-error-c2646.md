---
title: Compiler-Fehler C2646 generiert | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2646
dev_langs:
- C++
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6d4fdd5141c8fafb350110bee838a13b2cd3b1d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2646"></a>Compiler-Fehler C2646 generiert
Eine anonyme Struktur oder Union im globalen Gültigkeitsbereich oder im Namespacebereich muss als statisch deklariert werden.  
  
 Eine anonyme Struktur oder Union verfügt über einen globalen Gültigkeitsbereich oder Namespacebereich, ist jedoch nicht als `static` deklariert.  
  
 Im folgenden Beispiel wird C2646 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2646.cpp  
// compile with: /c  
union { int i; };   // C2646 not static  
  
// OK  
static union { int j; };  
union U { int i; };  
```