---
title: C-Laufzeitfehler R6009 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6009
dev_langs:
- C++
helpviewer_keywords:
- R6009
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42a5aed9f823b5d2c5425c4d7baae129c08e76e7
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860926"
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