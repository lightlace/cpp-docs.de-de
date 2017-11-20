---
title: STACKSIZE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: STACKSIZE
dev_langs: C++
helpviewer_keywords: STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 82b33d217e593a35b66bb3530840a739e93082ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="stacksize"></a>STACKSIZE
Legt die Stapelgröße in Bytes fest.  
  
```  
STACKSIZE reserve[,commit]  
```  
  
## <a name="remarks"></a>Hinweise  
 Alternativ können Sie den Stapel festgelegt ist, mit der [Stapelreservierungen](../../build/reference/stack-stack-allocations.md) (/ STACK) Option. Finden Sie in der Dokumentation auf diese Option für Details zu den *reservieren* und `commit` Argumente.  
  
 Diese Option wirkt sich nicht für DLLs aus.  
  
## <a name="see-also"></a>Siehe auch  
 [Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)