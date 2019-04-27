---
title: C-Laufzeitfehler R6026
ms.date: 11/04/2016
f1_keywords:
- R6026
helpviewer_keywords:
- R6026
ms.assetid: 7ea751f8-fc20-46ab-99ef-84c95ca0b6b4
ms.openlocfilehash: 28e541b61b6381cd283578a0ce1909e5b39a4a53
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151915"
---
# <a name="c-runtime-error-r6026"></a>C-Laufzeitfehler R6026

nicht genügend Speicherplatz für die Stdio-Initialisierung

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

Dieser Fehler tritt auf, wenn nicht genügend Arbeitsspeicher zur Verfügung, um die standard-e/a--Unterstützung in der C-Laufzeit zu initialisieren. Dieser Fehler tritt gewöhnlich beim Starten der app. Stellen Sie sicher, dass Ihre app und die Treiber und -Dlls, die es lädt den Heap beim Start nicht beschädigt.