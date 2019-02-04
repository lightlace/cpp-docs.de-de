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
- pop-up menus [C++], connecting to applications
- context menus [C++], connecting to applications
- shortcut menus [C++], connecting to applications
- pop-up menus
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
ms.openlocfilehash: cf2e3578f49cb6b4af8797052273211f699a6b4f
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702829"
---
# <a name="creating-pop-up-menus-c"></a>Erstellen von Popupmenüs (C++)

[Popupmenüs](../mfc/menus-mfc.md) enthalten häufig verwendete Befehle. Sie können kontextbezogen für die Position des Zeigers sein. Für das Verwenden von Popupmenüs in Ihrer Anwendung muss das Menü selbst erstellt und anschließend mit dem Anwendungscode verbunden werden.

Nachdem Sie die Menüressource erstellt haben, muss der Anwendungscode die Menüressource laden und verwenden [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) auf das Menü angezeigt wird. Sobald der Benutzer das Popupmenü dazu außerhalb davon geschlossen oder einen Befehl ausgewählt hat, wird die Funktion zurückgegeben. Wenn der Benutzer einen Befehl auswählt, wird dessen Befehlsmeldung an das Fenster gesendet, dessen Handle übergeben wurde.

## <a name="to-create-a-pop-up-menu"></a>Erstellen eines Popupmenüs

1. [Erstellen eines Menüs](../windows/creating-a-menu.md) mit einem leeren Titel (also ohne Angabe einer **Beschriftung**).

1. [Hinzufügen eines Menübefehls zum neuen Menü](../windows/adding-commands-to-a-menu.md). Verschieben Sie in der ersten Menübefehl unter dem leeren Menütitel (die temporäre Beschriftung sagt `Type Here`). Geben Sie eine **Beschriftung** und weitere Informationen ein.

   Wiederholen Sie diesen Vorgang für alle anderen Menübefehle im Popupmenü.

1. Speichern Sie die Menüressource.

## <a name="to-connect-a-pop-up-menu-to-your-application"></a>So verbinden Sie ein Popupmenü mit Ihrer Anwendung

1. Fügen Sie einen Meldungshandler für WM_CONTEXTMENU (z. B.). Weitere Informationen finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).

1. Fügen Sie dem Meldungshandler folgenden Code hinzu.

    ```cpp
    CMenu menu;
    VERIFY(menu.LoadMenu(IDR_MENU1));
    CMenu* pPopup = menu.GetSubMenu(0);
    ASSERT(pPopup != NULL);
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());
    ```

   > [!NOTE]
   > Die [CPoint](../atl-mfc-shared/reference/cpoint-class.md) übergeben durch die Nachricht Handler ist, in Bildschirmkoordinaten.

   > [!NOTE]
   > Verbinden eines Popupmenüs mit der Anwendung erfordert MFC.

## <a name="to-view-a-menu-resource-as-a-pop-up-menu"></a>So zeigen Sie eine Menüressource als ein Popupmenü an

Normalerweise, wenn Sie arbeiten der **Menü** -Editor wird eine Menüressource als Menüleiste angezeigt. Sie verfügen jedoch möglicherweise über Menüressourcen, die während der Ausführung des Programms zur Menüleiste der Anwendung hinzugefügt werden.

Mit der rechten Maustaste im Menüs, und wählen Sie **als Popup anzeigen** aus dem Kontextmenü.

   Diese Option ist nur eine anzeigeeinstellung, und es ändert sich das Menü nicht.

   > [!NOTE]
   > Um zur Ansicht Menüleiste zu ändern, klicken Sie auf **als Popup anzeigen** erneut aus (die das Häkchen entfernt und Ihre Menüleistenansicht zurückgibt).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Menü-Editor](../windows/menu-editor.md)
