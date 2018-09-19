---
title: Festlegen der Position und Größe eines Dialogfelds (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], size
- dialog boxes [C++], positioning
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 854e4df84bfc5f75eda8f98fa117c199ba054b3a
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316574"
---
# <a name="specifying-the-location-and-size-of-a-dialog-box-c"></a>Festlegen der Position und Größe eines Dialogfelds (C++)

Die Position und Größe des Dialogfeld C++ als auch die Position und Größe von Steuerelementen, werden in Dialogeinheiten gemessen. In der unteren rechten Ecke der Visual Studio Statusleiste an, wenn Sie sie auswählen, werden die Werte für einzelne Steuerelemente und das Dialogfeld angezeigt.

Es gibt drei Eigenschaften, die Sie, in festlegen können der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) angeben, in dem ein Dialogfeld, das auf dem Bildschirm angezeigt wird. Die **Center** Eigenschaft boolescher Wert; ist, wenn Sie den Wert auf **"true"**, das Dialogfeld wird immer in der Mitte des Bildschirms angezeigt. Wenn Sie die Einstellung **"false"**, Sie können dann Festlegen der **XPos** und **YPos** Eigenschaften explizit definieren, auf dem Bildschirm, das Dialogfeld wird angezeigt. Die Positionseigenschaften sind von Offsetwerten aus der linken oberen Ecke des Anzeigebereichs, die folgendermaßen definiert ist `{X=0, Y=0}`. Die Position basiert ebenfalls auf die **Absolute Ausrichtung** Eigenschaft: Wenn **"true"**, die Koordinaten sind relativ zum Bildschirm; Wenn **"false"**, die Koordinaten sind relativ zu das Dialogfeld " Fenster des Besitzers.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)  
[Steuerelemente](../mfc/controls-mfc.md)