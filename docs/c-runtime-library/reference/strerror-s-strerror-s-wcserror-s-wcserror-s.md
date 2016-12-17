---
title: "strerror_s, _strerror_s, _wcserror_s, __wcserror_s"
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
  - "__wcserror_s"
  - "_strerror_s"
  - "_wcserror_s"
  - "strerror_s"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wcserror_s"
  - "__wcserror_s"
  - "_tcserror_s"
  - "_wcserror_s"
  - "tcserror_s"
  - "strerror_s"
  - "_strerror_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "__wcserror_s-Funktion"
  - "_strerror_s-Funktion"
  - "_tcserror_s-Funktion"
  - "_wcserror_s-Funktion"
  - "Fehlermeldungen, Abrufen"
  - "Fehlermeldungen, Drucken"
  - "Druckfehlermeldungen"
  - "strerror_s-Funktion"
  - "tcserror_s-Funktion"
  - "wcserror_s-Funktion"
ms.assetid: 9e5b15a0-efe1-4586-b7e3-e1d7c31a03d6
caps.latest.revision: 21
caps.handback.revision: "21"
ms.author: "corob"
manager: "ghogen"
---
# strerror_s, _strerror_s, _wcserror_s, __wcserror_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Abrufen der Systemfehlermeldung \(`strerror_s``_wcserror_s`\) oder Drucken einer vom Benutzer angegebenen Fehlermeldung \(`_strerror_s`, `__wcserror_s`\).  Diese Versionen von [strerror, \_strerror, \_wcserror, \_\_wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) enthalten Sicherheitserweiterungen wie unter [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t _strerror_s(  
   char *buffer,  
   size_t numberOfElements,  
   const char *strErrMsg   
);  
errno_t _wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   int errnum   
);  
errno_t __wcserror_s(  
   wchar_t *buffer,  
   size_t numberOfElements,  
   const wchar_t *strErrMsg   
);  
template <size_t size>  
errno_t strerror_s(  
   char (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t _strerror_s(  
   char (&buffer)[size],  
   const char *strErrMsg   
); // C++ only  
template <size_t size>  
errno_t _wcserror_s(  
   wchar_t (&buffer)[size],  
   int errnum   
); // C++ only  
template <size_t size>  
errno_t __wcserror_s(  
   wchar_t (&buffer)[size],  
   const wchar_t *strErrMsg   
); // C++ only  
```  
  
#### Parameter  
 `buffer`  
 Puffer für die Fehlerzeichenfolge.  
  
 `numberOfElements`  
 Puffergröße.  
  
 `errnum`  
 Fehlernummer.  
  
 `strErrMsg`  
 Vom Benutzer angegebene Meldung.  
  
## Rückgabewert  
 Null, wenn erfolgreich, Fehlercode bei Fehler.  
  
### Fehlerbedingungen  
  
|`buffer`|`numberOfElements`|`strErrMsg`|Inhalt von `buffer`|  
|--------------|------------------------|-----------------|-------------------------|  
|`NULL`|any|any|nicht verfügbar|  
|any|0|any|nicht geändert|  
  
## Hinweise  
 Die `strerror_s`\-Funktion ordnet `errnum` einer Fehlermeldungszeichenfolge zu und gibt die Zeichenfolge in `buffer` zurück.  `_strerror_s` verwendet nicht die Fehlernummer, sondern den aktuellen Wert von `errno`, um die entsprechende Meldung zu bestimmen.  Die Meldung wird allerdings weder von `strerror_s` noch `_strerror_s` gedruckt: Dazu muss eine Ausgabefunktion wie [fprintf](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md) aufgerufen werden:  
  
```  
if (( _access( "datafile",2 )) == -1 )  
{  
   _strerror_s(buffer, 80);  
   fprintf( stderr, buffer );  
}  
```  
  
 Wenn `strErrMsg``NULL` ist, gibt `_strerror_s` eine Zeichenfolge in `buffer` zurück, die die Systemfehlermeldung zu dem letzten Bibliotheksaufruf enthält, der einen Fehler erzeugt hat.  Die Fehlermeldungszeichenfolge wird durch das Zeilenumbruchzeichen \('\\n'\) beendet.  Wenn `strErrMsg` nicht gleich `NULL` ist, gibt `_strerror_s` eine Zeichenfolge in `buffer` zurück, die folgende Elemente \(in der angegebenen Reihenfolge\) enthält: die Zeichenfolgenmeldung, einen Doppelpunkt, ein Leerzeichen, die Systemfehlermeldung zu dem letzten Bibliotheksaufruf, einen Fehler erzeugt hat, und ein Zeilenumbruchzeichen.  Die Zeichenfolgenmeldung darf höchstens 94 Zeichen lang sein.  
  
 Diese Funktionen schneiden die Fehlermeldung ab, wenn die Länge `numberOfElements` – 1 überschreitet.  Die resultierende Zeichenfolge in `buffer` endet immer mit NULL.  
  
 Die tatsächliche Fehlernummer für `_strerror_s` wird in der Variablen [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) gespeichert.  Über die Variable [\_sys\_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird auf die Systemfehlermeldungen zugegriffen, die als Array von Meldungen nach Fehlernummern geordnet sind.  `_strerror_s` greift auf die entsprechende Fehlermeldung zu, indem der `errno`\-Wert als Index zur Variablen `_sys_errlist` verwendet wird.  Der Wert der Variablen [\_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) wird als maximale Anzahl an Elementen im `_sys_errlist`\-Array definiert.  Um vollständige Ergebnisse zu erzeugen, rufen Sie umgehend `_strerror_s` auf, nachdem eine Bibliotheksroutine einen Fehler zurückgibt.  Andernfalls können nachfolgende Aufrufe von `strerror_s` oder `_strerror_s` den `errno`\-Wert überschreiben.  
  
 `_wcserror_s` und `__wcserror_s` sind Breitzeichenversionen von `strerror_s` und `_strerror_s`, verwendet.  
  
 Diese Funktionen überprüfen ihre Parameter.  Wenn der Puffer `NULL` oder der Größenparameter 0 ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, gibt diese Funktion `EINVAL` zurück und setzt `errno` auf `EINVAL`.  
  
 `_strerror_s, _wcserror_s,` und `__wcserror_s`  sind nicht Teil der ANSI\-Definition, sondern zusätzliche Microsoft\-Erweiterungen.  Verwenden Sie sie nicht bei gewünschter Portabilität. Wenn Sie ANSI\-Kompatibilität benötigen, verwenden Sie stattdessen  `strerror_s` .  
  
 Die Verwendung dieser Funktionen in C\+\+ wird durch Überladungen \(als Vorlagen vorhanden\) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf.  Mit [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) deaktivieren Sie dieses Verhalten.  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tcserror_s`|`strerror_s`|`strerror_s`|`_wcserror_s`|  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`strerror_s`, `_strerror_s`|\<string.h\>|  
|`_wcserror_s`, `__wcserror_s`|\<string.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Betrachten Sie das Beispiel für [perror](../../c-runtime-library/reference/perror-wperror.md).  
  
## .NET Framework-Entsprechung  
 [System::Exception::Message](https://msdn.microsoft.com/en-us/library/system.exception.message.aspx)  
  
## Siehe auch  
 [Zeichenfolgenbearbeitung](../../c-runtime-library/string-manipulation-crt.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)