---
title: C-Laufzeitfehler R6024 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6024
dev_langs:
- C++
helpviewer_keywords:
- R6024
ms.assetid: 0fb11c0f-9b81-4cab-81bd-4785742946a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: df874ae68f786585e85a8bc1b01ea8d0ac831d87
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861290"
---
# <a name="c-runtime-error-r6024"></a>C-Laufzeitfehler R6024

nicht genügend Speicherplatz für die Tabelle der _onexit/von "atexit"

> [!NOTE]
> Wenn diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da sie ein Problem des internen Speicher verfügt. Dieser Fehler wird normalerweise verursacht, durch eine Bedingung für extrem wenig Arbeitsspeicher oder nur selten, durch einen Fehler im Programm oder eine Beschädigung der Visual C++-Bibliotheken, die verwendet werden.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Anderen ausgeführten Anwendungen zu schließen, oder Neustart des Computers, um Arbeitsspeicher freizugeben.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder alle Kopien von Microsoft Visual C++ Redistributable zu installieren.
> - Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Dieser Fehler tritt auf, da nicht genügend Arbeitsspeicher verfügbar für war die `_onexit` oder `atexit` Funktion. Dieser Fehler wird durch einen Arbeitsspeichermangel verursacht. Sie können erwägen, vorab zuweisen von Puffern, die beim Starten der app, speichert Benutzerdaten und Durchführen einer sauberen app erleichtern in Speichermangel beendet.