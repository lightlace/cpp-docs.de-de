---
title: Ändern des Layoutrasters | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], layout grid
- snap to layout grid
- grids, turning on or off
- layout grid in Dialog Editor
- grids, changing size
ms.assetid: ec31f595-7542-485b-806f-efbaeccc1b3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d583bbbfeb4cd426684d1091a165335f7cbb6e64
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46441396"
---
# <a name="modifying-the-layout-grid"></a>Ändern des Layoutrasters

Beim Anordnen von Steuerelementen in einem Dialogfeld oder platziert werden, können Sie das Layoutraster für die eine genauere Positionierung verwenden. Wenn das Raster aktiviert ist, scheinen die Steuerelemente ", die gepunkteten Zeilen im Raster ausrichten" einzurasten. Sie können Aktivieren dieses Feature "am Raster ausrichten" ein, und deaktivieren und Ändern der Größe der Rasterzellen des Layouts.

### <a name="to-turn-the-layout-grid-on-or-off"></a>Zum Aktivieren oder deaktivieren Sie des Layoutrasters

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

2. In der [im Dialogfeld "Einstellungen" Handbuch](../windows/guide-settings-dialog-box.md)aktivieren oder Deaktivieren der **Raster** Schaltfläche.

   Sie können weiterhin steuern das Raster in einzelnen **Dialogfeld** -Editor-Fenster mit den **Raster umschalten** Schaltfläche der [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).

### <a name="to-change-the-size-of-the-layout-grid"></a>Ändern die Größe des Layoutrasters

1. Von der **Format** Menü wählen **Einstellungen für Führungslinien**.

2. In der [im Dialogfeld "Einstellungen" Handbuch](../windows/guide-settings-dialog-box.md), geben Sie die Höhe und Breite in DLUs für die Zellen im Raster. Die minimale Höhe oder Breite ist 4 DLUs. Weitere Informationen zu DLUs, finden Sie unter [Anordnung von Steuerelementen in Dialogfeldern](../windows/arrangement-of-controls-on-dialog-boxes.md).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Modi des Dialog-Editors (Führungslinien und Raster)](../windows/dialog-editor-states-guides-and-grids.md)<br/>
[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)