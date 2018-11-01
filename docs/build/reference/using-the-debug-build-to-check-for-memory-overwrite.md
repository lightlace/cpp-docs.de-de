---
title: Verwenden des Debugbuilds zur Suche nach Speicherüberschreibungen
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
ms.openlocfilehash: 4983d64f7d783c5f23643a046780fb5fa4ba4565
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623729"
---
# <a name="using-the-debug-build-to-check-for-memory-overwrite"></a>Verwenden des Debugbuilds zur Suche nach Speicherüberschreibungen

Um den Debugbuild verwenden, um nach speicherüberschreibungen überprüfen, müssen Sie zuerst Ihr Projekt für das Debuggen neu erstellen. Wechseln Sie dann den Anfang der Anwendung `InitInstance` Funktion, und fügen Sie die folgende Zeile hinzu:

```
afxMemDF |= checkAlwaysMemDF;
```

Die Debug-Speicherreservierungsfunktion setzt umgibt aller speicherbelegungen. Allerdings schützen diese Bytes nicht gut, es sei denn, Sie überprüfen, ob sie geändert wurden (die auf eine speicherüberschreibungen hinweisen würden). Andernfalls können Sie dies nur über einen Puffer bereitstellt, der in der Tat kann sofort mit einem speicherüberschreibungen erhalten.

Durch Aktivieren der `checkAlwaysMemDF`, Sie erzwingen, dass MFC ermöglicht, einen Aufruf an die `AfxCheckMemory` Funktion jedes Mal einen Aufruf von **neue** oder **löschen** erfolgt. Wenn eine speicherüberschreibungen erkannt wurde, generiert er eine Ablaufverfolgungsmeldung, die in etwa wie folgt aussieht:

```
Damage Occurred! Block=0x5533
```

Wenn Sie eine der folgenden Meldungen angezeigt wird, müssen Sie schrittweise Ihren Code, um zu bestimmen, wo die Beschädigung aufgetreten ist. Um zu isolieren, genauer gesagt, in der speicherüberschreibungen aufgetreten ist, können Sie explizite Aufrufe vornehmen `AfxCheckMemory` selbst. Zum Beispiel:

```
ASSERT(AfxCheckMemory());
    DoABunchOfStuff();
    ASSERT(AfxCheckMemory());
```

Wenn die erste Bestätigung ist erfolgreich, und das zweite Argument ein Fehler auftritt, bedeutet dies, dass die speicherüberschreibungen in der Funktion zwischen den beiden aufrufen aufgetreten sind, muss.

Je nach Art der Anwendung, erweist sich `afxMemDF` bewirkt, dass das Programm zu langsam ausgeführt wird, um selbst zu testen. Die `afxMemDF` dazu führt, dass `AfxCheckMemory` für jeden Aufruf von neuen aufgerufen werden, und löschen. In diesem Fall sollten Sie Ihre eigenen Aufrufe für Punktdiagramme `AfxCheckMemory`(), wie oben gezeigt, und wiederholen Sie den Arbeitsspeicher zu isolieren, überschreiben Sie auf diese Weise.

## <a name="see-also"></a>Siehe auch

[Beheben von Problemen mit dem Releasebuild](../../build/reference/fixing-release-build-problems.md)