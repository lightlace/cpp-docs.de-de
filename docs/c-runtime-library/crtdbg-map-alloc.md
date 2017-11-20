---
title: _CRTDBG_MAP_ALLOC | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CRTDBG_MAP_ALLOC
- _CRTDBG_MAP_ALLOC
dev_langs: C++
helpviewer_keywords:
- _CRTDBG_MAP_ALLOC macro
- memory allocation, in debug builds
- CRTDBG_MAP_ALLOC macro
ms.assetid: 435242b8-caea-4063-b765-4a608200312b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a2b61b315baa337675147ded1232a943e82b24ec
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="crtdbgmapalloc"></a>_CRTDBG_MAP_ALLOC
Wenn das **_CRTDBG_MAP_ALLOC**-Flag in der Debugversion einer Anwendung definiert ist, wird die Basisversion der Heapfunktionen den entsprechenden Debugversionen direkt zugeordnet. Das Flag wird in Crtdbg.h verwendet, um die Zuordnung vorzunehmen. Dieses Flag ist nur verfügbar, wenn das Flag [_DEBUG](../c-runtime-library/debug.md) in der Anwendung definiert wurde.  
  
 Weitere Informationen zum Verwenden der Debugversion im Vergleich zur Basisversion der Heapfunktion finden Sie unter [Using the Debug Version Versus the Base Version (Verwenden der Debugversion im Vergleich zur Basisversion)](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerungsflags](../c-runtime-library/control-flags.md)