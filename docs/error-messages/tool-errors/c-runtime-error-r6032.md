---
title: C-Laufzeitfehler R6032
ms.date: 11/04/2016
f1_keywords:
- R6032
helpviewer_keywords:
- R6032
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
ms.openlocfilehash: e0ae3acc491658840d74e262f3ab2719e613d60e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399992"
---
# <a name="c-runtime-error-r6032"></a>C-Laufzeitfehler R6032

Nicht genügend Speicherplatz für Gebietsschema-Informationen

> [!NOTE]
> Wenn diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da sie ein Problem des internen Speicher verfügt. Es gibt mehrere mögliche Gründe für diesen Fehler, aber dies wird häufig verursacht durch eine extrem wenig Arbeitsspeicher verfügbar oder durch einen Fehler im Programm.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Anderen ausgeführten Anwendungen zu schließen, oder Neustart des Computers, um Arbeitsspeicher freizugeben.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> - Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Die Common Language Runtime verwaltet Informationen über das Gebietsschema für jeden Thread, sodass sie Aufrufe von gebietsschemaabhängigen Funktionen verarbeiten kann. Wenn die Zuordnung des Arbeitsspeichers für diese Informationen fehlschlägt, ist die Runtime kann nicht fortgesetzt werden, weil zu viele der grundlegenden Funktionen, die davon abhängen.