---
title: C-Laufzeitfehler R6019
ms.date: 11/04/2016
f1_keywords:
- R6019
helpviewer_keywords:
- R6019
ms.assetid: 8129923e-7db2-40ee-9602-def9365f8d28
ms.openlocfilehash: 93d340b2a12a00420a9003429251387b2f04ad37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62214098"
---
# <a name="c-runtime-error-r6019"></a>C-Laufzeitfehler R6019

Konsole Gerät kann nicht geöffnet

> [!NOTE]
> Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da versucht wurde, Zugriff auf die Konsole, aber es nicht über ausreichende Berechtigungen verfügen. Es gibt mehrere mögliche Gründe für diesen Fehler, aber dies ist normalerweise, weil das Programm als Administrator ausgeführt werden muss oder ein Fehler im Programm vorhanden ist.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Führen Sie das Programm als Administrator an.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> - Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Dieser Fehler tritt auf, da die app eine der hat, das Betriebssystem hat jedoch Zugriff auf die Konsole. Mit Ausnahme von sind im Debugmodus, Konsolenfunktionen in der Regel nicht in Microsoft Store-apps zulässig. Wenn Ihre app Administratorrechte ausführen erfordert, stellen Sie sicher, dass er standardmäßig als Administrator ausführen installiert ist.