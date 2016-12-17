---
title: "__getmainargs, __wgetmainargs"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "__wgetmainargs"
  - "__getmainargs"
apilocation: 
  - "msvcr100.dll"
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__wgetmainargs"
  - "__getmainargs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__wgetmainargs"
  - "__getmainargs"
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# __getmainargs, __wgetmainargs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft Befehlszeilenanalyse auf und kopiert die Argumente für `main()` zurück durch die übergebenen Zeiger.  
  
## Syntax  
  
```cpp  
int __getmainargs(  
    int * _Argc,   
   char *** _Argv,   
   char *** _Env,   
   int _DoWildCard,  
_startupinfo * _StartInfo);  
  
 int __wgetmainargs (  
   int *_Argc,  
   wchar_t ***_Argv,  
   wchar_t ***_Env,  
   int _DoWildCard,  
   _startupinfo * _StartInfo)  
  
```  
  
#### Parameter  
 `_Argc`  
 Eine ganze Zahl, die die Anzahl der Argumente enthält, die in `argv` auf.  Der Parameter `argc` ist immer mindestens 1 sein.  
  
 `_Argv`  
 Ein Array auf NULL endende Zeichenfolge, die die Befehlszeilenargumente vom Benutzer eingegeben des Programms darstellen.  Üblicherweise ist `argv[0]` der Befehl, mit dem das Programm aufgerufen wird, argv \[1\] befindet erstes Befehlszeilenargument usw. bis argv \[argc\], das immer NULL ist.  Das erste Befehlszeilenargument ist immer `argv[1]` und der letzte Suchvorgang ist `argv[argc – 1]`.  
  
 `_Env`  
 Ein Array von Zeichenfolgen, das die Variablen darstellen, die in die Anwenderkonfiguration festgelegt werden.  Das Array wird durch einen NULL\- Eintrag beendet.  
  
 `_DoWildCard`  
 Eine ganze Zahl, wenn die Gruppe bis 1 die Platzhalter in den Befehlszeilenargumenten erweitert oder wenn dieser Wert auf 0 keine Aktion ausführt.  
  
 `_StartInfo`  
 Andere der CRT\-DLL übergeben werden, Informationen.  
  
## Rückgabewert  
 0 Wenn erfolgreich; ein negativer Wert, wenn fehlgeschlagen.  
  
## Hinweise  
 Verwenden Sie `__getmainargs` für nicht\-weiten Zeichenplattformen und `__wgetmainargs` auf Plattformen des Breitzeichens \(Unicode\).  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|\_\_getmainargs|internal.h|  
|\_\_wgetmainargs|internal.h|