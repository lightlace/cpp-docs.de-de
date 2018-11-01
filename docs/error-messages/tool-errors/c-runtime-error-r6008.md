---
title: C-Laufzeitfehler R6008
ms.date: 11/04/2016
f1_keywords:
- R6008
helpviewer_keywords:
- R6008
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
ms.openlocfilehash: 60e6475a84d2662ad3718e04dba879dc06afeee7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441898"
---
# <a name="c-runtime-error-r6008"></a>C-Laufzeitfehler R6008

nicht genügend Speicherplatz für Argumente

> [!NOTE]
> Wenn diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da sie ein Problem des internen Speicher verfügt. Es gibt mehrere mögliche Gründe für diesen Fehler, aber dies wird häufig durch eine extrem wenig Arbeitsspeicher verfügbar, zu viel Arbeitsspeicher, die von der Umgebungsvariablen oder eines Fehlers im Programm verursacht.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Anderen ausgeführten Anwendungen zu schließen, oder Neustart des Computers, um Arbeitsspeicher freizugeben.
> - Reduzieren Sie die Anzahl und Größe der Befehlszeilenargumente an die app ein.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> - Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Es war zwar genügend Arbeitsspeicher zum Laden des Programms jedoch nicht genügend Arbeitsspeicher zum Erstellen der **Argv** Array. Dies kann durch extrem wenig Arbeitsspeicher oder durch ungewöhnlich große Befehlszeilen oder die Variable Auslastung Umgebung verursacht werden. Erwägen Sie eine der folgenden Lösungen:

- Erhöhen Sie die Menge an Arbeitsspeicher für die Anwendung verfügbar.

- Reduzieren Sie die Anzahl und Größe der Befehlszeilenargumente.

- Verringern Sie die Größe der Umgebung, indem unnötige Variablen entfernen.