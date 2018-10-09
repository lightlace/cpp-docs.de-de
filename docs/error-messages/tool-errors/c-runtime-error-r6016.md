---
title: C-Laufzeitfehler R6016 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6016
dev_langs:
- C++
helpviewer_keywords:
- R6016
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b14d6e20f58ef5a9fbda6d640f5c8a596635d70c
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861706"
---
# <a name="c-runtime-error-r6016"></a>C-Laufzeitfehler R6016

Nicht genügend Speicher für Threaddaten

> [!NOTE]
> Wenn diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da sie ein Problem des internen Speicher verfügt. Es gibt viele mögliche Ursachen für diesen Fehler, aber dies wird häufig verursacht durch eine extrem wenig Arbeitsspeicher verfügbar, einen Fehler in der app oder durch einen Fehler in einer Add-in oder die Erweiterung, die von der app verwendet.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Anderen ausgeführten Anwendungen zu schließen, oder Neustart des Computers, um Arbeitsspeicher freizugeben.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie die app neu.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** entfernen, reparieren oder neu installieren, add-ins oder Erweiterungen, die von der app verwendet.
> - Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Dieser Fehler tritt auf, weil die Anwendung nicht genügend Arbeitsspeicher vom Betriebssystem ausführen erhalten hat eine [_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md) oder `_beginthreadex` Aufruf oder Thread wurde nicht vom lokaler Speicher initialisiert `_beginthread` oder `_beginthreadex`.

Beim Start eines neuen Threads muss die Bibliothek für diesen eine interne Datenbank anlegen. Wenn der vom Betriebssystem bereitgestellte Speicher nicht zum Erweitern dieser Datenbank ausreicht, wird der Thread nicht gestartet, und der Aufrufprozess wird angehalten. Das kann vorkommen, wenn durch den Prozess zu viele Threads erstellt wurden oder der threadlokale Speicher ausgeschöpft ist.

Es wird empfohlen, eine ausführbare Datei, die die C-Laufzeitbibliothek (CRT) aufruft, zu verwendende `_beginthreadex` zur Threaderstellung und nicht die Windows-API `CreateThread`. `_beginthreadex` initialisiert den internen statischen Speicher, der von vielen CRT-Funktionen im lokalen Threadspeicher verwendet wird. Wenn Sie zur Erstellung eines Threads die `CreateThread`-Funktion verwenden, beendet das CRT den Prozess beim Aufruf einer CRT-Funktion, die initialisierten internen statischen Speicher benötigt, möglicherweise mit R6016.