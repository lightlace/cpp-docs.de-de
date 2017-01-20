---
title: "_splitpath_s, _wsplitpath_s"
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
  - "_wsplitpath_s"
  - "_splitpath_s"
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
  - "_wsplitpath_s"
  - "splitpath_s"
  - "_splitpath_s"
  - "wsplitpath_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_splitpath_s-Funktion"
  - "_wsplitpath_s-Funktion"
  - "Pfadnamen"
  - "Pfadnamen"
  - "splitpath_s-Funktion"
  - "wsplitpath_s-Funktion"
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: 29
caps.handback.revision: "29"
ms.author: "corob"
manager: "ghogen"
---
# _splitpath_s, _wsplitpath_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterteilt einen Pfadnamen in Komponenten.  Diese Versionen sind von [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md) mit werden, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## Syntax  
  
```  
errno_t _splitpath_s(  
   const char * path,  
   char * drive,  
   size_t driveNumberOfElements,  
   char * dir,  
   size_t dirNumberOfElements,  
   char * fname,  
   size_t nameNumberOfElements,  
   char * ext,   
   size_t extNumberOfElements  
);  
errno_t _wsplitpath_s(  
   const wchar_t * path,  
   wchar_t * drive,  
   size_t driveNumberOfElements,  
   wchar_t *dir,  
   size_t dirNumberOfElements,  
   wchar_t * fname,  
   size_t nameNumberOfElements,  
   wchar_t * ext,  
   size_t extNumberOfElements  
);  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _splitpath_s(  
   const char *path,  
   char (&drive)[drivesize],  
   char (&dir)[dirsize],  
   char (&fname)[fnamesize],  
   char (&ext)[extsize]  
); // C++ only  
template <size_t drivesize, size_t dirsize, size_t fnamesize, size_t extsize>  
errno_t _wsplitpath_s(  
   const wchar_t *path,  
   wchar_t (&drive)[drivesize],  
   wchar_t (&dir)[dirsize],  
   wchar_t (&fname)[fnamesize],  
   wchar_t (&ext)[extsize]  
); // C++ only  
```  
  
