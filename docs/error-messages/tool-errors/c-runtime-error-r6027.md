---
title: C-Laufzeitfehler R6027
ms.date: 11/04/2016
f1_keywords:
- R6027
helpviewer_keywords:
- R6027
ms.assetid: c06a62b3-08d9-4bf5-bcad-8340ec552f69
ms.openlocfilehash: 2884f148091d9407d3229f0690a161639b5195e1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395143"
---
# <a name="c-runtime-error-r6027"></a>C-Laufzeitfehler R6027

nicht genügend Speicherplatz für Lowio-Initialisierung.

> [!NOTE]
> Wenn diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da sie ein Problem des internen Speicher verfügt. Es gibt mehrere mögliche Gründe für diesen Fehler, aber dies wird normalerweise verursacht durch eine extrem wenig Arbeitsspeicher verfügbar. Es kann auch durch einen Fehler in der app, eine Beschädigung der Visual C++-Bibliotheken, die verwendet oder von einem Treiber verursacht werden.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Anderen ausgeführten Anwendungen zu schließen, oder Neustart des Computers, um Arbeitsspeicher freizugeben.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> - Wenn die app vor einer kürzlich durchgeführten Installationen von einer anderen app oder Treiber ordnungsgemäß funktioniert, verwenden Sie die **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** Entfernen der neue app oder -Treiber verwenden, und versuchen Sie es erneut mit Ihrer app.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder alle Kopien von Microsoft Visual C++ Redistributable zu installieren.
> - Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Dieser Fehler tritt auf, wenn nicht genügend freier Arbeitsspeicher zur Verfügung, um die Low-Level e/a-Unterstützung in der C-Laufzeit zu initialisieren. Dieser Fehler tritt gewöhnlich beim Starten der app. Stellen Sie sicher, dass Ihre app und die Treiber und -Dlls, die es lädt den Heap beim Start nicht beschädigt.