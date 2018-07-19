---
title: setvbuf-Konstanten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d4292ae29602b5890a167a3e2c29e460d65373f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32407963"
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