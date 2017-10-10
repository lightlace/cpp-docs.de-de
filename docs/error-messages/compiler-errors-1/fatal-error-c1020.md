---
title: Schwerwiegender Fehler C1020 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1020
dev_langs:
- C++
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c2689b2526b2cf9dc513052e292aca429113c129
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

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
