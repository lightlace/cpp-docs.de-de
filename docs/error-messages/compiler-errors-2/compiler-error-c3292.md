---
title: Compilerfehler C3292 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3292
dev_langs:
- C++
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b5bad02a4c7eae9a30855596ccb1695430c4f15e
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3292"></a>Compilerfehler C3292
Der cli-Namespace kann nicht erneut geöffnet werden.  
  
 Der cli-Namespace kann nicht in Ihrem Code deklariert werden.  Weitere Informationen finden Sie unter [Plattform, Default- und Cli-Namespaces](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3292 generiert:  
  
```  
// C3292.cpp  
// compile with: /clr /c  
namespace cli {};   // C3292  
```
