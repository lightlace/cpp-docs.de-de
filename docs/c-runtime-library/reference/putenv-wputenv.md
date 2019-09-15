---
title: _putenv, _wputenv
ms.date: 11/04/2016
api_name:
- _putenv
- _wputenv
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tputenv
- _wputenv
- _putenv
- wputenv
- tputenv
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
ms.openlocfilehash: 8fe699a476ea1dd09a6ce9922294bce398df16b2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70949882"
---
# <a name="_putenv-_wputenv"></a>_putenv, _wputenv

Erstellt, ändert oder entfernt Umgebungsvariablen. Sicherere Versionen dieser Funktionen sind verfügbar. Informationen dazu finden Sie unter [_putenv_s, _wputenv_s](putenv-s-wputenv-s.md).

> [!IMPORTANT]
> Diese API kann nicht in Anwendungen verwendet werden, die in Windows-Runtime ausgeführt werden. Weitere Informationen finden Sie im Artikel [CRT functions not supported in Universal Windows Platform apps (In Apps für die universelle Windows-Plattform nicht unterstützte CRT-Funktionen)](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Syntax

```C
int _putenv(
   const char *envstring
);
int _wputenv(
   const wchar_t *envstring
);
```

### <a name="parameters"></a>Parameter

*envstring*<br/>
Definition der Umgebungszeichenfolge.

## <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn erfolgreich, oder-1 im Fall eines Fehlers.

## <a name="remarks"></a>Hinweise

Die **_putenv** -Funktion fügt neue Umgebungsvariablen hinzu oder ändert die Werte vorhandener Umgebungsvariablen. Umgebungsvariablen definieren die Umgebung, in der ein Prozess ausgeführt wird (beispielsweise der Standardsuchpfad für die mit einem Programm zu verknüpfenden Bibliotheken). **_wputenv** ist eine breit Zeichen Version von **_putenv**. Das *envstring* -Argument für **_wputenv** ist eine Zeichenfolge mit breit Zeichen.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

Das *envstring* -Argument muss ein Zeiger auf eine Zeichenfolge in der Form *varname*=*value_string*sein, wobei *varname* der Name der hinzu zufügenden oder zu ändernden Umgebungsvariablen und *value_string* der der Variablen ist. Wert. Wenn *varname* bereits Teil der Umgebung ist, wird sein Wert durch *value_string*ersetzt; Andernfalls werden die neue *varname* -Variable und Ihr *value_string* -Wert der Umgebung hinzugefügt. Sie können eine Variable aus der Umgebung entfernen, indem Sie eine leere *value_string*angeben, oder anders ausgedrückt, indem Sie nur *varname*= angeben.

**_putenv** und **_wputenv** wirken sich nur auf die Umgebung aus, die für den aktuellen Prozess lokal ist. Sie können Sie nicht zum Ändern der Umgebung auf Befehls Ebene verwenden. Das bedeutet, dass diese Funktionen nur bei Datenstrukturen funktionieren, auf die die Laufzeitbibliothek zugreifen kann, aber nicht bei dem Umgebungssegment, das vom Betriebssystem für einen Prozess erstellt wurde. Wenn der aktuelle Prozess beendet wird, wird die Umgebung auf die Ebene des aufrufenden Prozesses zurückgesetzt (in den meisten Fällen die Betriebssystemebene). Die geänderte Umgebung kann jedoch an alle neuen, von **_spawn**, **_exec**oder **System**erstellten Prozesse übermittelt werden, und diese neuen Prozesse erhalten alle neuen Elemente, die von **_putenv** und **_wputenv**hinzugefügt werden.

Ändern Sie keinen Umgebungs Eintrag direkt: Verwenden Sie stattdessen **_putenv** oder **_wputenv** , um ihn zu ändern. Insbesondere direkte Freigabe Elemente des globalen Arrays " **_environ []** " können dazu führen, dass ein ungültiger Speicher adressiert wird.

**getenv** und **_putenv** verwenden die globale Variable **_environ** , um auf die Umgebungs Tabelle zuzugreifen. **_wgetenv** und **_wputenv** verwenden Sie **_wenviron**. **_putenv** und **_wputenv** können den Wert von **_environ** und **_wenviron**ändern, wodurch das **_envp** -Argument für **Main** und das **_wenvp** -Argument für **wmain**ungültig wird. Daher ist es sicherer, **_environ** oder **_wenviron** zu verwenden, um auf die Umgebungs Informationen zuzugreifen. Weitere Informationen zur Beziehung zwischen **_putenv** und **_wputenv** und globalen Variablen finden Sie unter [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> Die **_putenv** -und **_getenv** -Funktions Familien sind nicht Thread sicher. **_getenv** könnte einen Zeichen folgen Zeiger zurückgeben, während **_putenv** die Zeichenfolge ändert, was zu zufälligen Fehlern führt. Stellen Sie sicher, dass Aufrufe dieser Funktionen synchronisiert sind.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_putenv**|\<stdlib.h>|
|**_wputenv**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **_putenv**finden Sie unter [getenv, _wgetenv](getenv-wgetenv.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
