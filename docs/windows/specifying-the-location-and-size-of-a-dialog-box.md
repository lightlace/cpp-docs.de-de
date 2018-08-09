---
title: Festlegen der Position und Größe eines Dialogfelds | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, size
- dialog boxes, positioning
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3a3a9a629ec138659a7b0d2aba2460aced31fc74
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649002"
---
# <a name="specifying-the-location-and-size-of-a-dialog-box"></a>Festlegen der Position und Größe eines Dialogfelds
Die Position und Größe des Dialogfeld als auch die Position und Größe von Steuerelementen, werden in Dialogeinheiten gemessen. In der unteren rechten Ecke der Visual Studio Statusleiste an, wenn Sie sie auswählen, werden die Werte für einzelne Steuerelemente und das Dialogfeld angezeigt.  
  
 Es gibt drei Eigenschaften, die Sie, in festlegen können der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) angeben, in dem ein Dialogfeld, das auf dem Bildschirm angezeigt wird. Die Center-Eigenschaft ist vom Typ. Wenn Sie den Wert auf "true" festlegen, wird das Dialogfeld immer in der Mitte des Bildschirms angezeigt. Wenn Sie es auf "false" festlegen, können Sie dann die XPos und YPos Eigenschaften explizit definieren, auf dem Bildschirm, erscheint das Dialogfeld festlegen. Die Positionseigenschaften sind Offsetwerten aus der linken oberen Ecke des Anzeigebereichs, die als {X = 0, Y = 0} definiert ist. Die Position basiert ebenfalls auf die **Absolute Ausrichtung** Eigenschaft: bei "true", die Koordinaten sind relativ zum Bildschirm; False gibt an, die Koordinaten sind relativ zum des Dialogfeldbesitzers-Fenster.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)