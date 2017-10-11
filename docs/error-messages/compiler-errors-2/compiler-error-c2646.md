---
title: Compiler-Fehler C2646 generiert | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2646
dev_langs:
- C++
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 353f65b4d9702ed82ff92eae63fcedaa6adba227
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
