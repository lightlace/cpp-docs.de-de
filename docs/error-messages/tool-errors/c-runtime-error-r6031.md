---
title: C-Laufzeitfehler R6031 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6031
dev_langs:
- C++
helpviewer_keywords:
- R6031
ms.assetid: 805d4cd1-cb2f-43fe-87e6-e7bd5b7329c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66d75fb0095b1de0fe1572d8c946823a89791740
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33303945"
---
# <a name="c-runtime-error-r6031"></a>C-Laufzeitfehler R6031
Es wurde versucht mehr als einmal die CRT initialisiert werden. Hiermit wird einen Fehler in der Anwendung.  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da es sich um ein internes Problem enthält. Dies kann verursacht werden Fehler in der app oder von einem Fehler in einem Add-on oder einer Erweiterung, die die app verwendet.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** um entfernen, reparieren oder Add-Ons oder einer Erweiterung von der Anwendung verwendeten Programme neu installieren.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Diese Diagnose gibt an, dass MSIL-Anweisungen während der Loadersperre ausgeführt wurden. Weitere Informationen finden Sie unter [Initialisierung gemischter Assemblys](../../dotnet/initialization-of-mixed-assemblies.md).