---
title: _putenv_s, _wputenv_s | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wputenv_s
- _putenv_s
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
apitype: DLLExport
f1_keywords:
- putenv_s
- wputenv_s
- _wputenv_s
- _putenv_s
dev_langs: C++
helpviewer_keywords:
- wputenv_s function
- _putenv_s function
- environment variables, deleting
- putenv_s function
- _wputenv_s function
- environment variables, creating
- environment variables, modifying
ms.assetid: fbf51225-a8da-4b9b-9d7c-0b84ef72df18
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b7d55736daf6652ecbde6b0d16256ccebc206bb5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="putenvs-wputenvs"></a>_putenv_s, _wputenv_s
Erstellt, ändert oder entfernt Umgebungsvariablen. Dies sind Versionen von [_putenv, _wputenv](../../c-runtime-library/reference/putenv-wputenv.md), enthalten aber Sicherheitserweiterungen wie unter [Sicherheitserweiterungen im CRT](../../c-runtime-library/security-features-in-the-crt.md) beschrieben.  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [In /ZW nicht unterstützte CRT-Funktionen](http://msdn.microsoft.com/en-us/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```  
errno_t _putenv_s(  
   const char *name,  
   const char *value   
);  
errno_t _wputenv_s(  
   const wchar_t *name,  
   const wchar_t *value  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `name`  
 Der Umgebungsvariablenname.  
  
 `value`  
 Der Wert, auf den die Umgebungsvariable festgelegt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null) zurück, wenn erfolgreich, oder einen Fehlercode.  
  
### <a name="error-conditions"></a>Fehlerbedingungen  
  
|`name`|`value`|Rückgabewert|  
|------------|-------------|------------------|  
|`NULL`|any|`EINVAL`|  
|any|`NULL`|`EINVAL`|  
  
 Wenn einer dieser Fehlerzustände auftritt, wird ein Handler für ungültige Parameter von diesen Funktionen aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn die weitere Ausführung zugelassen wird, geben diese Funktionen `EINVAL` zurück und stellen `errno` auf `EINVAL` ein.  
  
## <a name="remarks"></a>Hinweise  
 Die `_putenv_s`-Funktion fügt neue Umgebungsvariablen hinzu oder ändert die Werte vorhandener Umgebungsvariablen. Umgebungsvariablen definieren die Umgebung, in der ein Prozess ausgeführt wird (beispielsweise der Standardsuchpfad für die mit einem Programm zu verknüpfenden Bibliotheken). `_wputenv_s` ist eine Breitzeichenversion von `_putenv_s`. Das `envstring`-Argument für `_wputenv_s` ist eine Breitzeichenfolge.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|TCHAR.H-Routine|_UNICODE und _MBCS nicht definiert.|_MBCS definiert|_UNICODE definiert|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tputenv_s`|`_putenv_s`|`_putenv_s`|`_wputenv_s`|  
  
 `name` ist der Name der Umgebungsvariable,der hinzugefügt oder geändert werden soll, und `value` ist der Wert der Variablen. Wenn `name` bereits Teil der Umgebung ist, wird sein Wert durch `value` ersetzt. Andernfalls werden die neue `name`-Variable und ihr `value`-Wert zur Umgebung hinzugefügt. Sie können eine Variable aus der Umgebung entfernen, indem Sie eine leere Zeichenfolge (d. h. "") für `value` angeben.  
  
 `_putenv_s` und `_wputenv_s` wirken sich nur auf die Umgebung aus, die für den aktuellen Prozess lokal ist. Sie können sie nicht zum Ändern der Umgebung auf Befehlsebene verwenden. Diese Funktionen funktionieren nur bei Datenstrukturen, auf die die Laufzeitbibliothek zugreifen kann, aber nicht bei dem Umgebungssegment, das vom Betriebssystem für einen Prozess erstellt wurde. Wenn der aktuelle Prozess beendet wird, wird die Umgebung auf die Ebene des aufrufenden Prozesses zurückgesetzt (in den meisten Fällen die Betriebssystemebene). Die geänderte Umgebung kann jedoch an alle neue Prozesse übergeben werden, die von `_spawn`, `_exec` oder `system` erstellt werden, und diese neuen Prozesse rufen alle neuen Elemente ab, die von `_putenv_s` und `_wputenv_s` hinzugefügt werden.  
  
 Ändern Sie keinen Umgebungseintrag direkt, verwenden Sie stattdessen zum Ändern `_putenv_s` oder `_wputenv_s`. Das direkte Loslösen von Elementen des globalen `_environ[]`-Arrays kann nämlich dazu führen, dass ein ungültiger Speicher adressiert wird.  
  
 `getenv` und `_putenv_s` verwenden die globale Variable `_environ`, um auf die Umgebungstabelle zuzugreifen; `_wgetenv` und `_wputenv_s` verwenden `_wenviron`. `_putenv_s` und `_wputenv_s` ändern möglicherweise den Wert von `_environ` und `_wenviron`, wodurch das `envp`-Argument für `main` und das `_wenvp`-Argument für `wmain` ungültig werden. Es ist daher sicherer mit `_environ` oder `_wenviron` auf die Umgebungsinformationen zuzugreifen. Weitere Informationen über die Beziehung von `_putenv_s` und `_wputenv_s` mit globalen Variablen finden Sie unter [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Die Familien `_putenv_s` und `_getenv_s` der Funktionen sind nicht threadsicher. `_getenv_s` gibt möglicherweise einen Zeichenfolgenzeiger zurück, während `_putenv_s` die Zeichenfolge ändert, was zu zufälligen Fehlern führen kann. Stellen Sie sicher, dass Aufrufe dieser Funktionen synchronisiert sind.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_putenv_s`|\<stdlib.h>|  
|`_wputenv_s`|\<stdlib.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel, das die Verwendung von `_putenv_s` zeigt, finden Sie unter [getenv_s, _wgetenv_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Process and Environment Control (Prozess- und Umgebungssteuerung)](../../c-runtime-library/process-and-environment-control.md)   
 [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)