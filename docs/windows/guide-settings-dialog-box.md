---
title: Führen Sie die Einstellungen (Dialogfeld) (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLUs (dialog units)
- Dialog Editor [C++], snap to guides
- grid spacing
- guides, settings
- dialog units (DLUs)
- layout grid in Dialog Editor
- snap to guides (Dialog editor)
- controls [C++], snap to guides/grid
- Guide Settings dialog box (Dialog editor)
ms.assetid: 55381e1c-146a-4fa7-b1b3-b1492817615f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7369fdb37dbef474dafea2ba2a9a7e28f5eface9
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318888"
---
# <a name="guide-settings-dialog-box-c"></a>Handbuch Einstellungen (Dialogfeld) (C++)

## <a name="layout-guides"></a>Layoutführungslinien

Zeigt die Einstellungen für die Layoutführungslinien.

### <a name="none"></a>Keiner

Blendet die Layout-Tools.

### <a name="rulers-and-guides"></a>Lineale und Führungslinien

Wenn aktiviert, wird die Layouttools Lineale hinzugefügt; Führungslinien können in die Lineale platziert werden. Die Standard-Handbücher sind die Ränder, die durch Ziehen von verschoben werden können. Klicken Sie auf die Lineale, um eine Anleitung zu platzieren. Steuerelemente "Ausrichten" in den Anleitungen, wenn die Steuerelemente über oder neben dem Namen verschoben werden. Steuerelemente werden auch mit einer Anleitung verschieben, nachdem sie sie verbunden sind. Wenn Sie ein Steuerelement in ein auf jeder Seite angefügt ist und eine Anleitung verschoben wird, wird das Steuerelement geändert.

### <a name="grid"></a>Raster

Erstellt eine Layoutraster für Telefone. Neue Steuerelemente werden automatisch auf das Raster ausgerichtet.

## <a name="grid-spacing"></a>Rasterweite

Zeigt die Einstellungen für den Rasterabstand in Box Dialogeinheiten (DLUs).

### <a name="width-dlus"></a>Breite: DLUs

Legt die Breite des Layoutrasters in DLUs fest. Eine horizontale DLU ist die durchschnittliche Breite der Dialogfeld-Schriftart geteilt durch vier.

### <a name="height-dlus"></a>Height: DLUs

Legt die Höhe des Layoutrasters in DLUs fest. Eine vertikale DLU ist die durchschnittliche Höhe des geteilt durch acht Dialogfeld-Schriftart.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ändern des Layoutrasters](../windows/modifying-the-layout-grid.md)  
[Modi des Dialog-Editors (Führungslinien und Raster)](../windows/dialog-editor-states-guides-and-grids.md)