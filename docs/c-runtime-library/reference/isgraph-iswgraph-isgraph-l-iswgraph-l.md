---
title: isgraph, iswgraph, _isgraph_l, _iswgraph_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- isgraph
- iswgraph
- _iswgraph_l
- _isgraph_l
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _isgraph_l
- _iswgraph_l
- _ismbcgraph_l
- Isgraph
- _istgraph_l
- _istgraph
- iswgraph
dev_langs: C++
helpviewer_keywords:
- isgraph function
- _istgraph_l function
- istgraph function
- _isgraph_l function
- iswgraph function
- _iswgraph_l function
- _istgraph function
- _ismbcgraph_l function
ms.assetid: 531a5f34-4302-4d0a-8a4f-b7ea150ad941
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fc1dd32d2b427f6d22fad330cc25804ac528ea83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="isgraph-iswgraph-isgraphl-iswgraphl"></a>isgraph, iswgraph, _isgraph_l, _iswgraph_l
Bestimmt, ob eine ganze Zahl ein Grafikzeichen darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
int isgraph(  
   int c   
);  
int iswgraph(  
   wint_t c   
);  
int _isgraph_l(  
   int c,  
   _locale_t locale  
);  
int _iswgraph_l(  
   wint_t c,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `c`  
 Zu testende ganze Zahl.  
  
## <a name="return-value"></a>Rückgabewert  
 Jede dieser Routinen gibt einen Wert ungleich 0 (null) zurück, wenn `c` eine bestimmte Darstellung eines druckbaren Zeichens ist, das keine Leerzeichen ist. `isgraph` gibt einen Wert ungleich 0 (null) zurück, wenn `c` ein anderes druckbares Zeichen als ein Leerzeichen ist. `iswgraph` gibt einen Wert ungleich 0 (null) zurück, wenn `c` ein anderes druckbares Breitzeichen als ein Leerzeichen ist. Jede dieser Routinen gibt 0 zurück, wenn `c` die Testbedingung nicht erfüllt.  
  
 Die Versionen dieser Funktionen mit dem `_l`-Suffix verwenden das übergebene Gebietsschema anstelle des aktuellen Gebietsschemas für ihr vom Gebietsschema abhängiges Verhalten. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Das Verhalten von `isgraph` und `_isgraph_l` ist nicht definiert, wenn `c` nicht EOF ist oder nicht im Bereich von 0 bis 0xFF liegt. Wenn eine CRT-Debugbibliothek verwendet wird und `c` keinem dieser Werte entspricht, lösen die Funktionen eine Assertion aus.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_istgraph`|`isgraph`|[_ismbcgraph](../../c-runtime-library/reference/ismbcgraph-functions.md)|`iswgraph`|  
|`_istgraph_l`|`_isgraph_l`|[_ismbcgraph_l](../../c-runtime-library/reference/ismbcgraph-functions.md)|`_iswgraph_l`|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`isgraph`|\<ctype.h>|  
|`iswgraph`|\<ctype.h> oder \<wchar.h>|  
|`_isgraph_l`|\<ctype.h>|  
|`_iswgraph_l`|\<ctype.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenklassifizierung](../../c-runtime-library/character-classification.md)   
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [is, isw Routines (is- und isw-Routinen)](../../c-runtime-library/is-isw-routines.md)