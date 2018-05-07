---
title: Schwerwiegender Fehler C1020 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1020
dev_langs:
- C++
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c70727b5e0d83b03099b637e0f768f65d271b05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1020"></a>Schwerwiegender Fehler C1020
Unerwartetes #endif  
  
 Die `#endif` -Direktive hat keine entsprechende `#if`-, `#ifdef`- oder `#ifndef` -Direktive. Stellen Sie sicher, dass jede `#endif` -Direktive über eine entsprechende Direktive verfügt.  
  
 Im folgenden Beispiel wird C1020 generiert:  
  
```  
// C1020.cpp  
#endif     // C1020  
```  
  
 Mögliche Lösung:  
  
```  
// C1020b.cpp  
// compile with: /c  
#if 1  
#endif  
```