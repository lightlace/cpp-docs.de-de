---
title: C-Laufzeitfehler R6008 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6008
dev_langs:
- C++
helpviewer_keywords:
- R6008
ms.assetid: f0f304fc-709a-4843-bc7e-bad1ae0d1649
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39b06566f84003b08f5fe3869a021c4bf86dcf5f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105128"
---
# <a name="c-runtime-error-r6008"></a>C-Laufzeitfehler R6008

nicht genügend Speicherplatz für Argumente

> [!NOTE]
>  Wenn diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da sie ein Problem des internen Speicher verfügt. Es gibt mehrere mögliche Gründe für diesen Fehler, aber dies wird häufig durch eine extrem wenig Arbeitsspeicher verfügbar, zu viel Arbeitsspeicher, die von der Umgebungsvariablen oder eines Fehlers im Programm verursacht.
>
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
>  -   Anderen ausgeführten Anwendungen zu schließen, oder Neustart des Computers, um Arbeitsspeicher freizugeben.
> -   Reduzieren Sie die Anzahl und Größe der Befehlszeilenargumente an die app ein.
> -   Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> -   Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Es war zwar genügend Arbeitsspeicher zum Laden des Programms jedoch nicht genügend Arbeitsspeicher zum Erstellen der **Argv** Array. Dies kann durch extrem wenig Arbeitsspeicher oder durch ungewöhnlich große Befehlszeilen oder die Variable Auslastung Umgebung verursacht werden. Erwägen Sie eine der folgenden Lösungen:

- Erhöhen Sie die Menge an Arbeitsspeicher für die Anwendung verfügbar.

- Reduzieren Sie die Anzahl und Größe der Befehlszeilenargumente.

- Verringern Sie die Größe der Umgebung, indem unnötige Variablen entfernen.