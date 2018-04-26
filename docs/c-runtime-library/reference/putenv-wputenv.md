---
title: _putenv, _wputenv | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 74984106c94ec3b6af1811fba63707d7d5056791
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="putenv-wputenv"></a>_putenv, _wputenv

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

Geben Sie 0, wenn erfolgreich, oder-1 im Fall eines Fehlers zurück.

## <a name="remarks"></a>Hinweise

Die **_putenv** -Funktion fügt neue Umgebungsvariablen hinzu oder ändert die Werte vorhandener Umgebungsvariablen. Umgebungsvariablen definieren die Umgebung, in der ein Prozess ausgeführt wird (beispielsweise der Standardsuchpfad für die mit einem Programm zu verknüpfenden Bibliotheken). **_wputenv** ist eine Breitzeichen-Version von **_putenv**; das *Envstring* Argument **_wputenv** ist eine Breitzeichen-Zeichenfolge.

### <a name="generic-text-routine-mappings"></a>Zuordnung generischer Textroutinen

|Tchar.h-Routine|_UNICODE und _MBCS nicht definiert|_MBCS definiert|_UNICODE definiert|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tputenv**|**_putenv**|**_putenv**|**_wputenv**|

Die *Envstring* Argument muss ein Zeiger auf eine Zeichenfolge der Form *Varname*=*Value_string*, wobei *Varname* ist der Name der Umgebungsvariablen, die hinzugefügt oder geändert werden und *Value_string* ist der Wert der Variablen. Wenn *Varname* ist bereits Teil der Umgebung durch seinen Wert ersetzt *Value_string*ist, andernfalls der neue *Varname* Variable und die zugehörige *Value_string*  -Wert zur Umgebung hinzugefügt. Sie können eine Variable aus der Umgebung entfernen, durch Angabe einer leeres *Value_string*, oder in anderen Worten: durch Angeben von nur *Varname*=.

**_putenv** und **_wputenv** wirken sich auf nur die Umgebung, die für den aktuellen Prozess lokal ist; Sie können nicht zum Ändern der Befehlsebene Umgebung. Das bedeutet, dass diese Funktionen nur bei Datenstrukturen funktionieren, auf die die Laufzeitbibliothek zugreifen kann, aber nicht bei dem Umgebungssegment, das vom Betriebssystem für einen Prozess erstellt wurde. Wenn der aktuelle Prozess beendet wird, wird die Umgebung auf die Ebene des aufrufenden Prozesses zurückgesetzt (in den meisten Fällen die Betriebssystemebene). Allerdings kann die geänderte Umgebung übergeben werden, an alle neue Prozesse erstellt, indem **_spawn**, **_exec**, oder **System**, und diese neuen Prozesse rufen alle neuen Elemente hinzugefügt, indem **_putenv** und **_wputenv**.

Ändern Sie einen Umgebungseintrag nicht direkt: Verwenden Sie stattdessen **_putenv** oder **_wputenv** um ihn zu ändern. Direkte Loslösen von Elementen von der **_environ []** ungültiger Speicher anvisiert wird, globale Array führen.

**Getenv** und **_putenv** verwenden die globale Variable **_environ** auf die umgebungstabelle zuzugreifen; **_wgetenv** und **_wputenv** verwenden **_wenviron**. **_putenv** und **_wputenv** ändern möglicherweise den Wert der **_environ** und **_wenviron**, daher Ungültigkeit der **_envp** Argument für **main** und **_wenvp** Argument **"wmain"**. Es ist daher sicherer mit **_environ** oder **_wenviron** auf die Umgebungsinformationen zuzugreifen. Weitere Informationen über die Beziehung von **_putenv** und **_wputenv** mit globalen Variablen finden Sie unter [_environ, _wenviron](../../c-runtime-library/environ-wenviron.md).

> [!NOTE]
> Die **_putenv** und **_getenv** -Funktionsfamilie sind nicht threadsicher. **_getenv** gibt möglicherweise einen Zeichenfolgenzeiger beim zurück **_putenv** ist die Zeichenfolge ändert, was zu zufällige Fehlern führt. Stellen Sie sicher, dass Aufrufe dieser Funktionen synchronisiert sind.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**_putenv**|\<stdlib.h>|
|**_wputenv**|\<stdlib.h> oder \<wchar.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Beispiel

Ein Beispiel zum Verwenden von **_putenv**, finden Sie unter [Getenv, _wgetenv](getenv-wgetenv.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[getenv, _wgetenv](getenv-wgetenv.md)<br/>
[_searchenv, _wsearchenv](searchenv-wsearchenv.md)<br/>
