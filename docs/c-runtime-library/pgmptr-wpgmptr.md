---
title: "_pgmptr, _wpgmptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pgmptr"
  - "_pgmptr"
  - "wpgmptr"
  - "_wpgmptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pgmptr-Funktion"
  - "_wpgmptr-Funktion"
  - "pgmptr-Funktion"
  - "wpgmptr-Funktion"
ms.assetid: 4d44b515-0eff-4136-8bc4-684195f218f5
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# _pgmptr, _wpgmptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Pfad der ausführbaren Datei.  Veraltet; Verwenden Sie [\_get\_pgmptr](../c-runtime-library/reference/get-pgmptr.md) und [\_get\_wpgmptr](../c-runtime-library/reference/get-wpgmptr.md).  
  
## Syntax  
  
```  
extern char *_pgmptr;  
extern wchar_t *_wpgmptr;  
```  
  
## Hinweise  
 Wenn ein Programm im Befehlsinterpreter \(Cmd.exe\) ausgeführt wird, wird `_pgmptr` automatisch zum vollständigen Pfad der ausführbaren Datei initialisiert.  Wenn Hello.exe in C:\\BIN ist und C:\\BIN im Pfad ist, wird `_pgmptr` auf C:\\BIN\\Hello.exe festgelegt, wenn Sie ausführen:  
  
```  
C> hello   
```  
  
 Wenn ein Programm nicht über die Befehlszeile ausgeführt wird, würde `_pgmptr` dem Programmnamen \(Basisname der Datei ohne die Dateinamenerweiterung\) oder einen Dateinamen, zu einem relativen Pfad oder einen vollständigen Pfad initialisiert werden.  
  
 `_wpgmptr` ist die Breitzeichenentsprechung von `_pgmptr` für Programme, die `wmain` verwenden.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|  
  
## Anforderungen  
  
|Variable|Erforderlicher Header|  
|--------------|---------------------------|  
|`_pgmptr`, `_wpgmptr`|\<stdlib.h\>|  
  
## Beispiel  
 Das folgende Programm veranschaulicht die Verwendung von `_pgmptr`.  
  
```  
// crt_pgmptr.c  
// compile with: /W3  
// The following program demonstrates the use of _pgmptr.  
//  
#include <stdio.h>  
#include <stdlib.h>  
int main( void )  
{  
   printf("The full path of the executing program is : %Fs\n",   
     _pgmptr); // C4996  
   // Note: _pgmptr is deprecated; use _get_pgmptr instead  
}  
```  
  
 Sie können `_wpgmptr` verwenden, indem Sie `%Fs` in `%S` und `main` zu `wmain` geändert.  
  
## Siehe auch  
 [Globale Variablen](../c-runtime-library/global-variables.md)