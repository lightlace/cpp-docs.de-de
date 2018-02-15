---
title: _umask_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _umask_s
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
f1_keywords:
- unmask_s
- _umask_s
dev_langs:
- C++
helpviewer_keywords:
- masks, file-permission-setting
- _umask_s function
- masks
- file permissions [C++]
- umask_s function
- files [C++], permission settings for
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 315473748d64e572c73746ce6f6fc97ccc912bb0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="umasks"></a>_umask_s
Legt die Standard-Dateiberechtigungsmaske fest. Dies ist eine Version von [_umask](../../c-runtime-library/reference/umask.md) mit Sicherheitserweiterungen wie in den [Sicherheitsfunktionen in CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _umask_s(  
   int mode,  
   int * pOldMode  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `mode`  
 Standard-Berechtigungseinstellung.  
  
 [out] `oldMode`  
 Der vorherige Wert der Berechtigungseinstellung.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt einen Fehlercode zurück, wenn `Mode` keinen gültigen Modus angibt oder der `pOldMode`-Zeiger `NULL` ist.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`mode`|`pOldMode`|**Rückgabewert**|**Inhalt** `oldMode`|  
|------------|----------------|----------------------|--------------------------------|  
|any|`NULL`|`EINVAL`|nicht geändert|  
|ungültiger Modus|any|`EINVAL`|nicht geändert|  
  
 Wenn eine der obengenannten Bedingungen auftritt, wird der Handler für ungültige Parameter aufgerufen wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, gibt `_umask_s` `EINVAL` zurück und setzt `errno` auf `EINVAL`.  
  
## <a name="remarks"></a>Hinweise  
 Die `_umask_s` Funktion legt die dateiberechtigungsmaske des aktuellen Prozesses für den Modus gemäß `mode`. Die Dateiberechtigungsmaske ändert die Berechtigungseinstellung neuer Dateien, die von `_creat`, `_open` oder `_sopen` erstellt werden. Wenn ein Bit in der Maske 1 ist, wird das entsprechende Bit im angeforderten Berechtigungswert der Datei auf 0 (nicht zulässig) festgelegt. Wenn ein Bit in der Maske 0 ist, bleibt das entsprechende Bit unverändert. Die Berechtigungseinstellung für eine neue Datei wird erst festgelegt, wenn die Datei zum ersten Mal geschlossen wird.  
  
 Der ganzzahlige Ausdruck `pmode` enthält eine oder beide der folgenden Manifestkonstanten, die in SYS\Stat.h definiert sind:  
  
 `_S_IWRITE`  
 Schreiben zugelassen.  
  
 `_S_IREAD`  
 Lesen erlaubt.  
  
 `_S_IREAD | _S_IWRITE`  
 Lesen und Schreiben erlaubt.  
  
 Wenn beide Konstanten gegeben sind, werden sie mit dem bitweisen OR-Operator verbunden ( `|` ). Wenn das `mode`-Argument `_S_IREAD` ist, ist Lesen nicht zulässig (die Datei ist lesegeschützt). Wenn das `mode`-Argument `_S_IWRITE` ist, ist Schreiben nicht zulässig (die Datei ist schreibgeschützt). Wenn z.B. das Schreib-Bit in der Maske festgelegt ist, sind alle neuen Dateien schreibgeschützt. Beachten Sie, dass in MS-DOS und Windows-Betriebssystemen alle Dateien lesbar sind und es nicht möglich ist, nur Schreibberechtigungen zu vergeben. Deshalb hat es keine Auswirkung auf den Dateimodus, wenn das Lese-Bit mit `_umask_s` belegt wird.  
  
 Wenn `pmode` keine Kombination aus einer der Manifestkonstanten ist oder eine alternative Gruppe von Konstanten enthält, ignoriert die Funktion diese einfach.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_umask_s`|\<io.h> und \<sys/stat.h> und \<sys/types.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
  
```  
// crt_umask_s.c  
/* This program uses _umask_s to set  
 * the file-permission mask so that all future  
 * files will be created as read-only files.  
 * It also displays the old mask.  
 */  
  
#include <sys/stat.h>  
#include <sys/types.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int oldmask, err;  
  
   /* Create read-only files: */  
   err = _umask_s( _S_IWRITE, &oldmask );  
   if (err)  
   {  
      printf("Error setting the umask.\n");  
      exit(1);  
   }  
   printf( "Oldmask = 0x%.4x\n", oldmask );  
}  
```  
  
```Output  
Oldmask = 0x0000  
```  
  
## <a name="see-also"></a>Siehe auch  
 [File Handling (Dateibehandlung)](../../c-runtime-library/file-handling.md)   
 [E/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)