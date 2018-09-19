---
title: C-Laufzeitfehler R6033 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6033
dev_langs:
- C++
helpviewer_keywords:
- R6033
ms.assetid: f9cffdc9-81bd-4a64-a698-02762cbd82c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb107dcd2bd044ad6fb933869319bb7afd5aab72
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049799"
---
# <a name="c-runtime-error-r6033"></a>C-Laufzeitfehler R6033

Versucht, MSIL-Code aus dieser Assembly während der Initialisierung von nativem Code zu verwenden. Dies gibt einen Fehler in Ihrer Anwendung an. Es ist wahrscheinlich das Ergebnis des Aufrufs einer MSIL-kompiliert (/ Clr)-Funktion von einem einheitlichen Konstruktor oder aus DllMain.

> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da er ein internes Problem aufweist. Dieser Fehler kann verursacht werden, indem Sie einen Fehler in der app oder eines Fehlers in einer Add-in oder die Erweiterung, die verwendet.
>
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:
>
>  -   Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.
> -   Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** entfernen, reparieren oder installieren Sie alle Erweiterungen oder -add-ins.
> -   Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.

**Informationen für Programmierer**

Diese Diagnose gibt an, dass die MSIL-Anweisungen ausgeführt wurden, während die Loadersperre aufgehoben. Dies kann auftreten, wenn Sie systemeigenes C++ mit dem Flag "/ CLR" kompiliert haben. Verwenden Sie nur das Flag "/ CLR", auf die Module, die verwalteten Code enthalten. Weitere Informationen finden Sie unter [Initialization of Mixed Assemblies](../../dotnet/initialization-of-mixed-assemblies.md).