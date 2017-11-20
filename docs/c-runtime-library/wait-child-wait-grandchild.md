---
title: _WAIT_CHILD, _WAIT_GRANDCHILD | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _WAIT_GRANDCHILD
- WAIT_CHILD
- WAIT_GRANDCHILD
- _WAIT_CHILD
dev_langs: C++
helpviewer_keywords:
- WAIT_CHILD constant
- WAIT_GRANDCHILD constant
- _WAIT_CHILD constant
- _WAIT_GRANDCHILD constant
ms.assetid: 7acd96fa-d118-4339-bb00-e5afaf286945
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1e5e3aa48f0184730a7860ea055d9b233b4ac708
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="waitchild-waitgrandchild"></a>_WAIT_CHILD, _WAIT_GRANDCHILD
## <a name="syntax"></a>Syntax  
  
```  
  
#include <process.h>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion `_cwait` kann von jedem Prozess verwendet werden, der auf einen anderen Prozess wartet (wenn die Prozess-ID bekannt ist). Das Aktionsargument kann einen der folgenden Werte aufweisen:  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|`_WAIT_CHILD`|Der aufrufende Prozess wartet, bis der angegebene neue Prozess beendet ist.|  
|`_WAIT_GRANDCHILD`|Der aufrufende Prozess wartet, bis der angegebene neue Prozess und alle Prozesse, die durch den neuen Prozess erstellt werden, beendet sind.|  
  
## <a name="see-also"></a>Siehe auch  
 [_cwait](../c-runtime-library/reference/cwait.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)