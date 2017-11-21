---
title: _umask | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _umask
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords: _umask
dev_langs: C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask function
- masks
- umask function
- file permissions [C++]
- files [C++], permission settings for
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8651fd1aa1400b366c6db369eff7bfde8751507
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="umask"></a>_umask
Legt die Standard-Dateiberechtigungsmaske fest. Es ist eine sicherere Version dieser Funktion verfügbar. Informationen dazu finden Sie unter [_umask_s](../../c-runtime-library/reference/umask-s.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _umask(  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pmode`  
 Standard-Berechtigungseinstellung.  
  
## <a name="return-value"></a>Rückgabewert  
 `_umask` gibt den vorherigen Wert von `pmode` zurück. Es gibt keine Fehlerrückgabe.  
  
## <a name="remarks"></a>Hinweise  
 Die `_umask` Funktion legt die dateiberechtigungsmaske des aktuellen Prozesses für den Modus gemäß `pmode`. Die Dateiberechtigungsmaske ändert die Berechtigungseinstellung neuer Dateien, die von `_creat`, `_open` oder `_sopen` erstellt werden. Wenn ein Bit in der Maske 1 ist, wird das entsprechende Bit im angeforderten Berechtigungswert der Datei auf 0 (nicht zulässig) festgelegt. Wenn ein Bit in der Maske 0 ist, bleibt das entsprechende Bit unverändert. Die Berechtigungseinstellung für eine neue Datei wird erst festgelegt, wenn die Datei zum ersten Mal geschlossen wird.  
  
 Der ganzzahlige Ausdruck `pmode` enthält eine oder beide der folgenden Manifestkonstanten, die in SYS\Stat.h definiert sind:  
  
 `_S_IWRITE`  
 Schreiben erlaubt.  
  
 `_S_IREAD`  
 Lesen erlaubt.  
  
 `_S_IREAD | _S_IWRITE`  
 Lesen und Schreiben erlaubt.  
  
 Wenn beide Konstanten gegeben sind, werden sie mit dem bitweisen OR-Operator verbunden ( `|` ). Wenn das `pmode`-Argument `_S_IREAD` ist, ist Lesen nicht zulässig (die Datei ist lesegeschützt). Wenn das `pmode`-Argument `_S_IWRITE` ist, ist Schreiben nicht zulässig (die Datei ist schreibgeschützt). Wenn z.B. das Schreib-Bit in der Maske festgelegt ist, sind alle neuen Dateien schreibgeschützt. Beachten Sie, dass in MS-DOS und Windows-Betriebssystemen alle Dateien lesbar sind und es nicht möglich ist, nur Schreibberechtigungen zu vergeben. Deshalb hat es keine Auswirkung auf den Dateimodus, wenn das Lese-Bit mit `_umask` belegt wird.  
  
 Wenn `pmode` keine Kombination aus einer der Manifestkonstanten ist oder eine alternative Gruppe von Konstanten enthält, ignoriert die Funktion diese einfach.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_umask`|\<io.h>, \<sys/stat.h>, \<sys/types.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="libraries"></a>Bibliotheken  
 Alle Versionen der [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_umask.c  
// compile with: /W3  
// This program uses _umask to set  
// the file-permission mask so that all future  
// files will be created as read-only files.  
// It also displays the old mask.  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask;  
  
   /* Create read-only files: */  
   oldmask = _umask( _S_IWRITE ); // C4996  
   // Note: _umask is deprecated; consider using _umask_s instead  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
```Output  
Oldmask = 0x0000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [File Handling (Dateibehandlung)](../../c-runtime-library/file-handling.md)   
 [Low-Level I/O (E/A auf niedriger Ebene)](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)