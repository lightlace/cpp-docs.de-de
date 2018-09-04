---
title: C-Laufzeitfehler R6025 | Microsoft-Dokumentation
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
ms.openlocfilehash: 1055d60d95292d3585bccf64c56962d62d4ea48e
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680554"
---
# <a name="c-runtime-error-r6025"></a>C-Laufzeitfehler R6025
rein virtuellen Funktionsaufruf  
  
> [!NOTE]
>  Wenn Sie diese Fehlermeldung beim Ausführen einer app auftritt, wurde die app beendet, da er ein internes Problem aufweist. Die häufigste Ursache für diesen Fehler ist ein Fehler in der app oder eine beschädigte Installation.  
>   
>  Sie können versuchen, diesen Fehler zu beheben, indem Sie folgende Schritte ausführen:  
>   
>  -   Verwenden der **Apps und Features** oder **Programme und Funktionen** auf der Seite die **Systemsteuerung** zu reparieren oder installieren Sie das Programm neu.  
> -   Überprüfen Sie **Windows Update** in die **Systemsteuerung** für Softwareupdates.  
> -   Überprüfen Sie nach einer aktualisierten Version der app. Wenn das Problem weiterhin besteht, wenden Sie sich an den app-Anbieter.  
  
 **Informationen für Programmierer**  
  
 Kein Objekt ist instanziiert wurde, um die rein virtuellen Funktionsaufruf zu behandeln.  
  
 Dieser Fehler wird verursacht durch eine virtuelle Funktion in einer abstrakten Klasse über einen Zeiger auf die wird durch eine Umwandlung in den Typ der abgeleiteten Klasse erstellt, jedoch ist eigentlich ein Zeiger auf die Basisklasse aufrufen. Dies kann auftreten, bei der Umwandlung von einer **"void"** <strong>\*</strong> in einen Zeiger auf eine Klasse bei der **"void"** <strong>\*</strong> wurde während der Erstellung der Basisklasse erstellt.  
  
