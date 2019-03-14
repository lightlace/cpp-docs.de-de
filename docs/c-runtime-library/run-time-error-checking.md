---
title: Laufzeitfehlerüberprüfung
ms.date: 11/04/2016
f1_keywords:
- c.runtime
helpviewer_keywords:
- run-time error checking
- run-time errors, checking
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
ms.openlocfilehash: ec07b9b0c6aa52187c3c24bff4cc51712dbf9fc8
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746460"
---
# <a name="run-time-error-checking"></a>Laufzeitfehlerüberprüfung

Die C-Laufzeitbibliothek enthält die Funktionen, die Laufzeitfehlerüberprüfungen (Run-Time Error Checks, RTC) unterstützen. Mit der Laufzeitfehlerüberprüfung können Sie Ihr Programm so erstellen, dass bestimmte Arten von Laufzeitfehlern gemeldet werden. Sie geben an, welche Arten von Fehlern gemeldet werden sollen und wie die Meldung erfolgen soll. Weitere Informationen finden Sie unter [Vorgehensweise: Use Native Run-Time Checks (Verwenden von nativen Laufzeitüberprüfungen)](/visualstudio/debugger/how-to-use-native-run-time-checks).

Verwenden Sie die folgenden Funktionen, um die Art und Weise anzupassen, in der Ihr Programm die Laufzeitfehlerüberprüfung ausführt.

## <a name="run-time-error-checking-functions"></a>Funktionen der Laufzeitfehlerüberprüfung

|Funktion|Verwendung|
|--------------|---------|
|[_RTC_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Gibt eine kurze Beschreibung des Typs einer Laufzeitfehlerüberprüfung zurück.|
|[_RTC_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Gibt die Gesamtzahl der Fehler zurück, die durch die Laufzeitfehlerüberprüfungen erkannt werden können.|
|[_RTC_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Legt eine Funktion als Handler für das Melden von Laufzeitfehlerüberprüfungen fest.|
|[_RTC_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Ordnet einen Fehler, der von den Laufzeitfehlerüberprüfungen erkannt wurde, einem Typ zu.|

## <a name="see-also"></a>Siehe auch

[Universelle C-Laufzeitroutinen nach Kategorie](../c-runtime-library/run-time-routines-by-category.md)<br/>
[/RTC (Laufzeitfehlerüberprüfungen)](../build/reference/rtc-run-time-error-checks.md)<br/>
[runtime_checks](../preprocessor/runtime-checks.md)<br/>
[Debugroutinen](../c-runtime-library/debug-routines.md)<br/>
