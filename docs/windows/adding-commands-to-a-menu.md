---
title: "Hinzufügen von Befehlen zu einem Menü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.menu
dev_langs:
- C++
helpviewer_keywords:
- menu items, adding to menus
- menus, adding items
- commands, adding to menus
- commands
- menu items
ms.assetid: 1523a755-0ab5-42f8-9e98-bb9881564431
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d53f868fd76877152bb3ec81fdba85c1d97b3aac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-commands-to-a-menu"></a>Hinzufügen von Befehlen zu einem Menü
### <a name="to-add-commands-to-a-menu"></a>So fügen Sie Befehle zu einem Menü hinzu  
  
1.  [Erstellen eines Menüs](../windows/creating-a-menu.md).  
  
2.  Klicken Sie auf einen Menünamen, beispielsweise „Datei“.  
  
     Jedes Menü wird erweitert, und es wird ein neues Elementfeld für Befehle zur Verfügung gestellt. Beispielsweise können Sie die Befehle „New“, „Open“ und „Close“ zu einem Dateimenü hinzufügen.  
  
3.  Geben Sie im neuen Elementfeld einen Namen für den neuen Menübefehl ein.  
  
    > [!NOTE]
    >  Der eingegebene Text wird angezeigt, in den Menü-Editor und in der **Beschriftung** Feld der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Die Eigenschaften des neuen Menüs können an einer der beiden Stellen bearbeitet werden.  
  
    > [!TIP]
    >  Sie können eine mnemonische Taste (Zugriffstaste) definieren, die dem Benutzer ermöglicht, den Menübefehl auszuwählen. Geben Sie ein kaufmännisches Und-Zeichen (&) vor einen Buchstaben ein, um ihn als mnemonisch anzugeben. Der Benutzer kann den Menübefehl auswählen, indem er diesen Buchstaben eingibt.  
  
4.  Wählen Sie im Fenster „Eigenschaften“ die geltenden Menübefehlseigenschaften aus. Weitere Informationen finden Sie unter [Menübefehlseigenschaften](../windows/menu-command-properties.md).  
  
5.  In der **Eingabeaufforderung** im Fenster Eigenschaften geben Sie die eingabeaufforderungs-Zeichenfolge in der Statusleiste Ihrer Anwendung angezeigt werden sollen.  
  
     Dadurch wird ein Eintrag mit einem Ressourcenbezeichner in der Zeichenfolgentabelle erstellt, der dem von Ihnen erstellten Menübefehl entspricht.  
  
    > [!NOTE]
    >  Eingabeaufforderungen können nur auf Menüelemente mit Anwenden einer **Popup** Eigenschaft **"true"**. Beispielsweise können Menüelemente auf oberster Ebene über Eingabeaufforderungen verfügen, wenn sie über Untermenüelemente verfügen. Der Zweck einer Eingabeaufforderung besteht darin, das anzuzeigen, was passiert, wenn ein Benutzer auf das Menüelement klickt.  
  
6.  Drücken Sie **EINGABETASTE** auf den Menübefehl abzuschließen.  
  
     Das neue Elementfeld wird ausgewählt, sodass Sie zusätzliche Menübefehle erstellen können.  
  

  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Menü-Editor](../windows/menu-editor.md)   
