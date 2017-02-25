---
title: "_putch, _putwch | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_putwch"
  - "_putch"
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
  - "api-ms-win-crt-conio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_putch"
  - "putwch"
  - "_putwch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_putch-Funktion"
  - "_putwch-Funktion"
  - "Zeichen, Schreiben"
  - "Konsole, Schreiben von Zeichen in"
  - "putch-Funktion"
  - "putwch-Funktion"
ms.assetid: 3babc7cf-e333-405d-8449-c788d61d51aa
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _putch, _putwch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Schreibt ein Zeichen in die Konsole.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
  
      int _putch(  
int c   
);  
wint_t _putwch(  
   wchar_t c  
);  
```  
  
#### Parameter  
 `c`  
 Auszugebende Zeichen.  
  
## Rückgabewert  
 Gibt bei Erfolg `c` zurück.  Wenn `_putch` fehlschlägt, wird `EOF` zurückgegeben; wenn **\_putwch** fehlschlägt, wird **WEOF** zurückgegeben.  
  
## Hinweise  
 Diese Funktionen schreiben das Zeichen `c` direkt, ohne in die Konsole zu puffern.  In Windows NT schreibt **\_putwch** Unicodezeichen unter Verwendung der aktuellen Konsolengebietsschemaeinstellung.  
  
 Die Versionen mit dem Suffix **\_nolock** sind identisch, allerdings sind sie nicht vor Störungen durch andere Threads geschützt.  Weitere Informationen finden Sie unter `_putch_nolock` und `_putwch_nolock`.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|**\_puttch**|`_putch`|`_putch`|**\_putwch**|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_putch`|\<conio.h\>|  
|**\_putwch**|\<conio.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## Beispiel  
 Betrachten Sie das Beispiel für [\_getch](../../c-runtime-library/reference/getch-getwch.md).  
  
## Siehe auch  
 [Konsole und Port\-E\/A](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)