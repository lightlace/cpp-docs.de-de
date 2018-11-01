---
title: Fehlerhooks
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
ms.openlocfilehash: 2bda1d34c85b1e88c7d278816e30e76537a7523b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463609"
---
# <a name="failure-hooks"></a>Fehlerhooks

Der Fehlerhook aktiviert ist, auf die gleiche Weise wie die [Benachrichtigungshook](../../build/reference/notification-hooks.md). Der Hook routinemäßige muss einen geeigneten Wert zurück, sodass die Verarbeitung können weiterhin (HINSTANCE oder FARPROC) oder 0, um anzugeben, dass eine Ausnahme ausgelöst werden soll.

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

[Fehlerbehandlung und Benachrichtigung](../../build/reference/error-handling-and-notification.md)