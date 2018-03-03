---
title: "Erstellen von Popupmenüs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- context menus, Menu Editor
- pop-up menus, creating
- menus, pop-up
- menus, creating
- shortcut menus, creating
- pop-up menus, displaying
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6185f52eeaf56ac0d31cb8e9f22715db36514725
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="creating-pop-up-menus"></a>Erstellen von Popupmenüs
[Popupmenüs](../mfc/menus-mfc.md) enthalten häufig verwendete Befehle. Sie können kontextbezogen für die Position des Zeigers sein. Für das Verwenden von Popupmenüs in Ihrer Anwendung muss das Menü selbst erstellt und anschließend mit dem Anwendungscode verbunden werden.  
  
 Nachdem Sie die Menüressource erstellt haben, muss der Anwendungscode die Menüressource laden und [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) verwenden, damit das Menü angezeigt wird. Sobald der Benutzer durch Klicken neben das Menü das Popupmenü ausblendet oder auf einen Befehl geklickt hat, wird die Funktion zurückgegeben. Wenn der Benutzer einen Befehl auswählt, wird dessen Befehlsmeldung an das Fenster gesendet, dessen Handle übergeben wurde.  
  
### <a name="to-create-a-pop-up-menu"></a>Erstellen eines Popupmenüs  
  
1.  [Erstellen eines Menüs](../windows/creating-a-menu.md) mit einem leeren Titel (also ohne Angabe einer **Beschriftung**).  
  
2.  [Hinzufügen eines Menübefehls zum neuen Menü](../windows/adding-commands-to-a-menu.md). Kehren Sie zum ersten Menübefehl unter dem leeren Menütitel zurück (in der temporäre Beschriftung steht „hier tippen“). Geben Sie eine **Beschriftung** und weitere Informationen ein.  
  
     Wiederholen Sie diesen Vorgang für alle anderen Menübefehle im Popupmenü.  
  
3.  Speichern Sie die Menüressource.  
  
    > [!TIP]
    >  Weitere Informationen zur Anzeige der Popupmenüs finden Sie unter [Anzeigen eines Menüs als Popupmenü](../windows/viewing-a-menu-as-a-pop-up-menu.md).  
  

  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Verbinden eines Popupmenüs mit der Anwendung](../windows/connecting-a-pop-up-menu-to-your-application.md)   
 [Menü-Editor](../windows/menu-editor.md)