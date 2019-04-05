---
title: C-Laufzeitfehler R6018
ms.date: 11/04/2016
f1_keywords:
- R6018
helpviewer_keywords:
- R6018
ms.assetid: f6dd40d1-a119-4d8b-b39e-97350ea23349
ms.openlocfilehash: b36e2184e5be131645fb4dd58a361fdb9a31da63
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58774973"
---
# <a name="c-runtime-error-r6018"></a>C-Laufzeitfehler R6018

unerwarteter Heapfehler

> [!NOTE]
> Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da er ein internes Problem aufweist. Es gibt mehrere mögliche Gründe für diesen Fehler, aber dies wird häufig durch einen Fehler in der app-Code verursacht.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> - Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Das Programm ist einen unerwarteter Fehler beim Ausführen eines Vorgangs für die Speicherverwaltung.

Dieser Fehler tritt gewöhnlich auf, wenn das Programm die Runtime-Heapdaten versehentlich geändert wird. Es kann jedoch auch durch einen internen Fehler in der Common Language Runtime oder ein Betriebssystem-Code verursacht werden.

Um dieses Problem zu beheben, überprüfen Sie die Heap-Beschädigung Fehlern im Code. Weitere Informationen und Beispiele finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Als Nächstes überprüfen Sie, dass Sie die neuesten verteilbaren Dateien für Ihre app-Bereitstellung verwenden. Weitere Informationen finden Sie unter [Bereitstellung in Visual C++](../../windows/deployment-in-visual-cpp.md).