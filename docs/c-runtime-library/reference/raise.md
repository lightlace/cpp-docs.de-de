---
title: raise
ms.date: 01/02/2018
apiname:
- raise
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- Raise
helpviewer_keywords:
- signals, sending to executing programs
- raise function
- signals
- programs [C++], sending signals to executing programs
ms.openlocfilehash: 1354c76207d6cd59249f6c06df88ae23fe69b1e0
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927421"
---
# <a name="raise"></a>raise

Sendet ein Signal an das ausführende Programm.

> [!NOTE]
> Verwenden Sie diese Methode nicht zum Herunterfahren einer Microsoft Store-App, mit Ausnahme von Test-oder Debugszenarien. Programmgesteuerte oder UI-Methoden zum Schließen einer Store-App sind gemäß den [Microsoft Store Richtlinien](/legal/windows/agreements/store-policies)nicht zulässig. Weitere Informationen finden Sie unter [UWP-App-Lebenszyklus](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Syntax

```C
int raise(
   int sig
);
```

### <a name="parameters"></a>Parameter

*sig*<br/>
Auszulösendes Signal.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg gibt **raise** 0 zurück . Andernfalls gibt es einen Wert ungleich 0 (null) zurück.

## <a name="remarks"></a>Hinweise

Die **raise**-Funktion sendet *sig* an das ausführende Programm. Wenn ein vorheriger Aufruf von **signal** eine Signalverarbeitungsfunktion für *sig* installiert hat, führt **raise** diese Funktion aus. Wenn keine Handlerfunktion installiert wurde, wird die dem Signalwert *sig* zugeordnete Standardaktion wie folgt ausgeführt.

|Signal|Bedeutung|Default|
|------------|-------------|-------------|
|**SIGABRT**|Nicht ordnungsgemäße Beendigung|Beendet das aufrufende Programm mit Exitcode 3|
|**SIGFPE**|Gleitkommafehler|Beendet das aufrufende Programm|
|**SIGILL**|Ungültige Anweisung|Beendet das aufrufende Programm|
|**SIGINT**|STRG+C-Unterbrechung|Beendet das aufrufende Programm|
|**SIGSEGV**|Ungültiger Speicherzugriff|Beendet das aufrufende Programm|
|**SIGTERM**|An das Programm gesendete Beendigungsanforderung|Ignoriert das Signal|

Wenn das Argument kein gültiges Signal gemäß den oberen Angaben ist, wird der Handler für ungültige Parameter aufgerufen, wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben. Wenn keine Behandlung erfolgt, legt die Funktion **errno** auf **EINVAL** fest und gibt einen Wert ungleich 0 (null) zurück.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**raise**|\<signal.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Siehe auch

[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[signal](signal.md)<br/>
