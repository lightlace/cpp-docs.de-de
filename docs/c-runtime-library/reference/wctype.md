---
title: wctype | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wctype
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
apitype: DLLExport
f1_keywords: wctype
dev_langs: C++
helpviewer_keywords:
- wctype function
- wide characters
ms.assetid: 14aded12-4087-4123-bc48-db4e10999223
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: daae662a39d012418b5cd178e26d731dbca1e715
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="wctype"></a>wctype
Bestimmt eine Klassifizierungsregel für Breitzeichencodes.  
  
## <a name="syntax"></a>Syntax  
  
```  
wctype_t wctype(  
   const char * property   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `property`  
 Eigenschaftszeichenfolge  
  
## <a name="return-value"></a>Rückgabewert  
 Wenn die Kategorie `LC_CTYPE` des aktuellen Gebietsschemas keine Klassifizierungsregel definiert, deren Name der Eigenschaftszeichenfolge `property` entspricht, gibt die Funktion 0 zurück. Andernfalls wird ein Wert ungleich 0 zurückgegeben, der für die Verwendung als das zweite Argument für einen nachfolgenden Aufruf von [towctrans](../../c-runtime-library/reference/towctrans.md) geeignet ist.  
  
## <a name="remarks"></a>Hinweise  
 Die Funktion bestimmt eine Klassifizierungsregel für Breitzeichencodes. Die folgenden Paare von Aufrufen weisen in allen Gebietsschemas das gleiche Verhalten auf (durch eine Implementierung können jedoch sogar im Gebietsschema „C“ zusätzliche Klassifizierungsregeln definiert werden):  
  
|Funktion|Identisch mit|  
|--------------|-------------|  
|`iswalnum(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alnum" ) )`|  
|`iswalpha(`  `c`  `)`|`iswctype(`  `c` `, wctype( "alpha" ) )`|  
|`iswcntrl(`  `c`  `)`|`iswctype(`  `c` `, wctype( "cntrl" ) )`|  
|`iswdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "digit" ) )`|  
|`iswgraph(`  `c`  `)`|`iswctype(`  `c` `, wctype( "graph" ) )`|  
|`iswlower(`  `c`  `)`|`iswctype(`  `c` `, wctype( "lower" ) )`|  
|`iswprint(`  `c`  `)`|`iswctype(`  `c` `, wctype( "print" ) )`|  
|`iswpunct(`  `c`  `)`|`iswctype(`  `c` `, wctype( "punct" ) )`|  
|`iswspace(`  `c`  `)`|`iswctype(`  `c` `, wctype( "space" ) )`|  
|`iswupper(`  `c`  `)`|`iswctype(`  `c` `, wctype( "upper" ) )`|  
|`iswxdigit(`  `c`  `)`|`iswctype(`  `c` `, wctype( "xdigit" ) )`|  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`wctype`|\<wctype.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenkonvertierung](../../c-runtime-library/data-conversion.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)