---
title: Benachrichtigungshooks | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, notification hooks
ms.assetid: e9c291ed-2f2d-4319-a171-09800625256f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97e471e2de1ecb6ec6664658a2f1c5df09bc8079
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700621"
---
# <a name="notification-hooks"></a>Benachrichtigungshooks

Die Benachrichtigungshooks werden aufgerufen, kurz bevor die folgenden Aktionen, in die Hilfsroutine hat ausgeführt werden:

- Das gespeicherte Handle in die Bibliothek wird überprüft, um festzustellen, ob sie bereits geladen wurde.

- **LoadLibrary** wird aufgerufen, um die DLL zu laden.

- **GetProcAddress** aufgerufen, um zu versuchen, die die Adresse der Prozedur abzurufen.

- Zurück zum Thunk Verzögerung importieren.

Der Benachrichtigungshook ist aktiviert:

- Durch Bereitstellen einer neuen Definition des Zeigers **__pfnDliNotifyHook2** , um auf Ihre eigene Funktion zu verweisen die Benachrichtigungen empfangenden initialisiert.

   \-oder:

- Durch Festlegen des Zeigers **__pfnDliNotifyHook2** auf die Hookfunktion, bevor Aufrufe an die DLL, die das Programm ist laden verzögern.

Wenn die Benachrichtigung ist **DliStartProcessing**, kann die Hookfunktion zurückgeben:

- NULL

   Hilfsfunktion übernimmt das Laden der DLL. Dies ist hilfreich, die nur zu Informationszwecken aufgerufen werden.

- Funktionszeiger

   Umgehen Sie die Standardbehandlung für das verzögerte Laden an. Dadurch können Sie Ihren eigenen Handler laden angeben.

Wenn die Benachrichtigung ist **DliNotePreLoadLibrary**, kann die Hookfunktion zurückgeben:

- 0, wenn er nur zu Informationszwecken Benachrichtigungen will.

- Das HMODULE für die geladenen DLL, wenn sie die DLL selbst geladen werden soll.

Wenn die Benachrichtigung ist **DliNotePreGetProcAddress**, kann die Hookfunktion zurückgeben:

- 0, wenn er nur zu Informationszwecken Benachrichtigungen will.

- Importiert die Adresse der Funktion, wenn die Hookfunktion die Adresse selbst abruft.

Wenn die Benachrichtigung ist **um DliNoteEndProcessing**, die Hookfunktion Rückgabewert wird ignoriert.

Wenn dieser Zeiger (ungleich null) initialisiert wird, wird die Hilfsfunktion für verzögertes Laden die Funktion während der Ausführung an bestimmten aufgerufen. Der Funktionszeiger weist folgende Definition:

```C
// The "notify hook" gets called for every call to the
// delay load helper.  This allows a user to hook every call and
// skip the delay load helper entirely.
//
// dliNotify == {
//  dliStartProcessing |
//  dliNotePreLoadLibrary  |
//  dliNotePreGetProc |
//  dliNoteEndProcessing}
//  on this call.
//
ExternC
PfnDliHook   __pfnDliNotifyHook2;

// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

Übergeben Sie die Benachrichtigungen ein **DelayLoadInfo** Struktur, die Hookfunktion sowie der benachrichtigungswert. Diese Daten sind identisch, die von der Hilfsfunktion für verzögertes Laden verwendet. Der benachrichtigungswert wird einer der Werte in definierten [Struktur- und Konstantendefinitionen](../../build/reference/structure-and-constant-definitions.md).

## <a name="see-also"></a>Siehe auch

[Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md)