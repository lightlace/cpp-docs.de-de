---
title: Compilerfehler C2920 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2920
dev_langs:
- C++
helpviewer_keywords:
- C2920
ms.assetid: 0a4cb2de-00a0-4209-8160-c7ce6ed7d9ab
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 50d1995bd27417a6e0e70b9fee86cbcc8ece84fe
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2920"></a>Compilerfehler C2920
Neudefinition: 'class': Klassenvorlage oder Generika wurde bereits als 'type' deklariert  
  
 Eine generische oder Vorlagenklasse weist mehrere Deklarationen auf, die nicht identisch sind. Verwenden Sie zum Beheben dieses Fehlers unterschiedliche Name für unterschiedlichen Typen, oder entfernen Sie die Neudefinition des Typnamens.  
  
 Im folgenden Beispiel wird C2920 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2920.cpp  
// compile with: /c  
typedef int TC1;  
template <class T>   
struct TC1 {};   // C2920  
struct TC2 {};   // OK - fix by using a different name  
```  
  
 C2920 kann auch auftreten, wenn Generika verwendet werden:  
  
```  
// C2920b.cpp  
// compile with: /clr /c  
typedef int GC1;  
generic <class T>   
ref struct GC1 {};   // C2920  
ref struct GC2 {};   // OK - fix by using a different name  
```