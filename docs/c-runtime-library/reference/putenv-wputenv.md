---
title: _putenv, _wputenv | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _putenv
- _wputenv
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
dev_langs:
- C++
helpviewer_keywords:
- _putenv function
- environment variables, deleting
- putenv function
- tputenv function
- environment variables, creating
- wputenv function
- _wputenv function
- _tputenv function
- environment variables, modifying
ms.assetid: 9ba9b7fd-276e-45df-8420-d70c4204b8bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 12b1379ea70c841f1689a8b83fae7ca7f43f5789
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="putenv-wputenv"></a>_putenv, _wputenv
Erstellt, ändert oder entfernt Umgebungsvariablen. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_putenv_s, _wputenv_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md).  
  
> [!IMPORTANT]
>  Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie unter [CRT-Funktionen, die in universellen Windows-Plattform-apps nicht unterstützt](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).  
  
## <a name="syntax"></a>Syntax  
  
```  
int _putenv(  
   const char *envstring   
);  
int _wputenv(  
   const wchar_t *envstring   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `envstring`  
 Definition der Umgebungszeichenfolge.  
  
## <a name="return-value"></a>Rückgabewert  
 Geben Sie 0, wenn erfolgreich, oder-1 im Fall eines Fehlers zurück.  
  
## <a name="remarks"></a>Hinweise  
 Die `_putenv`-Funktion fügt neue Umgebungsvariablen hinzu oder ändert die Werte vorhandener Umgebungsvariablen. Umgebungsvariablen definieren die Umgebung, in der ein Prozess ausgeführt wird (beispielsweise der Standardsuchpfad für die mit einem Programm zu verknüpfenden Bibliotheken). `_wputenv` ist eine Breitzeichenversion von `_putenv`. Das `envstring`-Argument für `_wputenv` ist eine Breitzeichenfolge.  
  
### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen  
  
|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tputenv`|`_putenv`|`_putenv`|`_wputenv`|  
  
 Das `envstring`-Argument muss ein Zeiger auf eine Zeichenfolge der Form `varname=string` sein, wobei `varname` der Name der hinzuzufügenden oder zu ändernden Umgebungsvariablen ist und `string` der Wert der Variablen. Wenn `varname` bereits Teil der Umgebung ist, wird sein Wert durch `string`ersetzt. Andernfalls werden die neue `varname`-Variable und ihr `string`-Wert zur Umgebung hinzugefügt. Sie können eine Variable aus der Umgebung entfernen, indem Sie einen leeren `string` angeben, d. h., indem Sie nur `varname=` angeben.  
  
 `_putenv` und `_wputenv` wirken sich nur auf die Umgebung aus, die für den aktuellen Prozess lokal ist. Sie können sie nicht zum Ändern der Umgebung auf Befehlsebene verwenden. Das bedeutet, dass diese Funktionen nur bei Datenstrukturen funktionieren, auf die die Laufzeitbibliothek zugreifen kann, aber nicht bei dem Umgebungssegment, das vom Betriebssystem für einen Prozess erstellt wurde. Wenn der aktuelle Prozess beendet wird, wird die Umgebung auf die Ebene des aufrufenden Prozesses zurückgesetzt (in den meisten Fällen die Betriebssystemebene). Die geänderte Umgebung kann jedoch an alle neue Prozesse übergeben werden, die von `_spawn`, `_exec` oder `system` erstellt werden, und diese neuen Prozesse rufen alle neuen Elemente ab, die von `_putenv` und `_wputenv` hinzugefügt werden.  
  
 Ändern Sie keinen Umgebungseintrag direkt: Verwenden Sie stattdessen zum Ändern `_putenv` oder `_wputenv`. Das direkte Loslösen von Elementen des globalen `_environ[]`-Arrays kann nämlich dazu führen, dass ein ungültiger Speicher anvisiert wird.  
  
 `getenv` und `_putenv` verwenden die globale Variable `_environ`, um auf die Umgebungstabelle zuzugreifen; `_wgetenv` und `_wputenv` verwenden `_wenviron`. `_putenv` und `_wputenv` ändern möglicherweise den Wert der `_environ` und `_wenviron`, daher ungültig der `_envp` Argument `main` und die `_wenvp` Argument `wmain`. Es ist daher sicherer mit `_environ` oder `_wenviron` auf die Umgebungsinformationen zuzugreifen. Weitere Informationen über die Beziehung von `_putenv` und `_wputenv` mit globalen Variablen finden Sie unter [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).  
  
> [!NOTE]
>  Die Familien `_putenv` und `_getenv` der Funktionen sind nicht threadsicher. `_getenv` gibt möglicherweise einen Zeichenfolgenzeiger zurück, während `_putenv` die Zeichenfolge ändert, was zu zufälligen Fehlern führen kann. Stellen Sie sicher, dass Aufrufe dieser Funktionen synchronisiert sind.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|`_putenv`|\<stdlib.h>|  
|`_wputenv`|\<stdlib.h> oder \<wchar.h>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung von `_putenv` finden Sie unter [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Process and Environment Control (Prozess- und Umgebungssteuerung)](../../c-runtime-library/process-and-environment-control.md)   
 [getenv, _wgetenv](../../c-runtime-library/reference/getenv-wgetenv.md)   
 [_searchenv, _wsearchenv](../../c-runtime-library/reference/searchenv-wsearchenv.md)