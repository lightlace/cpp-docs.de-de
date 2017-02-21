---
title: "_umask | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_umask"
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
  - "_umask"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_umask-Funktion"
  - "Dateiberechtigungen [C++]"
  - "Dateien [C++], Berechtigungseinstellungen für"
  - "Masken"
  - "Masken, Dateiberechtigungseinstellung"
  - "umask-Funktion"
ms.assetid: 5e9a13ba-5321-4536-8721-6afb6f4c8483
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _umask
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die Standarddateiberechtigungsmaske fest.  Eine sicherere Version dieser Funktion ist verfügbar; finden Sie unter [\_umask\_s](../../c-runtime-library/reference/umask-s.md).  
  
## Syntax  
  
```  
int _umask(  
   int pmode   
);  
```  
  
#### Parameter  
 `pmode`  
 Standardberechtigungseinstellung.  
  
## Rückgabewert  
 `_umask` gibt dem vorhergehenden Wert von `pmode` zurück.  Es gibt keine Fehlerrückgabe.  
  
## Hinweise  
 Die `_umask`\-Funktion wird die Dateiberechtigungsmaske des aktuellen Prozesses auf den Modus ab, der von `pmode` angegeben wird *.* Die Dateiberechtigungsmaske ändert die Berechtigungseinstellung von neuen Dateien, die von `_creat`, `_open` oder `_sopen` erstellt werden.  Wenn ein Bit in der Maske 1 ist, wird das entsprechende Bit im angeforderten Berechtigungswert der Datei auf 0 festgelegt \(nicht zulässig\).  Wenn ein Bit in der Maske 0 ist, wird das entsprechende Bit unverändert gelassen.  Die Berechtigungseinstellung für eine neue Datei wird nicht festgelegt, bis die Datei zum ersten Mal geschlossen ist.  
  
 Der ganzzahlige Ausdruck `pmode` enthält eine oder beide der folgenden Manifestkonstanten, die in SYS\\STAT.H:  
  
 `_S_IWRITE`  
 Schreiben zulässig.  
  
 `_S_IREAD`  
 Lesen zulässig.  
  
 `_S_IREAD | _S_IWRITE`  
 Lesen und Schreiben zulässig.  
  
 Wenn beide Konstanten angegeben werden, sind sie mit dem bitweisen Operator OR verknüpft \(          `|`  \).  Wenn `pmode` das Argument `_S_IREAD`, wird das Lesen nicht zulässig \(die Datei ist lesegeschützt\).  Wenn `pmode` das Argument `_S_IWRITE`, wird das Schreiben nicht zulässig \(die Datei ist schreibgeschützt\).  Wenn das schreibensbit in der Maske gesetzt wird, werden alle neuen Dateien schreibgeschützt.  Beachten Sie das mit MS\-DOS\- und die Windows\-Betriebssysteme, alle Dateien sind lesbar; es ist nicht möglich, lesegeschützte Berechtigung zu geben.  Deshalb hat das Festlegen des Lesebits mit `_umask` keine Auswirkungen auf die Modi der Datei.  
  
 Wenn `pmode` keine Kombination einer Manifestkonstanten ist oder einen alternative Konstanten enthält, ignoriert die Funktion einfach die.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_umask`|\<io.h, sys\>\<\/stat.h, sys\/\>types.h \<\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
  
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