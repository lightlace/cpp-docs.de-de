---
title: Ausrichten von Steuerelementen an einer Führungslinie | Microsoft Docs
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
- Dialog editor, snap to guides
- guides, tick mark interval
- dialog box controls, placement
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
ms.openlocfilehash: a7c8cc57b4d2e7150ff09858cfd5b315beb37962
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857837"
---
# <a name="aligning-controls-on-a-guide"></a>Ausrichten von Steuerelementen an einer Führungslinie
Die Ziehpunkte des Steuerelemente ausrichten an Führungslinien, wenn die Steuerelemente verschoben werden, und Führungslinien an Steuerelemente ausrichten (wenn es keine Steuerelemente zuvor ausgerichtet). Wenn eine Orientierungshilfe verschoben wird, verschieben sowie Steuerelemente, die darauf ausgerichtet sind. Steuerelemente, die "angedockt", um mehr als eine Anleitung sind angepasst, wenn eine der Führungslinien verschoben wird.  
  
 Die Teilstriche in der Lineale, die bestimmen, den Abstand von Führungslinien und Steuerelemente werden durch Dialogeinheiten (DLUs) definiert. Eine DLU basiert auf der Größe der Dialogfeld-Schriftart, normalerweise 8 Punkt MS Shell Dlg. Eine horizontale DLU ist die durchschnittliche Breite der Dialogfeld-Schriftart geteilt durch vier. Eine vertikale DLU entspricht der durchschnittlichen Höhe der Schriftart, dividiert durch 8.  
  
### <a name="to-size-a-group-of-controls-with-guides"></a>Eine Gruppe von Steuerelementen mit Führungslinien Größe anpassen  
  
1.  Ausrichten von einer Seite eines Steuerelements (bzw. der Steuerelemente) in ein.  
  
2.  Ziehen Sie eine Anleitung für die andere Seite des Steuerelements (bzw. der Steuerelemente).  
  
     Bei Bedarf mit mehreren Steuerelementen, die Größe jedes Element in der zweiten Anleitung ausrichten.  
  
3.  Verschieben Sie entweder Anleitung zur Größe des Steuerelements (bzw. der Steuerelemente).  
  
### <a name="to-change-the-intervals-of-the-tick-marks"></a>So ändern Sie die Intervalle der Teilstriche  
  
1.  Aus der **Format** Menü wählen **Handbuch Einstellungen**.  
  
2.  In der [Handbuch Einstellungen (Dialogfeld)](../windows/guide-settings-dialog-box.md)in der **Rasterabstand** Feld, geben Sie eine neue Breite und Höhe in DLUs.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Dialog-Editor-Status (Führungslinien und Raster)](../windows/dialog-editor-states-guides-and-grids.md)   
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)

