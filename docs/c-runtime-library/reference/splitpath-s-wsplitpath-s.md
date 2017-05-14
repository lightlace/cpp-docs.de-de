---
title: _splitpath_s, _wsplitpath_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsplitpath_s
- _splitpath_s
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wsplitpath_s
- splitpath_s
- _splitpath_s
- wsplitpath_s
dev_langs:
- C++
helpviewer_keywords:
- splitpath_s function
- pathnames
- _splitpath_s function
- _wsplitpath_s function
- path names
- wsplitpath_s function
ms.assetid: 30fff3e2-cd00-4eb6-b5a2-65db79cb688b
caps.latest.revision: 29
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: c4c6803731deba188a4f4dba118b04f626f58564
ms.contentlocale: de-de
ms.lasthandoff: 04/04/2017

---
# <a name="splitpaths-wsplitpaths"></a>_splitpath_s, _wsplitpath_s
Unterteilen eines Pfadnamens in Komponenten Dies sind Versionen von [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md) mit Sicherheitsverbesserungen, wie in [Sicherheitsfunktionen in der CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 [in] `path`  
 Vollständiger Pfad  
  
 [out] `drive`  
 Laufwerkbuchstabe, gefolgt von einem Doppelpunkt (`:`). Sie können `NULL` für diesen Parameter übergeben, wenn Sie den Laufwerksbuchstaben nicht benötigen.  
  
 [in] `driveNumberOfElements`  
 Die Größe des `drive`-Puffers in Einzelbytezeichen oder Breitzeichen. Wenn `drive` `NULL` ist, muss der Wert 0 sein.  
  
 [out] `dir`  
 Verzeichnispfad, einschl. nachstehender Schrägstrich. Führende Schrägstriche ( `/` ), umgekehrte Schrägstriche ( `\` ) oder beide können verwendet werden. Sie können `NULL` für diesen Parameter übergeben, wenn Sie den Verzeichnispfad nicht benötigen.  
  
 [in] `dirNumberOfElements`  
 Die Größe des `dir`-Puffers in Einzelbytezeichen oder Breitzeichen. Wenn `dir` `NULL` ist, muss der Wert 0 sein.  
  
 [out] `fname`  
 Basisdateiname (ohne Erweiterung). Sie können `NULL` für diesen Parameter übergeben, wenn Sie den Dateinamen nicht benötigen.  
  
 [in] `nameNumberOfElements`  
 Die Größe des `fname`-Puffers in Einzelbytezeichen oder Breitzeichen. Wenn `fname` `NULL` ist, muss der Wert 0 sein.  
  
 [out] `ext`  
 Dateierweiterung mit führendem Punkt (**.**). Sie können `NULL` für diesen Parameter übergeben, wenn Sie die Dateierweiterung nicht benötigen.  
  
 [in] `extNumberOfElements`  
 Die Größe des `ext`-Puffers in Einzelbytezeichen oder Breitzeichen. Wenn `ext` `NULL` ist, muss der Wert 0 sein.  
  
## <a name="return-value"></a>Rückgabewert  
 Null, wenn erfolgreich, ein Fehlercode, wenn ein Fehler auftritt.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|Bedingung|Rückgabewert|  
|---------------|------------------|  
|`path` ist gleich `NULL`.|`EINVAL`|  
|`drive` ist gleich `NULL`, `driveNumberOfElements` ist ungleich null|`EINVAL`|  
|`drive` ist ungleich `NULL`, `driveNumberOfElements` ist null|`EINVAL`|  
|`dir` ist gleich `NULL`, `dirNumberOfElements` ist ungleich null|`EINVAL`|  
|`dir` ist ungleich `NULL`, `dirNumberOfElements` ist null|`EINVAL`|  
|`fname` ist gleich `NULL`, `nameNumberOfElements` ist ungleich null|`EINVAL`|  
|`fname` ist ungleich `NULL`, `nameNumberOfElements` ist null|`EINVAL`|  
|`ext` ist gleich `NULL`, `extNumberOfElements` ist ungleich null|`EINVAL`|  
|`ext` ist ungleich `NULL`, `extNumberOfElements` ist null|`EINVAL`|  
  
 Wenn eine dieser Bedingungen auftritt, wird die Ausnahme für ungültige Parameter aufgerufen, wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben `EINVAL` zurück.  
  
 Wenn einer der Puffer zu kurz ist, um das Ergebnis aufzunehmen, löschen diese Funktionen alle Puffer in leere Zeichenfolgen, setzen `errno` auf `ERANGE` und geben `ERANGE` zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_splitpath_s`-Funktion teilt einen Pfad in seine vier Komponenten auf. `_splitpath_s` behandelt Multibyte-Zeichenfolgenargumente automatisch richtig. Die Erkennung von Multibyte-Zeichenfolgen erfolgt auf der Grundlage der aktuell verwendeten Multibyte-Codeseite. `_wsplitpath_s` ist eine Breitzeichenversion von `_splitpath_s`. Die Argumente für `_``wsplitpath_s` sind Zeichenfolgen mit Breitzeichen. Andernfalls verhalten sich diese Funktionen identisch  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath_s`|`_splitpath_s`|`_splitpath_s`|`_wsplitpath_s`|  
  
 Jede Komponente des vollständigen Pfads wird in einem separaten Puffer gespeichert. Die Manifestkonstanten `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME` und `_MAX_EXT` (in STDLIB.H definiert) geben die maximal zulässige Größe für jede Dateikomponente an. Dateikomponenten, die größer als die entsprechenden Manifestkonstanten sind, können zur Beschädigung des Heaps führen.  
  
 In der folgenden Tabelle werden die Werte der Manifestkonstanten aufgelistet.  
  
|Name|Wert|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 Wenn der vollständige Pfad keine Komponente (z.B. Dateiname) enthält, weist `_splitpath_s` dem entsprechenden Puffer eine leere Zeichenfolge zu.  
  
 Die Verwendung dieser Funktionen in C++ wird durch Überladungen (als Vorlagen vorhanden) vereinfacht. Überladungen können automatisch die Pufferlänge ableiten, sodass kein Größenargument angegeben werden muss. Weitere Informationen finden Sie unter [Secure Template Overloads (Sichere Vorlagenüberladungen)](../../c-runtime-library/secure-template-overloads.md).  
  
 Die Debugversionen dieser Funktionen füllen zunächst den Puffer mit "0xFD" auf. Um dieses Verhalten zu deaktivieren, verwenden Sie [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_splitpath_s`|\<stdlib.h>|  
|`_wsplitpath_s`|\<stdlib.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [_makepath_s _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)
