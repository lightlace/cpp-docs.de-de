---
title: __fastfail
ms.date: 09/02/2019
ms.assetid: 9cd32639-e395-4c75-9f3a-ac3ba7f49921
ms.openlocfilehash: 34198409c6a57eb494bfe819b367b71405a84e64
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222197"
---
# <a name="__fastfail"></a>__fastfail

**Microsoft-spezifisch**

Beendet den aufrufenden Prozess mit minimalem Aufwand sofort.

## <a name="syntax"></a>Syntax

```C
void __fastfail(unsigned int code);
```

### <a name="parameters"></a>Parameter

*Ordnung*\
in Eine `FAST_FAIL_<description>` symbolische Konstante aus "Winnt. h" oder "WDM. h", die den Grund für die Beendigung des Prozesses angibt.

## <a name="return-value"></a>Rückgabewert

Die systeminterne `__fastfail`-Funktion gibt keinen Wert zurück.

## <a name="remarks"></a>Hinweise

Die `__fastfail` systeminterne Funktion bietet einen Mechanismus für eine *schnelle* Fehler Anforderung – eine Möglichkeit für einen potenziell beschädigten Prozess, sofortige Prozess Beendigung anzufordern. Kritische Fehler, die den Status des Programms und des Stapels unwiederbringlich beschädigt haben können, können von der regulären Ausnahmebehandlungsfunktion nicht verarbeitet werden. Mit `__fastfail` können Sie den Prozess mit minimalem Aufwand beenden.

Intern wird `__fastfail` mithilfe mehrerer architekturspezifischer Mechanismen implementiert:

|Architektur|Anweisung|Speicherort für das Code-Argument|
|------------------|-----------------|-------------------------------|
|x86|int 0x29|`ecx`|
|x64|int 0x29|`rcx`|
|ARM|Opcode 0xDEFB|`r0`|
|ARM64|Opcode 0xF 003|`x0`|

Eine Fast-Fail-Anforderung ist in sich abgeschlossen und erfordert in der Regel nur zwei Anweisungen, die ausgeführt werden müssen. Nachdem eine Anforderung für einen schnellen Ausfall ausgeführt wurde, führt der Kernel dann die entsprechende Aktion aus. Im Benutzermoduscode bestehen keine Speicherabhängigkeiten über den Anweisungszeiger selbst hinaus, wenn ein Fast-Fail-Ereignis ausgelöst wird. Das maximiert seine Zuverlässigkeit, auch bei schwerwiegender Speicher Beschädigung.

Das `code` Argument, eine `FAST_FAIL_<description>` der symbolischen Konstanten aus "Winnt. h" oder "WDM. h", beschreibt den Typ der Fehlerbedingung. Es ist auf Umgebungs spezifische Weise in Fehlerberichte integriert.

Fast-Fail-Anforderungen im Benutzermodus werden als nicht fort Setz Bare Ausnahme mit Ausnahme Code 0xc0000409 und mindestens einem Exception-Parameter angezeigt. Der erste Ausnahmeparameter ist der `code`-Wert. Dieser Ausnahme Code gibt dem Windows-Fehlerberichterstattung (wer) und der debugginginfrastruktur an, dass der Prozess beschädigt ist, und dass minimale Prozess interne Aktionen als Reaktion auf den Fehler ausgeführt werden sollen. Fast-Fail-Anforderungen im Kernelmodus werden mithilfe eines dedizierten Fehlercodes implementiert: `KERNEL_SECURITY_CHECK_FAILURE` (0x139). In beiden Fällen werden keine Ausnahmehandler aufgerufen, da davon ausgegangen wird, dass das Programm sich in einem beschädigten Zustand befindet. Wenn ein Debugger vorhanden ist, erhalten Sie die Möglichkeit, den Zustand des Programms vor dem Beenden zu untersuchen.

Unterstützung für systemeigene Fast-Fail-Mechanismen begann mit Windows 8. Windows-Betriebssysteme, die die schnell fehl geschbige Anweisung nicht unterstützen, behandeln in der Regel eine schnelle `UNEXPECTED_KERNEL_MODE_TRAP` Fehler Anforderung als Zugriffsverletzung oder als bugprüfung. In diesen Fällen wird das Programm dennoch beendet, aber nicht unbedingt so schnell.

`__fastfail` ist nur als systeminterne Funktion verfügbar.

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`__fastfail`|x86, x64, ARM, ARM64|

**Header Datei** \<intrin. h->

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Systeminterne Compilerfunktionen](../intrinsics/compiler-intrinsics.md)
