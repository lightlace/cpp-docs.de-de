---
title: "_putenv, _wputenv"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_putenv"
  - "_wputenv"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_tputenv"
  - "_wputenv"
  - "_putenv"
  - "wputenv"
  - "tputenv"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_putenv-Funktion"
  - "_tputenv-Funktion"
  - "_wputenv-Funktion"
  - "Umgebungsvariablen, Erstellen"
  - "Umgebungsvariablen, Löschen"
  - "Umgebungsvariablen, Ändern"
  - "putenv-Funktion"
  - "tputenv-Funktion"
  - "wputenv-Funktion"
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# _putenv, _wputenv
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt, ändert oder entfernt Umgebungsvariablen.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows\-Runtime ausgeführt werden.  Weitere Informationen finden Sie unter [CRT\-Funktionen nicht mit \/ZW unterstützt](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntax  
  
```  
int _putenv(  
   const char *envstring   
);  
int _wputenv(  
   const wchar_t *envstring   
);  
```  
  
#### Parameter  
 `envstring`  
 Definition der Umgebungszeichenfolge.  
  
## Rückgabewert  
 Gibt 0 bei Erfolg oder – 1 bei einem Fehler zurück.  
  
## Hinweise  
 Die `_putenv`\-Funktion fügt neue Umgebungsvariablen hinzu oder ändert die Werte vorhandener Umgebungsvariablen.  Umgebungsvariablen definieren die Umgebung, in der ein Prozess ausgeführt wird \(beispielsweise der Standardsuchpfad für die mit einem Programm zu verknüpfenden Bibliotheken\).  `_wputenv` ist eine Breitzeichenversion von `_putenv`. Das `envstring`\-Argument für `_wputenv` ist eine Breitzeichenfolge.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tputenv`|`_putenv`|`_putenv`|`_wputenv`|  
  
 Das `envstring`\-Argument muss ein Zeiger auf eine Zeichenfolge der Form `varname=string` sein, wobei `varname` der Name der hinzuzufügenden oder zu ändernden Umgebungsvariablen ist und `string` der Wert der Variablen.  Wenn `varname` bereits Teil der Umgebung ist, wird sein Wert durch `string`ersetzt. Andernfalls werden die neue `varname`\-Variable und ihr `string`\-Wert zur Umgebung hinzugefügt.  Sie können eine Variable aus der Umgebung entfernen, indem Sie einen leeren `string` angeben, d. h., indem Sie nur `varname=` angeben.  
  
 `_putenv` und `_wputenv` wirken sich nur auf die Umgebung aus, die für den aktuellen Prozess lokal ist. Sie können sie nicht zum Ändern der Umgebung auf Befehlsebene verwenden.  Das bedeutet, dass diese Funktionen nur bei Datenstrukturen funktionieren, auf die die Laufzeitbibliothek zugreifen kann, aber nicht bei dem Umgebungssegment, das vom Betriebssystem für einen Prozess erstellt wurde.  Wenn der aktuelle Prozess beendet wird, wird die Umgebung auf die Ebene des aufrufenden Prozesses zurückgesetzt \(in den meisten Fällen die Betriebssystemebene\).  Die geänderte Umgebung kann jedoch an alle neue Prozesse übergeben werden, die von `_spawn`, `_exec` oder `system` erstellt werden, und diese neuen Prozesse rufen alle neuen Elemente ab, die von `_putenv` und `_wputenv` hinzugefügt werden.  
  
 Ändern Sie keinen Umgebungseintrag direkt: Verwenden Sie stattdessen zum Ändern `_putenv` oder `_wputenv`.  Das direkte Loslösen von Elementen des globalen `_environ[]`\-Arrays kann nämlich dazu führen, dass ein ungültiger Speicher anvisiert wird.  
  
 `getenv` und `_putenv` verwenden die globale Variable `_environ`, um auf die Umgebungstabelle zuzugreifen; `_wgetenv` und `_wputenv` verwenden `_wenviron`.  `_putenv` und `_wputenv` ändern möglicherweise den Wert von `_environ` und `_wenviron`, wodurch das `_envp`\-Argument für `main` und das \_`wenvp`\-Argument für `wmain` ungültig werden.  Es ist daher sicherer mit `_environ` oder `_wenviron` auf die Umgebungsinformationen zuzugreifen.  Weitere Informationen über die Beziehung von `_putenv` und `_wputenv` mit globalen Variablen finden Sie unter [\_environ, \_wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Die Familien `_putenv` und `_getenv` der Funktionen sind nicht threadsicher.  `_getenv` gibt möglicherweise einen Zeichenfolgenzeiger zurück, während `_putenv` die Zeichenfolge ändert, was zu zufälligen Fehlern führen kann.  Stellen Sie sicher, dass Aufrufe dieser Funktionen synchronisiert sind.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_putenv`|\<stdlib.h\>|  
|`_wputenv`|\<stdlib.h\> oder \<wchar.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Beispiel  
 Ein Beispiel für die Verwendung von `_putenv` finden Sie unter [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [getenv, \_wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [\_searchenv, \_wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)