---
title: _mbccpy_s, _mbccpy_s_l | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _mbccpy_s
- _mbccpy_s_l
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
- _mbccpy_s_l
- mbccpy_s_l
- mbccpy_s
- _mbccpy_s
dev_langs:
- C++
helpviewer_keywords:
- tccpy_s_l function
- _tccpy_s function
- _mbccpy_s function
- mbccpy_s function
- tccpy_s function
- mbccpy_s_l function
- _tccpy_s_l function
- _mbccpy_s_l function
ms.assetid: b6e965fa-53c1-4ec3-85ef-a1c4b4f2b2da
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72b2e155dafe0b5fb5a83e5e62ea95fd2c3657e6
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="mbccpys-mbccpysl"></a>_mbccpy_s, _mbccpy_s_l
Kopiert ein Multibytezeichen von einer Zeichenfolge in eine andere Zeichenfolge. Diese Versionen von [_mbccpy, _mbccpy_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md) enthalten Sicherheitserweiterungen, wie unter [Sicherheitserweiterungen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [CRT-Funktionen, die in universellen Windows-Plattform-apps nicht unterstützt](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _mbccpy_s(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src   
);  
errno_t _mbccpy_s_l(  
   unsigned char *dest,  
   size_t buffSizeInBytes,  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
);  
template <size_t size>  
errno_t _mbccpy_s(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src   
); // C++ only  
template <size_t size>  
errno_t _mbccpy_s_l(  
   unsigned char (&dest)[size],  
   int * pCopied,  
   const unsigned char *src,  
   locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parameter  
 [out] `dest`  
 Kopierziel.  
  
 [in] `buffSizeInBytes`  
 Größe des Zielpuffers.  
  
 [out] `pCopied`  
 Wird mit der Anzahl kopierter Bytes gefüllt (bei Erfolg 1 oder 2). Übergeben Sie `NULL`, wenn die Zahl nicht relevant ist.  
  
 [in] `src`  
 Zu kopierendes Multibytezeichen.  
  
 [in] `locale`  
 Zu verwendendes Gebietsschema.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt. Wenn `src` oder `dest``NULL` ist oder wenn mehr als `buffSizeinBytes`-Bytes nach `dest` kopiert werden, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben die Funktionen `EINVAL` zurück und legen `errno` auf `EINVAL` fest.  
  
## <a name="remarks"></a>Hinweise  
 Die `_mbccpy_s`-Funktion kopiert ein Multibytezeichen von `src` in `dest`. Wenn `src` laut eines impliziten Aufrufs von [_ismbblead](../../c-runtime-library/reference/ismbblead-ismbblead-l.md) nicht auf das führende Byte eines Multibytezeichens zeigt, dann wird das einzelne Byte, auf das `src` zeigt, kopiert. Wenn `src` auf ein führendes Byte zeigt, aber das nächste Byte 0 und somit ungültig ist, wird 0 nach `dest` kopiert und `errno` auf `EILSEQ` festgelegt. Die Funktion gibt dann `EILSEQ` zurück.  
  
 `_mbccpy_s` fügt keinen NULL-Terminator an. Wenn jedoch `src` auf ein Nullzeichen zeigt, dann wird diese NULL nach `dest` kopiert (dies ist nur eine reguläre Einzelbytekopie).  
  
 Der Wert in `pCopied` wird mit der Anzahl kopierter Bytes gefüllt. Mögliche Werte sind 1 und 2, wenn der Vorgang erfolgreich ist. Wenn `NULL` übergeben wird, wird dieser Parameter ignoriert.  
  
|`src`|kopiert nach `dest`|`pCopied`|Rückgabewert|  
|-----------|----------------------|---------------|------------------|  
|kein führendes Byte|kein führendes Byte|1|0|  
|0|0|1|0|  
|führendes Byte gefolgt von Nicht-0|führendes Byte gefolgt von Nicht-0|2|0|  
|führendes Byte gefolgt von 0|0|1|`EILSEQ`|  
  
 Beachten Sie, dass die zweite Zeile nur ein Sonderfall der ersten ist. Die Tabelle setzt auch `buffSizeInBytes` >= `pCopied` voraus.  
  
 `_mbccpy_s` verwendet das aktuelle Gebietsschema für jedes gebietsschemaabhängige Verhalten. `_mbccpy_s_l` ist mit `_mbccpy_s` identisch, außer dass `_mbccpy_s_l` das Gebietsschema verwendet, das für jedes gebietsschemaabhängige Verhalten übergeben wurde.  
  
 Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads (Sichere Vorlagenüberladungen)](../../c-runtime-library/secure-template-overloads.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tccpy_s`|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus.|`_mbccpy_s`|Führt eine Zuordnung zum Makro oder zur Inlinefunktion aus.|  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_mbccpy_s`|\<mbstring.h>|  
|`_mbccpy_s_l`|\<mbstring.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Gebietsschema](../../c-runtime-library/locale.md)   
 [Interpretation von Multibyte-Zeichensequenzen](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)