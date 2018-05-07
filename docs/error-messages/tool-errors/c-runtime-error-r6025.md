---
title: C-Laufzeitfehler R6025 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- R6025
dev_langs:
- C++
helpviewer_keywords:
- R6025
ms.assetid: afa06d98-9c36-445b-b3e7-b6409bc8e779
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abdbdbf918462dfb83eff07190c32af1f1b3d015
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="c-runtime-error-r6025"></a>C-Laufzeitfehler R6025
rein virtuellen Funktionsaufruf  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app heruntergefahren, da es sich um ein internes Problem enthält. Die häufigste Ursache für diesen Fehler ist ein Fehler in der Anwendung oder eine beschädigte Installation.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Verwenden der **Apps und Funktionen** oder **Programme und Funktionen** auf der Seite der **Systemsteuerung** reparieren oder neu installieren die Anwendung.  
> -   Überprüfen Sie **Windows Update** in der **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den Hersteller der app.  
  
 **Informationen für Programmierer**  
  
 Kein Objekt wurde instanziiert, um die rein virtuellen Funktionsaufruf zu behandeln.  
  
 Dieser Fehler wird verursacht, durch den Aufruf einer virtuellen Funktion in einer abstrakten Klasse über einen Zeiger, die durch eine Umwandlung in den Typ der abgeleiteten Klasse erstellt wird, sondern ist tatsächlich ein Zeiger auf die Basisklasse der Klasse. Dies kann auftreten, wenn die Umwandlung von einer **"void"\***  in einen Zeiger auf eine Klasse bei der **"void"\***  während der Erstellung der Basisklasse erstellt wurde.  
  
 Weitere Informationen finden Sie unter der [Microsoft-Support](http://go.microsoft.com/fwlink/p/?linkid=75220) Website.