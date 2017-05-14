---
title: _splitpath, _wsplitpath | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wsplitpath
- _splitpath
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
- wsplitpath
- _splitpath
- splitpath
- _wsplitpath
- _tsplitpath
dev_langs:
- C++
helpviewer_keywords:
- _splitpath function
- pathnames
- wsplitpath function
- splitpath function
- _wsplitpath function
- tsplitpath function
- path names
- _tsplitpath function
ms.assetid: 32bd76b5-1385-4ee8-a64c-abcb541cd2e4
caps.latest.revision: 18
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: bbd6a163df9daf8e699f3ecf52325786fe89d8ea
ms.contentlocale: de-de
ms.lasthandoff: 03/29/2017

---
# <a name="splitpath-wsplitpath"></a>_splitpath, _wsplitpath
Unterteilen Sie einen Pfadnamen in Komponenten. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
## <a name="syntax"></a>Syntax  
  
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
  
#### <a name="parameters"></a>Parameter  
 `path`  
 Vollständiger Pfad  
  
 `drive`  
 Laufwerkbuchstabe, gefolgt von einem Doppelpunkt (`:`). Sie können `NULL` für diesen Parameter übergeben, wenn Sie den Laufwerksbuchstaben nicht benötigen.  
  
 `dir`  
 Verzeichnispfad, einschl. nachstehender Schrägstrich. Führende Schrägstriche ( `/` ), umgekehrte Schrägstriche ( `\` ) oder beide können verwendet werden. Sie können `NULL` für diesen Parameter übergeben, wenn Sie den Verzeichnispfad nicht benötigen.  
  
 `fname`  
 Basisdateiname (ohne Erweiterung). Sie können `NULL` für diesen Parameter übergeben, wenn Sie den Dateinamen nicht benötigen.  
  
 `ext`  
 Dateierweiterung, einschl. führender Punkt (`.`). Sie können `NULL` für diesen Parameter übergeben, wenn Sie die Dateierweiterung nicht benötigen.  
  
## <a name="remarks"></a>Hinweise  
 Die `_splitpath`-Funktion teilt einen Pfad in seine vier Komponenten auf. `_splitpath` behandelt Multibyte-Zeichenfolgenargumente automatisch richtig. Die Erkennung von Multibyte-Zeichenfolgen erfolgt auf der Grundlage der aktuell verwendeten Multibyte-Codeseite. `_wsplitpath` ist eine Breitzeichenversion von `_splitpath`. Die Argumente für `_wsplitpath` sind Zeichenfolgen mit Breitzeichen. Anderenfalls verhalten sich diese Funktionen identisch.  
  
 **Sicherheitshinweis:** Diese Funktionen stellen eine mögliche Bedrohung aufgrund eines Pufferüberlaufproblems dar. Pufferüberlaufprobleme werden häufig bei Systemangriffen eingesetzt, da sie zu einer unbefugten Ausweitung der Berechtigungen führen. Weitere Informationen finden Sie unter [Vermeiden von Pufferüberläufen](http://msdn.microsoft.com/library/windows/desktop/ms717795). Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md).  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tsplitpath`|`_splitpath`|`_splitpath`|`_wsplitpath`|  
  
 Jede Komponente des vollständigen Pfads wird in einem separaten Puffer gespeichert. Die Manifestkonstanten `_MAX_DRIVE`, `_MAX_DIR`, `_MAX_FNAME` und `_MAX_EXT` (in STDLIB.H definiert) geben die maximale Größe für jede Dateikomponente an. Dateikomponenten, die größer als die entsprechenden Manifestkonstanten sind, können zur Beschädigung des Heaps führen.  
  
 Jeder Puffer muss so groß wie die entsprechende Manifestkonstante sein, damit ein potenzieller Pufferüberlauf vermieden werden kann.  
  
 In der folgenden Tabelle werden die Werte der Manifestkonstanten aufgelistet.  
  
|Name|Wert|  
|----------|-----------|  
|_MAX_DRIVE|3|  
|_MAX_DIR|256|  
|_MAX_FNAME|256|  
|_MAX_EXT|256|  
  
 Wenn der vollständige Pfad keine Komponente (z.B. Dateiname) enthält, weist `_splitpath` den entsprechenden Puffern leere Zeichenfolgen zu.  
  
 Sie können `NULL` an `_splitpath` für alle Parameter außer `path` übergeben, die Sie nicht benötigen.  
  
 Wenn `path` `NULL` ist, wird der Handler für ungültige Parameter wie in [Parameter Validation (Parameterüberprüfung)](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, wird `errno` auf `EINVAL` gesetzt, und die Funktion gibt `EINVAL` zurück.  
  
## <a name="requirements"></a>Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------|  
|`_splitpath`|\<stdlib.h>|  
|`_wsplitpath`|\<stdlib.h> oder \<wchar.h>|  
  
 Zusätzliche Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md) in der Einführung.  
  
## <a name="example"></a>Beispiel  
 Siehe Beispiel für [_makepath](../../c-runtime-library/reference/makepath-wmakepath.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dateibehandlung](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_splitpath_s, _wsplitpath_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)
