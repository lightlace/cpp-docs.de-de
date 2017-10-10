---
title: Compilerfehler C2013 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2013
dev_langs:
- C++
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 23fdceda3b40a657301e8909c6847e9d596eb24d
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2013"></a>Compilerfehler C2013
">" fehlt  
  
 In einer `#include` -Direktive fehlt eine schließende spitze Klammer. Fügen Sie die schließende Klammer hinzu, um den Fehler zu beheben.  
  
 Im folgenden Beispiel wird C2013 generiert:  
  
```  
// C2013.cpp  
#include <stdio.h    // C2013  
```  
  
 Mögliche Lösung:  
  
```  
// C2013b.cpp  
// compile with: /c  
#include <stdio.h>  
```
