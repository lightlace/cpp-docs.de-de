---
title: Ändern der Steuerelementgröße beim Hinzufügen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog box controls [C++], size
- controls [C++], sizing
ms.assetid: 06b1dd2b-0ba1-4e1f-adc3-cb73679f765e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da998c748a3471f053c922e0a80c33d1526b2055
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313142"
---
# <a name="sizing-a-control-while-you-add-it"></a>Ändern der Steuerelementgröße beim Hinzufügen

### <a name="to-size-a-control-while-you-add-it"></a>Die Größe eines Steuerelements, beim Hinzufügen

1. Wählen Sie ein Steuerelement in der [Fenster "Toolbox"](/visualstudio/ide/reference/toolbox).

2. Platzieren Sie den Cursor (die Form eines Fadenkreuzes angezeigt), möchten Sie die linke obere Ecke des neuen Steuerelements auf das Dialogfeld.

3. Halten Sie die Maustaste gedrückt, verankern Sie die linke obere Ecke des Steuerelements im Dialogfeld klicken und ziehen Sie den Cursor nach rechts und nach unten, bis die gewünschte Größe hat.

   > [!NOTE]
   > Sie können tatsächlich eine der vier Ecken des Steuerelements verankern, die Sie zeichnen können. Dieses Verfahren verwendet die oberen linken Ecke als Beispiel.

4. Lassen Sie die Maustaste los. Das Steuerelement ist in der angegebenen Größe im Dialogfeld angelegt.

   > [!TIP]
   > Sie können die Größe des Steuerelements nach dem Ablegen im Dialogfeld durch das Verschieben der Ziehpunkte am Rand des Steuerelements. Weitere Informationen finden Sie unter [Festlegen der Größe der einzelnen Steuerelementen](../windows/sizing-individual-controls.md).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)  
[Hinzufügen von Ereignishandlern für Dialogfeld-Steuerelemente](../windows/adding-event-handlers-for-dialog-box-controls.md)  
[Dialogfeld-Steuerelemente und Variablentypen](../ide/dialog-box-controls-and-variable-types.md)