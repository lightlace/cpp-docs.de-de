---
title: _chsize_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _chsize_s
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
- chsize_s
- _chsize_s
dev_langs:
- C++
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
caps.latest.revision: 16
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: eb8292d70a77a5901c710349d6912e46cfda8f63
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="chsizes"></a>_chsize_s
Ändert die Größe einer Datei. Dies ist eine sicherere Version von [_chsize](../../c-runtime-library/reference/chsize.md), wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _chsize_s(   
   int fd,  
   __int64 size   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `fd`  
 Dateideskriptor, der auf eine geöffnete Datei verweist.  
  
 `size`  
 Neue Länge der Datei in Bytes.  
  
## <a name="return-value"></a>Rückgabewert  
 `_chsize_s` gibt den Wert 0 zurück, wenn die Dateigröße erfolgreich geändert wurde. Ein Rückgabewert ungleich null zeigt einen Fehler an: Der Rückgabewert ist `EACCES`, wenn die angegebene Datei für den Zugriff gesperrt ist, `EBADF`, wenn die angegebene Datei schreibgeschützt oder der Deskriptor ungültig ist, `ENOSPC`, wenn kein Speicherplatz mehr auf dem Gerät vorhanden ist, oder `EINVAL`, wenn die Größe kleiner als 0 (null) ist. `errno` wird auf denselben Wert festgelegt.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [_doserrno, errno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Hinweise  
 Die `_chsize_s`-Funktion erweitert oder verkürzt die mit `fd` verknüpfte Datei auf die von `size` angegebene Länge. Die Datei muss in einem Modus geöffnet sein, der Schreiben zulässt. Wenn die Datei erweitert wird, werden NULL-Zeichen ('\0') angefügt. Wenn die Datei abgeschnitten wird, gehen alle Daten vom Ende der gekürzten Datei bis zur ursprünglichen Länge der Datei verloren.  
  
 `_chsize_s` verwendet einen 64-Bit-Integer als Dateigröße und kann daher Dateien handhaben, die größer als 4 GB sind. `_chsize` ist auf 32-Bit-Dateien beschränkt.  
  
 Diese Funktion überprüft ihre Parameter. Wenn `fd` kein gültiger Dateideskriptor ist oder die Größe kleiner als null ist, wird – wie unter [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben – der Handler für ungültige Parameter aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|Optionaler Header|  
|-------------|---------------------|---------------------|  
|`_chsize_s`|\<io.h>|\<errno.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="see-also"></a>Siehe auch  
 [File Handling (Dateibehandlung)](../../c-runtime-library/file-handling.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
