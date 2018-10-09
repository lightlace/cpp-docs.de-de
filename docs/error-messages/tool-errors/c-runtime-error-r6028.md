---
title: C-Laufzeitfehler R6028 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6028
dev_langs:
- C++
helpviewer_keywords:
- R6028
ms.assetid: 81e99079-4388-4244-a4f7-4641c508871c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dbcc1f34fced7a7ea752d8733662f7510a01aad5
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860549"
---
# <a name="c-runtime-error-r6028"></a>C-Laufzeitfehler R6028

Heap kann nicht initialisiert werden.

> [!NOTE]
> Wenn diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da sie ein Problem des internen Speicher verfügt. Es gibt viele mögliche Ursachen für diesen Fehler, aber dies wird häufig verursacht durch eine extrem wenig Arbeitsspeicher verfügbar, einen Fehler im Programm oder defekte Hardware-Treiber.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Anderen ausgeführten Anwendungen zu schließen, oder Neustart des Computers, um Arbeitsspeicher freizugeben.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> - Wenn die app vor einer kürzlich durchgeführten Installationen von einer anderen app oder Treiber ordnungsgemäß funktioniert, verwenden Sie die **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** Entfernen der neue app oder -Treiber verwenden, und versuchen Sie es erneut mit Ihrer app.
> - Überprüfen Sie die Hardware der Website des Herstellers oder **Windows Update** in die **Systemsteuerung** für Software-und Treiberupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Dieser Fehler tritt auf, wenn das Betriebssystem den Speicherpool für die Anwendung nicht erstellen konnte. Das heißt, CRT (C Runtime) hat die Win32-Funktion `HeapCreate` aufgerufen, die NULL zurückgibt und auf einen Fehler hinweist.

Wenn dieser Fehler während des Starts der App auftritt, kann das System die Heapanforderungen möglicherweise nicht erfüllen, da fehlerhafte Treiber geladen werden. Aktualisierte Treiber finden Sie unter Windows Update oder auf der Website des Hardwareherstellers.