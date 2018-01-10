---
title: Compilerfehler C3645 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3645
dev_langs: C++
helpviewer_keywords: C3645
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 94745c4cc6edc66ad31acc61a868e1db59795496
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3645"></a>Compilerfehler C3645
'Funktion': __clrcall kann nicht auf Funktionen in nativen Code kompiliert verwendet werden  
  
 Das Vorhandensein einiger Schlüsselwörter in einer Funktion führt dazu, dass die Funktion in systemeigenem Code kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C3645 generiert.  
  
```  
// C3645.cpp  
// compile with: /clr /c  
#pragma unmanaged   
int __clrcall dog() {}   // C3645  
```