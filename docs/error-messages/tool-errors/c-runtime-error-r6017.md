---
title: C-Laufzeitfehler R6017
ms.date: 11/04/2016
f1_keywords:
- R6017
helpviewer_keywords:
- R6017
ms.assetid: df3ec5f5-6771-4648-ba06-0e26c6a1cc6a
ms.openlocfilehash: 45f3b07f540cb72a955b19420130a5a806b750d7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "58774697"
---
# <a name="c-runtime-error-r6017"></a>C-Laufzeitfehler R6017

Fehler beim unerwarteten multithread-Sperren

> [!NOTE]
> Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da er ein internes Problem aufweist. Es gibt mehrere mögliche Gründe für diesen Fehler, aber dies wird häufig durch einen Fehler in der app-Code verursacht.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> - Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Der Prozess empfangen einen unerwarteten Fehler beim Versuch, eine C-Laufzeit multithread-Sperre auf eine Systemressource zugreifen. Dieser Fehler tritt gewöhnlich auf, wenn der Prozess der Common Language Runtime-Heap-Daten versehentlich geändert wird. Es kann jedoch auch durch einen internen Fehler in der Common Language Runtime-Bibliothek oder ein Betriebssystem-Code verursacht werden.

Um dieses Problem zu beheben, überprüfen Sie die Heap-Beschädigung Fehlern im Code. Weitere Informationen und Beispiele finden Sie unter [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details). Als Nächstes überprüfen Sie, dass Sie die neuesten verteilbaren Dateien für Ihre app-Bereitstellung verwenden. Weitere Informationen finden Sie unter [Bereitstellung in Visual C++](../../windows/deployment-in-visual-cpp.md).