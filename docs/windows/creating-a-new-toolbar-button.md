---
title: "Erstellen einer neuen Symbolleistenschaltfläche | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.toolbar
dev_langs:
- C++
helpviewer_keywords:
- Toolbar editor, creating buttons
- toolbar buttons (in Toolbar editor), button image
- toolbar buttons (in Toolbar editor), creating
- toolbar buttons (in Toolbar editor)
ms.assetid: 46c120fe-4f2a-4887-a08f-bd1fea04b3f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6b89d88d931603f1f8dfd65f08cb78210eac19a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-new-toolbar-button"></a>Erstellen einer neuen Symbolleisten-Schaltfläche
### <a name="to-create-a-new-toolbar-button"></a>Zum Erstellen einer neuen Symbolleisten-Schaltfläche  
  
1.  In [Ressourcenansicht](../windows/resource-view-window.md) erweitern Sie den Ressourcenordner (z. B. Projekt1.rc).  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Erweitern Sie die **Symbolleiste** Ordner, und wählen Sie eine Symbolleiste zu bearbeiten.  
  
3.  Weisen Sie eine ID, auf die leere Schaltfläche am rechten Ende der Symbolleiste. Können Sie dies tun, indem Sie bearbeiten die **ID** Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Beispielsweise empfiehlt es sich um einer Symbolleisten-Schaltfläche auf die gleiche ID wie eine Menüoption zu gewähren. In diesem Fall verwenden Sie im Dropdown-Listenfeld auswählen der **ID** der Menüoption.  
  
     - oder -   
  
     Wählen Sie die leere Schaltfläche am rechten Ende der Symbolleiste (im Symbolleisten Ansichtsbereich), und beginnen Sie zeichnen. Die Befehls-ID eine Standard-Schaltfläche zugewiesen ist (ID_BUTTON\<n >).  
  
 Sie können auch kopieren und fügen Sie ein Bild auf einer Symbolleiste als eine Schaltfläche "Neu".  
  
#### <a name="to-add-an-image-to-a-toolbar-as-a-button"></a>So fügen Sie ein Bild zu einer Symbolleiste als Schaltfläche hinzu  
  
1.  In [Ressourcenansicht](../windows/resource-view-window.md), öffnen Sie die Symbolleiste, indem Sie darauf doppelklicken.  
  
2.  Als Nächstes öffnen Sie das Bild, das Sie hinzufügen möchten, klicken Sie auf der Symbolleiste angezeigt wird.  
  
    > [!NOTE]
    >  Wenn Sie das Bild in Visual Studio öffnen, wird es in der Grafik-Editor geöffnet. Sie können auch das Bild in anderen Programmen öffnen.  
  
3.  Aus der **bearbeiten** Menü wählen **Kopie**.  
  
4.  Wechseln Sie auf der Symbolleiste angezeigt wird, indem Sie auf der Registerkarte am oberen Rand des Quellcodefensters.  
  
5.  Aus der **bearbeiten** Menü wählen **einfügen**.  
  
     Das Bild wird als eine Schaltfläche "Neu" auf der Symbolleiste angezeigt.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Anforderungen  
 MFC oder ATL  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaften von Symbolleisten-Schaltfläche](../windows/toolbar-button-properties.md)   
 [Erstellen, verschieben und Bearbeiten von Schaltflächen der Symbolleiste](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [Symbolleisten-Editor](../windows/toolbar-editor.md)

