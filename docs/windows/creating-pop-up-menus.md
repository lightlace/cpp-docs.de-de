---
title: Erstellen von Popupmenüs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6b06fa02420b70538faa70b24137df634420dd8d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222643"
---
# <a name="creating-pop-up-menus"></a>Erstellen von Popupmenüs

[Popupmenüs](../mfc/menus-mfc.md) enthalten häufig verwendete Befehle. Sie können kontextbezogen für die Position des Zeigers sein. Für das Verwenden von Popupmenüs in Ihrer Anwendung muss das Menü selbst erstellt und anschließend mit dem Anwendungscode verbunden werden.

Nachdem Sie die Menüressource erstellt haben, muss Ihr Anwendungscode die Menüressource laden und verwenden [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) auf das Menü angezeigt wird. Sobald der Benutzer durch Klicken neben das Menü das Popupmenü ausblendet oder auf einen Befehl geklickt hat, wird die Funktion zurückgegeben. Wenn der Benutzer einen Befehl auswählt, wird dessen Befehlsmeldung an das Fenster gesendet, dessen Handle übergeben wurde.

### <a name="to-create-a-pop-up-menu"></a>Erstellen eines Popupmenüs

1. [Erstellen eines Menüs](../windows/creating-a-menu.md) mit einem leeren Titel (also ohne Angabe einer **Beschriftung**).

2. [Hinzufügen eines Menübefehls zum neuen Menü](../windows/adding-commands-to-a-menu.md). Verschieben Sie in der ersten Menübefehl unter dem leeren Menütitel (die temporäre Beschriftung sagt `Type Here`). Geben Sie eine **Beschriftung** und weitere Informationen ein.

   Wiederholen Sie diesen Vorgang für alle anderen Menübefehle im Popupmenü.

3. Speichern Sie die Menüressource.

   > [!TIP]
   > Weitere Informationen zur Anzeige der Popupmenüs finden Sie unter [Anzeigen eines Menüs als Popupmenü](../windows/viewing-a-menu-as-a-pop-up-menu.md).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Verbinden eines Popupmenüs mit der Anwendung](../windows/connecting-a-pop-up-menu-to-your-application.md)  
[Menü-Editor](../windows/menu-editor.md)