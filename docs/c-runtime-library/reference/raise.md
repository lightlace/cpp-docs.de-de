---
title: "raise"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "raise"
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
  - "Raise"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Programme [C++], Senden von Signalen zu ausführenden Programme"
  - "raise-Funktion"
  - "Signale"
  - "Signale, Senden zu ausführenden Programme"
ms.assetid: a3ccd3ad-f68f-4a7b-a005-c3ebfb217e8b
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "corob"
manager: "ghogen"
---
# raise
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sendet ein Signal an das ausführende Programm.  
  
> [!NOTE]
>  Verwenden Sie diese Methode nicht, um eine [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App zu schließen, außer bei Tests oder in Debugszenarios.  Programmgesteuerte oder UI\-Methoden zum Schließen einer [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]\-App sind gemäß Abschnitt 3.6 der [Zertifizierungsanforderungen für Windows 8\-Apps](http://go.microsoft.com/fwlink/?LinkId=262889) nicht zulässig.  Weitere Informationen finden Sie unter [Anwendungslebenszyklus \(Windows Store\-Apps\)](http://go.microsoft.com/fwlink/?LinkId=262853).  
  
## Syntax  
  
```  
  
      int raise(  
int sig   
);  
```  
  
#### Parameter  
 *sig*  
 Auszulösendes Signal.  
  
## Rückgabewert  
 Bei Erfolg gibt **raise** 0 zurück .  Andernfalls gibt es einen Wert ungleich 0 \(null\) zurück.  
  
## Hinweise  
 Die **raise**\-Funktion sendet *sig* an das ausführende Programm.  Wenn ein vorheriger Aufruf von **signal** eine Signalverarbeitungsfunktion für *sig* installiert hat, führt **raise** diese Funktion aus.  Wenn keine Handlerfunktion installiert wurde, wird die dem Signalwert *sig* zugeordnete Standardaktion wie folgt ausgeführt.  
  
|Signal|Bedeutung|Default|  
|------------|---------------|-------------|  
|`SIGABRT`|Nicht ordnungsgemäße Beendigung|Beendet das aufrufende Programm mit Exitcode 3|  
|`SIGFPE`|Gleitkommafehler|Beendet das aufrufende Programm|  
|`SIGILL`|Ungültige Anweisung|Beendet das aufrufende Programm|  
|`SIGINT`|STRG\+C\-Unterbrechung|Beendet das aufrufende Programm|  
|`SIGSEGV`|Ungültiger Speicherzugriff|Beendet das aufrufende Programm|  
|`SIGTERM`|An das Programm gesendete Beendigungsanforderung|Ignoriert das Signal|  
  
 Wenn das Argument kein gültiges Signal gemäß den oberen Angaben ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Falls keine Behandlung erfolgt, legt die Funktion `errno` auf `EINVAL` fest und gibt einen Wert ungleich 0 \(null\) zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|**raise**|\<signal.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Alle Versionen [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [signal](../../c-runtime-library/reference/signal.md)