---
title: "_splitpath, _wsplitpath | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wsplitpath"
  - "_splitpath"
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
  - "wsplitpath"
  - "_splitpath"
  - "splitpath"
  - "_wsplitpath"
  - "_tsplitpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_splitpath-Funktion"
  - "_tsplitpath-Funktion"
  - "_wsplitpath-Funktion"
  - "Pfadnamen"
  - "Pfadnamen"
  - "splitpath-Funktion"
  - "tsplitpath-Funktion"
  - "wsplitpath-Funktion"
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# _splitpath, _wsplitpath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterbrechen Sie einen Pfadnamen in Komponenten.  Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
## Syntax  
  
```  
void _splitpath(  
   const char *path,  
   char *drive,  
   char *dir,  
   char *fname,  
   char *ext   
);  
void _wsplitpath(  
   const wchar_t *path,  
   wchar_t *drive,  
   wchar_t *dir,  
   wchar_t *fname,  
   wchar_t *ext   
);  
```  
  
#### Parameter  
 `path`  
 Vollständiger Pfad.  
  
 `drive`  
 Laufwerkbuchstabe, gefolgt von einem Doppelpunkt \(`:`\).  Sie können `NULL` für diesen Parameter übergeben, wenn der Laufwerkbuchstaben benötigen.  
  
 `dir`  
 Verzeichnispfad, z nachgestellten Schrägstrich.  Schrägstrich \( `/` \), umgekehrte Schrägstriche \( `\` \) oder beide verwendet werden.  Sie können `NULL` für diesen Parameter übergeben, wenn Sie den Verzeichnispfad benötigen.  
  
 `fname`  
 Geringer Dateiname \(ohne Erweiterung\).  Sie können `NULL` für diesen Parameter übergeben, wenn der Dateiname benötigen.  
  
 `ext`  
 Dateinamenerweiterung, einschließlich führenden Punkt \(`.`\).  Sie können `NULL` für diesen Parameter übergeben, wenn Sie nicht die Dateinamenerweiterung benötigen.  
  
## Hinweise  
 Die `_splitpath`\-Funktion wird ein Pfad in seine vier Komponenten.  `_splitpath` behandelt automatisch Mehrbyte\-Zeichenfolgen\-Argumente entsprechend und derzeit erkennt Mehrbytezeichensequenzen entsprechend der Mehrbyte\-Codepage.  `_wsplitpath` ist eine Breitzeichenversion von `_splitpath`. Die Argumente für `_wsplitpath` sind Zeichenfolgen mit Breitzeichen.  Anderenfalls verhalten sich diese Funktionen identisch.  
  
 **Sicherheitshinweis** Diese Funktionen stellen eine mögliche Bedrohung aufgrund eines Pufferüberlaufproblems dar.  Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen.  Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795).  Sicherere Versionen dieser Funktionen sind verfügbar; finden Sie unter [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tsplitpath`|`_splitpath`|`_splitpath`|`_wsplitpath`|  
  
 Jede Komponente des vollständigen Pfads wird in einem separaten Puffer gespeichert; die Manifestkonstanten `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME` und `_MAX_EXT` \(definiert in STDLIB.H\) Geben Sie die maximale Größe für jede Dateikomponente an.  Erfassen Sie Komponenten, die größer sind, als die entsprechende Konstantenursachen\-Heapbeschädigung Manifest.  
  
 Jeder Puffer muss wie die zugehörige Manifest Konstanten so groß sein, potenziellen Pufferüberlauf zu vermeiden.  
  
 In der folgenden Tabelle sind die Werte der Manifestkonstanten auf.  
  
|Name|Wert|  
|----------|----------|  
|\_MAX\_DRIVE|3|  
|\_MAX\_DIR|256|  
|\_MAX\_FNAME|256|  
|\_MAX\_EXT|256|  
  
 Wenn der vollständige Pfad keine Komponente, \(beispielsweise ein Dateiname\) enthält, weist `_splitpath` leere Zeichenfolgen den entsprechenden Puffer zu.  
  
 Sie können `NULL` auf `_splitpath` für jeden Parameter unterschiedlich `path`  übergeben, das Sie nicht benötigen.  
  
 Wenn `path` den Wert `NULL` annimmt, wird der ungültige Parameterhandler, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben, aufgerufen.  Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `EINVAL` zurück.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_splitpath`|\<stdlib.h\>|  
|`_wsplitpath`|\<stdlib.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Im Beispiel für [\_makepath](../../c-runtime-library/reference/makepath-wmakepath.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)