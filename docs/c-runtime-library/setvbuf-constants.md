---
title: setvbuf-Konstanten | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _IOFBF
- _IONBF
- _IOLBF
dev_langs:
- C++
helpviewer_keywords:
- _IOFBF constant
- IOFBF constant
- IONBF constant
- _IOLBF constant
- IOLBF constant
- _IONBF constant
ms.assetid: a6ec4dd5-1f24-498c-871a-e874cd28d33c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6bdb0fd3ad3811e756458090a963f78bd716a581
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setvbuf-constants"></a>setvbuf-Konstanten
## <a name="syntax"></a>Syntax  
  
```  
  
#include <stdio.h>  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Konstanten stellen den Puffertyp für `setvbuf` dar.  
  
 Die möglichen Werte werden mit den folgenden Manifestkonstanten angegeben:  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|`_IOFBF`|Vollständige Pufferung: Der im Aufruf von `setvbuf` angegebene Puffer wird verwendet, und seine Größe ist wie im `setvbuf`-Aufruf angegeben. Wenn der Zeiger auf den Puffer **NULL** ist, wird der automatisch zugeordnete Puffer mit der angegebenen Größe verwendet.|  
|`_IOLBF`|Wie in `_IOFBF`.|  
|`_IONBF`|Unabhängig von Argumenten im Aufruf von `setvbuf` wird kein Puffer verwendet.|  
  
## <a name="see-also"></a>Siehe auch  
 [setbuf](../c-runtime-library/reference/setbuf.md)   
 [Globale Konstanten](../c-runtime-library/global-constants.md)