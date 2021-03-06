---
title: C-Laufzeitfehler R6009
ms.date: 11/04/2016
f1_keywords:
- R6009
helpviewer_keywords:
- R6009
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
ms.openlocfilehash: 5e1914d5d2f665609cfc24c2db3dc8a123d7e83f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299750"
---
# <a name="c-runtime-error-r6009"></a>C-Laufzeitfehler R6009

nicht genügend Speicherplatz für die Umgebung

> [!NOTE]
> Wenn diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da sie ein Problem des internen Speicher verfügt. Es gibt mehrere mögliche Gründe für diesen Fehler, aber dies wird häufig durch eine extrem wenig Arbeitsspeicher verfügbar, zu viel Arbeitsspeicher, die von der Umgebungsvariablen oder eines Fehlers im Programm verursacht.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Anderen ausgeführten Anwendungen zu schließen, oder Neustart des Computers, um Arbeitsspeicher freizugeben.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> - Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Gab es genügend Arbeitsspeicher zum Laden des Programms, jedoch nicht genügend Arbeitsspeicher zum Erstellen der **Envp** Array.  Dies kann äußerst wenig Arbeitsspeicher oder Variablenverwendung ungewöhnlich großen Umgebung verursacht werden. Erwägen Sie eine der folgenden Lösungen:

- Erhöhen Sie die Menge an Arbeitsspeicher für die Anwendung verfügbar.

- Reduzieren Sie die Anzahl und Größe der Befehlszeilenargumente.

- Verringern Sie die Größe der Umgebung, indem unnötige Variablen entfernen.