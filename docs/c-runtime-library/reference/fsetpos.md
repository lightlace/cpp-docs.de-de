---
title: fsetpos | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fsetpos
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
- fsetpos
dev_langs:
- C++
helpviewer_keywords:
- streams, setting position indicators
- fsetpos function
ms.assetid: 6d19ff48-1a2b-47b3-9f23-ed0a47b5a46e
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 1facc7aec41e7ab1c8b420f6792d76cce0d2b029
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="fsetpos"></a>fsetpos
Legt den Indikator für die Position im Stream fest  
  
## <a name="syntax"></a>Syntax  
  
```  
int fsetpos(   
   FILE *stream,  
   const fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `stream`  
 Zeiger zur `FILE` -Struktur.  
  
 `pos`  
 Speicher des Positionsindikators  
  
## <a name="return-value"></a>Rückgabewert  
 `fsetpos` gibt bei Erfolg 0 zurück. Bei einem Fehler gibt diese Funktion einen Wert ungleich null zurück und legt `errno` auf eine der folgenden Manifestkonstanten fest (definiert in ERRNO.H): `EBADF`, d.h., dass auf die Datei nicht zugegriffen werden kann oder das Objekt, auf das `stream` verweist, keine gültige Dateistruktur hat, oder `EINVAL`, was bedeutet, dass ein ungültiger Wert für `stream` oder `pos` übergeben wurde. Wenn ein ungültiger Parameter übergeben wird, rufen diese Funktionen den Handler für ungültige Parameter auf, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben wird.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `fsetpos` Funktion legt der dateipositionszeiger für `stream` auf den Wert der `pos`, erhalten Sie in einem vorherigen Aufruf für `fgetpos` für `stream`. Die Funktion löscht den Dateiende-Indikator und macht alle mit dem [Ungetc](../../c-runtime-library/reference/ungetc-ungetwc.md) auf `stream`. Nach dem Aufruf von `fsetpos` kann der nächste Vorgang auf `stream` entweder eine Eingabe oder eine Ausgabe sein.  
  
## <a name="requirements"></a>Anforderungen  
  
|Funktion|Erforderlicher Header|  
|--------------|---------------------|  
|`fsetpos`|\<stdio.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [fgetpos](../../c-runtime-library/reference/fgetpos.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Stream-E/A](../../c-runtime-library/stream-i-o.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)
