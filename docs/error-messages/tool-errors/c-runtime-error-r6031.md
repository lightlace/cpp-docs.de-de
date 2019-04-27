---
title: C-Laufzeitfehler R6031
ms.date: 11/04/2016
f1_keywords:
- R6031
helpviewer_keywords:
- R6031
ms.assetid: 805d4cd1-cb2f-43fe-87e6-e7bd5b7329c5
ms.openlocfilehash: 6ef3f5fa7d063fdc300e6ac28ca519992525851c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242681"
---
# <a name="c-runtime-error-r6031"></a>C-Laufzeitfehler R6031

Es wurde versucht die CRT mehr als einmal initialisiert werden. Dies gibt einen Fehler in Ihrer Anwendung an.

> [!NOTE]
> Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da er ein internes Problem aufweist. Mögliche Ursachen sind Fehler in der app oder durch einen Fehler in einem Add-on oder die Erweiterung, die die app verwendet.
>
> Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> - Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** reparieren oder von der Anwendung verwendeten Programme Add-On- oder Erweiterung neu installieren, um zu entfernen.
> - Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> - Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Diese Diagnose gibt an, dass die MSIL-Anweisungen ausgeführt wurden, während die Loadersperre aufgehoben. Weitere Informationen finden Sie unter [Initialization of Mixed Assemblies](../../dotnet/initialization-of-mixed-assemblies.md).