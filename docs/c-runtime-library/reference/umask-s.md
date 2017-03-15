---
title: "_umask_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_umask_s"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "unmask_s"
  - "_umask_s"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_umask_s-Funktion"
  - "Dateiberechtigungen [C++]"
  - "Dateien [C++], Berechtigungseinstellungen für"
  - "Masken"
  - "Masken, Dateiberechtigungseinstellung"
  - "umask_s-Funktion"
ms.assetid: 70898f61-bf2b-4d8d-8291-0ccaa6d33145
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _umask_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die Standarddateiberechtigungsmaske fest.  Eine Version von [\_umask](../../c-runtime-library/reference/umask.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _umask_s(  
   int mode,  
   int * pOldMode  
);  
```  
  
#### Parameter  
 \[in\] `mode`  
 Standardberechtigungseinstellung.  
  
 \[out\] `oldMode`  
 Der vorherige Wert der Berechtigungseinstellung.  
  
## Rückgabewert  
 Gibt einen Fehlercode zurück, wenn `Mode` keinen gültigen Modus angibt, oder der `pOldMode` Zeiger `NULL` ist.  
  
### Fehlerbedingungen  
  
|`mode`|`pOldMode`|**Rückgabewert**|**Contents of**  `oldMode`|  
|------------|----------------|----------------------|--------------------------------|  
|any|`NULL`|`EINVAL`|nicht geändert|  
|ungültiger Modus|any|`EINVAL`|nicht geändert|  
  
 Wenn eine der oben genannten Bedingungen auftritt, wird der ungültige Parameterhandler aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt `_umask_s``EINVAL` zurück und setzt `errno` auf `EINVAL`.  
  
## Hinweise  
 Die `_umask_s` \- Funktion wird die Dateiberechtigungsmaske des aktuellen Prozesses auf den Modus ab, der von `mode` angegeben wird *.* Die Dateiberechtigungsmaske ändert die Berechtigungseinstellung von neuen Dateien, die von `_creat`, `_open` oder `_sopen` erstellt werden.  Wenn ein Bit in der Maske 1 ist, wird das entsprechende Bit im angeforderten Berechtigungswert der Datei auf 0 festgelegt \(nicht zulässig\).  Wenn ein Bit in der Maske 0 ist, wird das entsprechende Bit unverändert gelassen.  Die Berechtigungseinstellung für eine neue Datei wird nicht festgelegt, bis die Datei zum ersten Mal geschlossen ist.  
  
 Der ganzzahlige Ausdruck `pmode` enthält eine oder beide der folgenden Manifestkonstanten, die in SYS\\STAT.H:  
  
 `_S_IWRITE`  
 Schreiben zulässig.  
  
 `_S_IREAD`  
 Lesen zulässig.  
  
 `_S_IREAD | _S_IWRITE`  
 Lesen und Schreiben zulässig.  
  
 Wenn beide Konstanten angegeben werden, sind sie mit dem bitweisen Operator OR verknüpft \(          `|`  \).  Wenn `mode` das Argument `_S_IREAD`, wird das Lesen nicht zulässig \(die Datei ist lesegeschützt\).  Wenn `mode` das Argument `_S_IWRITE`, wird das Schreiben nicht zulässig \(die Datei ist schreibgeschützt\).  Wenn das schreibensbit in der Maske gesetzt wird, werden alle neuen Dateien schreibgeschützt.  Beachten Sie das mit MS\-DOS\- und die Windows\-Betriebssysteme, alle Dateien sind lesbar; es ist nicht möglich, lesegeschützte Berechtigung zu geben.  Deshalb hat das Festlegen des Lesebits mit `_umask_s`  keine Auswirkungen auf die Modi der Datei.  
  
 Wenn `pmode` keine Kombination einer Manifestkonstanten ist oder einen alternative Konstanten enthält, ignoriert die Funktion einfach die.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_umask_s`|\<io.h und\> sys \<\/stat.h und sys\> \/types.h \<\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
  
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
  
  **Oldmask \= 0x0000**   
## .NET Framework-Entsprechung  
 [System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [E\/A auf niedriger Ebene](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_umask](../../c-runtime-library/reference/umask.md)