---
title: "Festlegen der Position und Größe eines Dialogfelds | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, size
- dialog boxes, positioning
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 03c4c6d6afb13a0e4ed8801838356ff0d1e851f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-the-location-and-size-of-a-dialog-box"></a>Festlegen der Position und Größe eines Dialogfelds
Der Speicherort und ein Dialogfeld, als auch die Position und Größe von Steuerelementen in ihr werden in Dialogeinheiten gemessen. In der unteren rechten Ecke der Visual Studio-Statusleiste angezeigt, wenn Sie sie auswählen, werden die Werte für einzelne Steuerelemente und das Dialogfeld angezeigt.  
  
 Es gibt drei Eigenschaften, die Sie, in festlegen können der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) angeben, wo ein Dialogfeld auf dem Bildschirm angezeigt wird. Die Eigenschaft zentriert ist boolescher Wert; Wenn Sie den Wert auf "true" festlegen, wird das Dialogfeld immer in der Mitte des Bildschirms angezeigt. Wenn sie auf "false" festgelegt wird, können Sie dann die XPos und YPos Eigenschaften explizit definieren, auf dem Bildschirm, erscheint das Dialogfeld festlegen. Die Positionseigenschaften sind Offsetwerte aus der linken oberen Ecke des Ansichtsbereichs, der als {X = 0, Y = 0} definiert ist. Die Position basiert auch auf die **Absolute Ausrichtung** Eigenschaft: bei "true", die Koordinaten sind relativ zu dem Bildschirm; Wenn "false", die Koordinaten sind relativ zu dem Dialogfeld Besitzerfenster.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

