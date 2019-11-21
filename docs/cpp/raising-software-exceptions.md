---
title: Auslösen von Softwareausnahmen
ms.date: 11/04/2016
helpviewer_keywords:
- run-time errors, treating as exceptions
- exception handling [C++], errors as exceptions
- exceptions [C++], flagging errors as exceptions
- errors [C++], treating as exceptions
- exception handling [C++], detecting errors
- structured exception handling [C++], errors as exceptions
- exceptions [C++], software
- RaiseException function
- software exceptions [C++]
- formats [C++], exception codes
ms.assetid: be1376c3-c46a-4f52-ad1d-c2362840746a
ms.openlocfilehash: 7c58ae2e2b6635345a162d11d2b75a9865d37751
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246408"
---
# <a name="raising-software-exceptions"></a>Auslösen von Softwareausnahmen

Einige der häufigsten Programmfehlerquellen werden vom System nicht als Ausnahmen gekennzeichnet. Wenn Sie beispielsweise versuchen, einen Speicherblock zu belegen, jedoch unzureichend Arbeitsspeicher vorhanden ist, löst die Laufzeit oder API-Funktion keine Ausnahme aus, sondern gibt einen Fehlercode zurück.

However, you can treat any condition as an exception by detecting that condition in your code and then reporting it by calling the [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) function. Indem Sie Fehler auf diese Weise kennzeichnen, können Sie die Vorteile der strukturierten Ausnahmebehandlung für jede Art von Laufzeitfehler nutzen.

So verwenden Sie die strukturierte Ausnahmebehandlung bei Fehlern

- Definieren Sie einen eigenen Ausnahmecode für das Ereignis.

- Call `RaiseException` when you detect a problem.

- Verwenden Sie Ausnahmebehandlungsfilter, um den von Ihnen definierten Ausnahmecode zu testen.

The \<winerror.h> file shows the format for exception codes. Um sicherzustellen, dass Sie keinen Code definieren, der in Konflikt mit einem vorhandenen Ausnahmecode steht, legen Sie das dritte höchstwertige Bit auf 1 fest. Die vier höchstwertigen Bits sollten so festgelegt werden, wie in der folgenden Tabelle gezeigt.

|Bits|Empfohlene Binäreinstellung|Beschreibung|
|----------|--------------------------------|-----------------|
|31-30|11|Diese zwei Bits beschreiben den grundlegenden Status des Codes: 11 = Fehler, 00 = Erfolg, 01 = Information, 10 = Warnung.|
|29|1|Clientbit. Wird für benutzerdefinierten Code auf 1 festgelegt.|
|28|0|Reservierte Bitzahl. (Festlegung auf 0 beibehalten.)|

Sie können die ersten zwei Bits optional auf eine andere Einstellung als binär 11 festlegen, obwohl die Einstellung "Fehler" für die meisten Ausnahmen angemessen ist. Es ist wichtig, daran zu denken, Bits 29 und 28 so festzulegen, wie es in der vorherigen Tabelle gezeigt wurde.

The resulting error code should therefore have the highest four bits set to hexadecimal E. For example, the following definitions define exception codes that do not conflict with any Windows exception codes. (Sie müssen jedoch prüfen, welche Codes von Drittanbieter-DLLs verwendet werden).

```cpp
#define STATUS_INSUFFICIENT_MEM       0xE0000001
#define STATUS_FILE_BAD_FORMAT        0xE0000002
```

Nachdem Sie einen Ausnahmecode definiert haben, können Sie ihn verwenden, um eine Ausnahme auszulösen. For example, the following code raises the `STATUS_INSUFFICIENT_MEM` exception in response to a memory allocation problem:

```cpp
lpstr = _malloc( nBufferSize );
if (lpstr == NULL)
    RaiseException( STATUS_INSUFFICIENT_MEM, 0, 0, 0);
```

Wenn Sie einfach eine Ausnahme auslösen möchten, können Sie die letzten drei Parameter auf 0 festlegen. Die drei letzten Parameter übergeben zusätzliche Informationen und legen Flags fest, die Handler beim Fortsetzen der Ausführung hindern. See the [RaiseException](/windows/win32/api/errhandlingapi/nf-errhandlingapi-raiseexception) function in the Windows SDK for more information.

In den Ausnahmebehandlungsfiltern können Sie dann die Codes testen, die Sie definiert haben. Beispiel:

```cpp
__try {
    ...
}
__except (GetExceptionCode() == STATUS_INSUFFICIENT_MEM ||
        GetExceptionCode() == STATUS_FILE_BAD_FORMAT )
```

## <a name="see-also"></a>Siehe auch

[Writing an exception handler](../cpp/writing-an-exception-handler.md)<br/>
[Structured exception handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)