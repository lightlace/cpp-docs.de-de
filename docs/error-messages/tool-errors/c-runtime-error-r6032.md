---
title: C-Laufzeitfehler R6032 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6032
dev_langs:
- C++
helpviewer_keywords:
- R6032
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43155f24411fb5206a03d607f0551c2d34294aeb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024202"
---
# <a name="c-runtime-error-r6032"></a>C-Laufzeitfehler R6032

Nicht genügend Speicherplatz für Gebietsschema-Informationen

> [!NOTE]
>  Wenn diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da sie ein Problem des internen Speicher verfügt. Es gibt mehrere mögliche Gründe für diesen Fehler, aber dies wird häufig verursacht durch eine extrem wenig Arbeitsspeicher verfügbar oder durch einen Fehler im Programm.
>
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
>  -   Anderen ausgeführten Anwendungen zu schließen, oder Neustart des Computers, um Arbeitsspeicher freizugeben.
> -   Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> -   Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Die Common Language Runtime verwaltet Informationen über das Gebietsschema für jeden Thread, sodass sie Aufrufe von gebietsschemaabhängigen Funktionen verarbeiten kann. Wenn die Zuordnung des Arbeitsspeichers für diese Informationen fehlschlägt, ist die Runtime kann nicht fortgesetzt werden, weil zu viele der grundlegenden Funktionen, die davon abhängen.