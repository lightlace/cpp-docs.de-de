---
title: Erstellen einer neuen Symbolleistenschaltfläche (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.toolbar
dev_langs:
- C++
helpviewer_keywords:
- Toolbar editor [C++], creating buttons
- toolbar buttons [C++], button image
- toolbar buttons [C++], creating
- toolbar buttons (in Toolbar editor)
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0f1ed792407160c1d025dabb3b8cc01a2ebc7330
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44314325"
---
# <a name="creating-a-new-toolbar-button-c"></a>Erstellen einer neuen Symbolleistenschaltfläche (C++)

### <a name="to-create-a-new-toolbar-button"></a>Erstellen Sie eine neue Symbolleisten-Schaltfläche

1. In [Ressourcenansicht](../windows/resource-view-window.md) erweitern Sie den Ressourcenordner (z. B. Projekt1.rc).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Erweitern Sie die **Symbolleiste** Ordner, und wählen Sie eine Symbolleiste zur Bearbeitung.

3. Weisen Sie eine ID, auf die leere Schaltfläche am rechten Ende der Symbolleiste. Bearbeiten Sie dazu die **ID** -Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Beispielsweise empfiehlt es sich um einer Symbolleisten-Schaltfläche, die gleiche ID wie eine Menüoption gewähren. In diesem Fall verwenden Sie im Dropdown-Listenfeld auswählen der **ID** der Menüoption.

   - oder - 

   Wählen Sie die leere Schaltfläche am rechten Ende der Symbolleiste (in der **Symbolleiste anzeigen** Bereich) und Zeichnen zu beginnen. Die Befehls-ID eine Standard-Schaltfläche zugewiesen ist (ID_BUTTON\<n >).

Sie können auch kopieren und fügen Sie ein Image auf einer Symbolleiste als neue Schaltfläche.

### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>Hinzufügen eines Bilds zu einer Symbolleiste als Schaltfläche

1. In [Ressourcenansicht](../windows/resource-view-window.md), öffnen Sie die Symbolleiste, indem Sie darauf doppelklicken.

2. Öffnen Sie als Nächstes das Bild, das Sie hinzufügen, klicken Sie auf der Symbolleiste möchten.

   > [!NOTE]
   > Wenn Sie das Bild in Visual Studio öffnen, öffnen sie in der **Image** Editor. Sie können das Bild auch in anderen Grafikprogrammen öffnen.

3. Von der **bearbeiten** Menü wählen **Kopie**.

4. Wechseln Sie zu der Symbolleiste, indem Sie auf der Registerkarte am oberen Rand des Fensters Datenquelle.

5. Von der **bearbeiten** Menü wählen **einfügen**.

   Das Bild wird auf der Symbolleiste als neue Schaltfläche angezeigt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

MFC oder ATL

## <a name="see-also"></a>Siehe auch

[Eigenschaften von Symbolleisten-Schaltflächen](../windows/toolbar-button-properties.md)  
[Erstellen, Verschieben und Bearbeiten von Schaltflächen der Symbolleiste](../windows/creating-moving-and-editing-toolbar-buttons.md)  
[Symbolleisten-Editor](../windows/toolbar-editor.md)