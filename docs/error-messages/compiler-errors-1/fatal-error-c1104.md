---
title: Schwerwiegender Fehler C1104 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1104
dev_langs:
- C++
helpviewer_keywords:
- C1104
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 7a3f7fbff36f998716bc6639ccb718b1699ccf80
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1104"></a>Schwerwiegender Fehler C1104
Schwerwiegender Fehler beim Importieren der LibID: "Meldung"  
  
 Der Compiler hat beim Importieren einer Typbibliothek ein Problem erkannt.  Sie können beispielsweise keine Typbibliothek mit LibID und gleichzeitig `no_registry`angeben.  
  
 Weitere Informationen finden Sie unter [#import-Direktive](../../preprocessor/hash-import-directive-cpp.md).  
  
 Im folgenden Beispiel wird C1104 generiert.  
  
```  
// C1104.cpp  
#import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104  
```
