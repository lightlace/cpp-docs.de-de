---
title: C-Laufzeitfehler R6033 | Microsoft Docs
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
ms.openlocfilehash: ed66dec4f4eb17378c9901439be2ad1449597a93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299993"
---
# <a name="c-runtime-error-r6033"></a>C-Laufzeitfehler R6033
Versucht, MSIL-Code aus dieser Assembly während der Initialisierung von systemeigenem Code zu verwenden. Hiermit wird einen Fehler in der Anwendung. Es ist sehr wahrscheinlich das Ergebnis des Aufrufs einer MSIL-kompilierten (/ Clr)-Funktion aus einem systemeigenen Konstruktor oder aus DllMain.  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da es sich um ein internes Problem enthält. Dieser Fehler kann verursacht werden, von einem Fehler in der app oder durch einen Bug in einer Add-in oder eine Erweiterung, die verwendet werden.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** entfernen, reparieren oder neu installieren, alle Erweiterungen oder -add-ins.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Diese Diagnose gibt an, dass MSIL-Anweisungen während der Loadersperre ausgeführt wurden. Dies kann auftreten, wenn Sie systemeigener C++-Code mithilfe des Flags "/ CLR" kompiliert haben. Verwenden Sie nur das Flag "/ CLR" auf Module mit verwaltetem Code an. Weitere Informationen finden Sie unter [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md).