---
title: Fehlerhooks
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
ms.openlocfilehash: 2fc22ae77d729868adbf8c37d40e450e35a8e866
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811991"
---
# <a name="failure-hooks"></a>Fehlerhooks

Der Fehlerhook aktiviert ist, auf die gleiche Weise wie die [Benachrichtigungshook](notification-hooks.md). Der Hook routinemäßige muss einen geeigneten Wert zurück, sodass die Verarbeitung können weiterhin (HINSTANCE oder FARPROC) oder 0, um anzugeben, dass eine Ausnahme ausgelöst werden soll.

Die Zeigervariable, die auf die benutzerdefinierte Funktion verweist ist:

```
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

Die **DelayLoadInfo** Struktur enthält alle relevanten Daten, die erforderlich ist, für die korrekte Meldung des Fehlers, einschließlich des Wertes von `GetLastError`.

Wenn die Benachrichtigung ist **DliFailLoadLib**, kann die Hookfunktion zurückgeben:

- 0, wenn den Fehler nicht verarbeitet werden können.

- Ein HMODULE, wenn der Fehlerhook wurde das Problem behoben und die Bibliothek geladen.

Wenn die Benachrichtigung ist **DliFailGetProc**, kann die Hookfunktion zurückgeben:

- 0, wenn den Fehler nicht verarbeitet werden können.

- Eine gültige Proc (Adresse Import-Funktion), erfolgreich Wenn der Fehler einzubinden beim Abrufen der Adresse selbst.

## <a name="see-also"></a>Siehe auch

[Fehlerbehandlung und Benachrichtigung](error-handling-and-notification.md)