#### Parameter  
 \[in\] `path`  
 Vollständiger Pfad.  
  
 \[out\] `drive`  
 Laufwerkbuchstabe, gefolgt von einem Doppelpunkt \(`:`\).  Sie können `NULL` für diesen Parameter übergeben, wenn der Laufwerkbuchstaben benötigen.  
  
 \[in\] `driveNumberOfElements`  
 Die Größe des Puffers `drive` im Einzelbyte\- oder den Breitzeichen.  Wenn `drive``NULL` ist, muss dieser Wert 0.  
  
 \[out\] `dir`  
 Verzeichnispfad, z nachgestellten Schrägstrich.  Schrägstrich \( `/` \), umgekehrte Schrägstriche \( `\` \) oder beide verwendet werden.  Sie können `NULL` für diesen Parameter übergeben, wenn Sie den Verzeichnispfad benötigen.  
  
 \[in\] `dirNumberOfElements`  
 Die Größe des Puffers `dir` im Einzelbyte\- oder den Breitzeichen.  Wenn `dir``NULL` ist, muss dieser Wert 0.  
  
 \[out\] `fname`  
 Geringer Dateiname \(ohne Dateinamenerweiterung\).  Sie können `NULL` für diesen Parameter übergeben, wenn der Dateiname benötigen.  
  
 \[in\] `nameNumberOfElements`  
 Die Größe des Puffers `fname` im Einzelbyte\- oder den Breitzeichen.  Wenn `fname``NULL` ist, muss dieser Wert 0.  
  
 \[out\] `ext`  
 Dateinamenerweiterung, einschließlich führenden Punkt \(**.**\). Sie können `NULL` für diesen Parameter übergeben, wenn Sie nicht die Dateinamenerweiterung benötigen.  
  
 \[in\] `extNumberOfElements`  
 Die Größe von `ext` Puffer im Einzelbyte\- oder den Breitzeichen.  Wenn `ext``NULL` ist, muss dieser Wert 0.  
  
## Rückgabewert  
 Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.  
  
### Fehlerbedingungen  
  
|Bedingung|Rückgabewert|  
|---------------|------------------|  
|`path` ist  `NULL`.|`EINVAL`|  
|`drive` ist `NULL`, `driveNumberOfElements` ist ungleich 0 \(null\)|`EINVAL`|  
|`drive` ist als `NULL`, `driveNumberOfElements` ist ungewöhnlich|`EINVAL`|  
|`dir` ist `NULL`, `dirNumberOfElements` ist ungleich 0 \(null\)|`EINVAL`|  
|`dir` ist als `NULL`, `dirNumberOfElements` ist ungewöhnlich|`EINVAL`|  
|`fname` ist `NULL`, `nameNumberOfElements` ist ungleich 0 \(null\)|`EINVAL`|  
|`fname` ist als `NULL`, `nameNumberOfElements` ist ungewöhnlich|`EINVAL`|  
|`ext` ist `NULL`, `extNumberOfElements` ist ungleich 0 \(null\)|`EINVAL`|  
|`ext` ist als `NULL`, `extNumberOfElements` ist ungewöhnlich|`EINVAL`|  
  
 Wenn eine der oben genannten Bedingungen, tritt der ungültige Parameterhandler wird aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben.  Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
 Wenn eine in Puffern zu kurz, das Ergebnis, freien Raum dieser Funktionen aufzunehmen ist sämtliche Puffer auf leere Zeichenfolgen, legen Sie `errno` auf `ERANGE` und geben `ERANGE` fest.  
  
## Hinweise  
 Die `_splitpath_s` \- Funktion wird ein Pfad in seine vier Komponenten.  `_splitpath_s`  behandelt automatisch Mehrbyte\-Zeichenfolgen\-Argumente entsprechend und derzeit erkennt Mehrbytezeichensequenzen entsprechend der Mehrbyte\-Codepage.  `_wsplitpath_s`  ist eine Breitzeichen\-Version von `_splitpath_s`; die Argumente für `_``wsplitpath_s` sind Zeichenfolgen mit Breitzeichen.  Diese Funktionen identisch verhalten sich andernfalls  
  
### Zuordnung generischer Textroutinen  
  
|TCHAR.H\-Routine|\_UNICODE & \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|----------------------------------------|----------------------|-------------------------|  
|`_tsplitpath_s`|`_splitpath_s`|`_splitpath_s`|`_wsplitpath_s`|  
  
 Jede Komponente des vollständigen Pfads wird in einem separaten Puffer gespeichert; die Manifestkonstanten `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME` und `_MAX_EXT` \(definiert in STDLIB.H\) Geben Sie die maximal zulässige Größe für jede Dateikomponente an.  Erfassen Sie die Komponenten, die als entsprechende Manifest Konstantenursachen\-Heapbeschädigung größer sind.  
  
 In der folgenden Tabelle sind die Werte der Manifestkonstanten auf.  
  
|Name|Wert|  
|----------|----------|  
|\_MAX\_DRIVE|3|  
|\_MAX\_DIR|256|  
|\_MAX\_FNAME|256|  
|\_MAX\_EXT|256|  
  
 Wenn der vollständige Pfad keine Komponente, \(beispielsweise ein Dateiname\) enthält, wird `_splitpath_s` eine leere Zeichenfolge an den entsprechenden Puffer zu.  
  
 Die Verwendung dieser Funktionen in C\+\+ wird durch Überladungen \(als Vorlagen vorhanden\) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss.  Weitere Informationen finden Sie unter [Sichere Vorlagenüberladungen](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf.  Mit [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md) deaktivieren Sie dieses Verhalten.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_splitpath_s`|\<stdlib.h\>|  
|`_wsplitpath_s`|\<stdlib.h\> oder \<wchar.h\>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## Beispiel  
 Ein Beispiel hierfür finden Sie unter [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## .NET Framework-Entsprechung  
 Nicht zutreffend. Mit `PInvoke` rufen Sie die Standard\-C\-Funktion auf. Weitere Informationen finden Sie unter [Beispiele für Plattformaufrufe](../Topic/Platform%20Invoke%20Examples.md).  
  
## Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)