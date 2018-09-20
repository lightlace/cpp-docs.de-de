---
title: Ausrichten von Steuerelementen an einer Führungslinie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DLUs (dialog units)
- controls [C++], aligning
- Dialog Editor [C++], snap to guides
- guides, tick mark interval
- dialog box controls [C++], placement
- guides, aligning controls
- dialog units (DLUs)
- snap to guides (Dialog editor)
- controls [C++], sizing
- tick mark interval in Dialog editor
- controls [C++], snap to guides/grid
ms.assetid: 17db84ba-5288-4478-be57-afa748aa6447
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 648d78466b912f5f1f8c6a83065a07861ab9a7f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374418"
---
# <a name="aligning-controls-on-a-guide"></a>Ausrichten von Steuerelementen an einer Führungslinie

Die Ziehpunkte des Steuerelementen ausrichten an Führungslinien, wenn die Steuerelemente verschoben werden, und Anleitungen an Steuerelementen ausrichten, (wenn vorhanden im Handbuch ausgerichtet sind). Wenn eine Anleitung verschoben wird, verschieben sowie Steuerelemente, die darauf ausgerichtet sind. Steuerelemente, die an mehr als ein Handbuch Rasterlinie ausgerichtet werden geändert, wenn eine der Anleitungen verschoben wird.

Die Teilstriche in die Lineale, die bestimmen, den Abstand von Führungslinien und Steuerelemente werden durch Dialogeinheiten (DLUs) definiert. Eine DLU basiert auf der Größe der Dialogfeld-Schriftart, normalerweise 8 Punkt MS Shell Dlg. Eine horizontale DLU ist die durchschnittliche Breite der Dialogfeld-Schriftart geteilt durch vier. Eine vertikale DLU ist die durchschnittliche Höhe der Schriftart geteilt durch acht.

### <a name="to-size-a-group-of-controls-with-guides"></a>Eine Gruppe von Steuerelementen mit Guides Größe

1. Richten Sie eine Seite des Steuerelements (oder Steuerelemente), um eine Anleitung.

2. Ziehen Sie eine Anleitung für die der anderen Seite des Steuerelements (oder Steuerelemente).

   Bei Bedarf mit mehreren Steuerelementen, die Größe jedes in der zweiten Anleitung ausrichten.

3. Verschieben Sie entweder Anleitung, die Größe des Steuerelements (bzw. der Steuerelemente).

### <a name="to-change-the-intervals-of-the-tick-marks"></a>So ändern Sie die Intervalle der Teilstriche

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

2. In der [im Dialogfeld "Einstellungen" Handbuch](../windows/guide-settings-dialog-box.md)in die **Rasterweite** an eine neue Breite und Höhe in DLUs.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Modi des Dialog-Editors (Führungslinien und Raster)](../windows/dialog-editor-states-guides-and-grids.md)<br/>
[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)