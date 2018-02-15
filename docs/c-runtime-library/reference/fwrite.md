---
title: fwrite | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fwrite
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fwrite
dev_langs:
- C++
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 73b5328ce6851ceb61ad3260760e95cd329ee064
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="fwrite"></a>fwrite
Schreibt Daten in einen Stream.  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t fwrite(  
   const void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `buffer`  
 Zeiger auf die zu schreibenden Daten.  
  
 `size`  
 Elementgröße in Bytes.  
  
 `count`  
 Maximale Anzahl zu schreibender Elemente.  
  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 `fwrite` gibt die Anzahl der tatsächlich geschriebenen vollständigen Elemente zurück. Diese kann kleiner sein als `count`, wenn ein Fehler auftritt. Außerdem kann im Fall eines Fehlers möglicherweise der Dateipositionszeiger nicht bestimmt werden. Wenn entweder `stream` oder `buffer` ein NULL-Zeiger ist, oder wenn im Unicode-Modus eine ungerade Anzahl zu schreibender Bytes festgelegt wird, ruft diese Funktion den ungültigen Parameterhandler auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird. Wenn die weitere Ausführung zugelassen wird, setzt diese Funktion `errno` auf `EINVAL` und gibt "0" zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `fwrite`-Funktion schreibt bis zu `count` Elemente, alle mit einer Länge von `size`, aus dem Puffer `buffer` in den Ausgabe-`stream`. Der mit `stream` assoziierte Dateizeiger (falls vorhanden) wird um die Anzahl tatsächlich geschriebener Bytes erhöht. Wenn `stream` öffnen im Textmodus wird jeder Zeilenvorschub durch einen Wagenrücklauf - Zeilenvorschub ersetzt. Diese Ersetzung hat keine Auswirkung auf den Rückgabewert.  
  
 Wenn `stream` in einem Unicode-Übersetzungsmodus geöffnet wird – z. B., wenn `stream` durch Aufrufen von `fopen` geöffnet wird und ein Modusparameter verwendet wird, der `ccs=UNICODE`, `ccs=UTF-16LE` oder `ccs=UTF-8` enthält, oder wenn der Modus durch Verwendung von `_setmode` und einem Modusparameter, der `_O_WTEXT`, `_O_U16TEXT` oder `_O_U8TEXT` enthält, in einen Unicode-Übersetzungsmodus geändert wird –, dann wird `buffer` als Zeiger auf ein Array von `wchar_t` interpretiert, das UTF-16 -Daten enthält. Der Versuch, in diesem Modus eine ungerade Anzahl von Bytes zu schreiben, führt zu einem Parametervalidierungsfehler.  
  
 Da diese Funktion den aufrufenden Thread sperrt, ist sie threadsicher. Eine nicht sperrende Version finden Sie unter `_fwrite_nolock`.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`fwrite`|\<stdio.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel hierfür finden Sie unter [fread](../../c-runtime-library/reference/fread.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [_fwrite_nolock](../../c-runtime-library/reference/fwrite-nolock.md)   
 [_write](../../c-runtime-library/reference/write.md)