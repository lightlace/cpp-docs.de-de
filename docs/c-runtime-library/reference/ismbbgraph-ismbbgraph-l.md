---
title: _ismbbgraph, _ismbbgraph_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ismbbgraph_l
- _ismbbgraph
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ismbbgraph
- _ismbbgraph_l
- ismbbgraph
- ismbbgraph_l
dev_langs: C++
helpviewer_keywords:
- _ismbbgraph_l function
- ismbbgraph_l function
- _ismbbgraph function
- ismbbgraph function
ms.assetid: b60db718-134f-4796-acc1-592d0b9efbb7
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3638740d4a62e42da71a7b076e636443e0530cdc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ismbbgraph-ismbbgraphl"></a>_ismbbgraph, _ismbbgraph_l
Bestimmt, ob ein bestimmtes Multibytezeichen ein Grafikzeichen ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
int _ismbbgraph (  
   unsigned int c   
);  
int _ismbbgraph_l (  
   unsigned int c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Die zu testende ganze Zahl.  
  
 `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert ungleich 0 (null) zurück, wenn diese Bedingung zutrifft. Der Ausdruck:  
  
```  
( _PUNCT | _UPPER | _LOWER | _DIGIT ) || _ismbbkprint  
```  
  
 ist für `c`ungleich 0, bzw. andernfalls 0. `_ismbbgraph` verwendet das aktuelle Gebietsschema für jedes gebietsschemaabhängige Verhalten. `_ismbbgraph_l` ist identisch, verwendet jedoch stattdessen das übergebene Gebietsschema. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_ismbbgraph`|\<mbctype.h>|  
|`_ismbbgraph_l`|\<mbctype.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Byteklassifizierung](../../c-runtime-library/byte-classification.md)   
 [_ismbb-Routinen](../../c-runtime-library/ismbb-routines.md)