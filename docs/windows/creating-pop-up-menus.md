---
title: Erstellen von Popupmenüs (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- context menus [C++], Menu Editor
- pop-up menus [C++], creating
- menus [C++], pop-up
- menus [C++], creating
- shortcut menus [C++], creating
- pop-up menus [C++], displaying
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
ms.openlocfilehash: 243a2489918f74243ce3b2268ec44c4fe4c1b566
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506781"
---
# <a name="creating-pop-up-menus-c"></a>Erstellen von Popupmenüs (C++)

[Popupmenüs](../mfc/menus-mfc.md) enthalten häufig verwendete Befehle. Sie können kontextbezogen für die Position des Zeigers sein. Für das Verwenden von Popupmenüs in Ihrer Anwendung muss das Menü selbst erstellt und anschließend mit dem Anwendungscode verbunden werden.

Nachdem Sie die Menüressource erstellt haben, muss der Anwendungscode die Menüressource laden und [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) verwenden, damit das Menü angezeigt wird. Sobald der Benutzer durch Klicken neben das Menü das Popupmenü ausblendet oder auf einen Befehl geklickt hat, wird die Funktion zurückgegeben. Wenn der Benutzer einen Befehl auswählt, wird dessen Befehlsmeldung an das Fenster gesendet, dessen Handle übergeben wurde.

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

[Verbinden eines Popupmenüs mit der Anwendung](../windows/connecting-a-pop-up-menu-to-your-application.md)<br/>
[Menü-Editor](../windows/menu-editor.md)