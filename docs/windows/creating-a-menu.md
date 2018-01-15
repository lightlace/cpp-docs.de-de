---
title: "Erstellen eines Menüs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.menu
dev_langs: C++
helpviewer_keywords:
- mnemonics, associating menu items
- menus, associating commands with mnemonic keys
- menus, creating
ms.assetid: 66f94448-9b97-4b73-bf97-10d4bf87cc65
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7d5d600a168c93b663ebe446ddd912d98fee1b19
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-menu"></a>Erstellen eines Menüs
> [!NOTE]
>  Das Ressourcen-Fenster ist in Express-Editionen nicht verfügbar.  
  
### <a name="to-create-a-standard-menu"></a>So erstellen Sie ein Standardmenü  
  
1.  Klicken Sie im Menü **Ansicht** auf **Ressourcenansicht** und klicken Sie mit der rechten Maustaste auf die Überschrift **Menü** , und wählen Sie **Ressource hinzufügen**aus. Wählen Sie **Menü**aus.  
  
2.  Wählen Sie auf der Menüleiste das Feld **Neues Element** (das Rechteck mit dem Text "Hier eingeben") aus.  
  
     ![Feld "Neues Element" im Menü-Editor](../windows/media/vcmenueditornewitembox.gif "VcMenuEditorNewItemBox")  
Feld "Neues Element"  
  
3.  Geben Sie einen Namen für das neue Menü ein, z. B. "Datei".  
  
     Der eingegebene Text wird sowohl im **Menü** -Editor als auch im Feld **Beschriftung** im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)angezeigt. Die Eigenschaften des neuen Menüs können an einer der beiden Stellen bearbeitet werden.  
  
     Nachdem Sie das neue Menü in der Menüleiste benannt haben, rückt das Feld für das neue Menüelement nach rechts (damit ein weiteres Menü eingefügt werden kann). Unter dem ersten Menü wird ein weiteres Feld geöffnet, dem Sie Menübefehle hinzufügen können.  
  
     ![Erweitertes Feld "Neues Element"](../windows/media/vcmenueditornewitemboxexpanded.gif "VcMenuEditorNewItemBoxExpanded")  
Feld "Neues Element", dessen Fokus nach der Eingabe des Menünamens versetzt wurde  
  
    > [!NOTE]
    >  Um ein Menü mit einem einzigen Element in der Menüleiste zu erstellen, legen Sie die Eigenschaft Popup auf False fest.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Menü-Editor](../windows/menu-editor.md)