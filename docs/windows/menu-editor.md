---
title: Menü-Editor (C++)
ms.date: 02/15/2019
f1_keywords:
- vc.editors.menu.F1
- vc.editors.menu
helpviewer_keywords:
- resource editors [C++], Menu editor
- editors, menus
- Menu editor
- menus [C++], Menu editor
- mnemonics [C++], associating menu items
- menus [C++], associating commands with mnemonic keys
- menus [C++], creating
- menus [C++], adding items
- commands [C++], adding to menus
- menu items, adding to menus
- submenus
- submenus [C++], creating
- menus [C++], creating
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
- menu commands [C++], selecting
- menus [C++], selecting
- commands [C++], menu commands
- commands [C++], copying on menus
- menu items, moving
- commands [C++], moving on menus
- menu items, copying
- menu items, deleting
- commands [C++], deleting from menus
- menus [C++], deleting
ms.assetid: 421fb215-6e12-4ec9-a3af-82d77f87bfa6
ms.openlocfilehash: 09d385404edbc33883d2d2add2328b33876d23ae
ms.sourcegitcommit: ecf274bcfe3a977c48745aaa243e5e731f1fdc5f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66504641"
---
# <a name="menu-editor-c"></a>Menü-Editor (C++)

Menüs ermöglichen Ihnen das Anordnen von Befehlen in einer logischen und leicht verständlichen Weise. Mit der **Menü-Editor**, können Sie erstellen und Bearbeiten von Menüs durch die enge direkt mit einer Menüleiste, ähnelt in der fertigen Anwendung.

> [!TIP]
> Bei der Verwendung der **Menü-Editor**, in vielen Fällen, Sie können mit der rechten Maustaste ein Popupmenü mit häufig verwendeten Befehlen anzuzeigen. Die verfügbaren Befehle hängen davon ab, auf was der Zeiger verweist.

## <a name="how-to"></a>Gewusst wie

Die **Menü-Editor** können Sie:

### <a name="to-create-a-standard-menu"></a>So erstellen Sie ein Standardmenü

1. Wechseln Sie zum Menü **Ansicht** > **Ressourcenansicht** mit der rechten Maustaste auf die **Menü** Überschrift. Wählen Sie **Ressource hinzufügen**, klicken Sie dann **Menü**.

1. Wählen Sie die **neues Element** Box (das Rechteck mit *Text hier eingeben*) in der Menüleiste.

   ![Feld "Neues Element" im Menü-Editor](../windows/media/vcmenueditornewitembox.gif "VcMenuEditorNewItemBox")<br/>
   **Neues Element** Feld

1. Geben Sie einen Namen für das neue Menü ein, z. B. *Datei*.

   Der eingegebene Text wird angezeigt, sowohl die **Menü-Editor** und klicken Sie in der **Beschriftung** im Feld der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Die Eigenschaften des neuen Menüs können an einer der beiden Stellen bearbeitet werden.

   Nachdem Sie das neue Menü in der Menüleiste benannt haben, rückt das Feld für das neue Menüelement nach rechts (damit ein weiteres Menü eingefügt werden kann). Unter dem ersten Menü wird ein weiteres Feld geöffnet, dem Sie Menübefehle hinzufügen können.

   ![Erweiterte neue Elementfeld](../windows/media/vcmenueditornewitemboxexpanded.gif "VcMenuEditorNewItemBoxExpanded")<br/>
   **Neues Element** Feld mit dem Fokus verschoben wird, nach der Eingabe des Namens im Startmenü

   > [!NOTE]
   > Um ein einzelnes Element im Menü auf der Menüleiste zu erstellen, legen die **Popup** Eigenschaft **"false"** .

### <a name="to-create-a-submenu"></a>So erstellen Sie ein Untermenü

1. Wählen Sie den Menübefehl für den Sie ein Untermenü erstellen möchten.

1. Geben Sie im Feld **Neues Element** , das rechts angezeigt wird, den Namen des neuen Menübefehls ein. Dieser neue Befehl wird im Untermenü an erster Stelle angezeigt.

1. Fügen Sie dem Untermenü weitere Menübefehle hinzu.

### <a name="to-insert-a-new-menu-between-existing-menus"></a>So fügen Sie ein neues Menüs zwischen vorhandenen Menüs ein

Wählen Sie einen vorhandenen Menünamen, und drücken Sie die **einfügen** drücken oder mit der rechten Maustaste in der Menüleiste, und wählen Sie **neue einfügen**.

   Die **neues Element** Feld vor dem ausgewählten Element eingefügt wird.

### <a name="to-add-commands-to-a-menu"></a>So fügen Sie Befehle zu einem Menü hinzu

1. Erstellen Sie ein Menü an. Wählen Sie dann einen Menünamen, z. B. **Datei**.

   Jedes Menü wird erweitert, und es wird ein neues Elementfeld für Befehle zur Verfügung gestellt. Sie können z. B. die Befehle hinzufügen **neu**, **öffnen**, und **schließen** auf eine **Datei** Menü.

1. Geben Sie im neuen Elementfeld einen Namen für den neuen Menübefehl ein.

   > [!NOTE]
   > Der eingegebene Text wird angezeigt, sowohl die **Menü-Editor** und klicken Sie in der **Beschriftung** im Feld der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Die Eigenschaften des neuen Menüs können an einer der beiden Stellen bearbeitet werden.

   > [!TIP]
   > Sie können eine mnemonische Taste (Zugriffstaste) definieren, die dem Benutzer ermöglicht, den Menübefehl auszuwählen. Geben Sie ein kaufmännisches und-Zeichen (`&`) vor einen Buchstaben ein, um ihn als mnemonisch anzugeben. Der Benutzer kann den Menübefehl auswählen, indem er diesen Buchstaben eingibt.

1. In der **Eigenschaften** wählen Sie im Fenster Eigenschaften, die gelten für den Menübefehl. Weitere Informationen finden Sie unter [Menübefehlseigenschaften](../windows/menu-command-properties.md).

1. In der **Eingabeaufforderung** im Feld der **Eigenschaften** Fenster, geben Sie die eingabeaufforderungs-Zeichenfolge in der Statusleiste Ihrer Anwendung angezeigt werden sollen.

   Dieser Schritt erstellt einen Eintrag in der Tabelle mit den gleichen Ressourcenbezeichner des Menübefehls, die Sie erstellt haben.

   > [!NOTE]
   > Eingabeaufforderungen können nur auf Menüelemente mit Anwenden einer **Popup** Eigenschaft **"true"** . Beispielsweise können Menüelemente auf oberster Ebene über Eingabeaufforderungen verfügen, wenn sie über Untermenüelemente verfügen. Der Zweck einer **Eingabeaufforderung** besteht darin anzugeben, was passiert, wenn ein Benutzer das Menüelement auswählt.

1. Drücken Sie **EINGABETASTE** auf den Menübefehl abzuschließen.

   Das neue Elementfeld wird ausgewählt, sodass Sie zusätzliche Menübefehle erstellen können.

### <a name="to-select-multiple-menu-commands-to-run-bulk-operations-such-as-deleting-or-changing-properties"></a>Zum Auswählen mehrerer Menübefehle zum Ausführen von Massenvorgängen wie z. B. das Löschen oder Ändern von Eigenschaften

Halten Sie die **STRG** Schlüssel, wählen Sie die Menüs oder Untermenübefehle werden sollen.

### <a name="to-move-and-copy-menus-and-menu-commands"></a>Zum Verschieben und Kopieren von Menüs und Menübefehlen

- Verwenden Sie die Drag & Drop-Methode:

   1. Ziehen oder kopieren Sie das zu verschiebende Elemente in:

      - Eine neue Position im aktuellen Menü.

      - Ein anderes Menü. Sie können mit anderen Menüs navigieren, durch Ziehen des Mauszeigers darüber.

   1. Legen Sie den Menübefehl ab, wenn die Einfügemarke die gewünschte Position anzeigt.

- Verwenden Sie die Befehle im Kontextmenü:

   1. Mit der rechten Maustaste eine oder mehrere Menüs oder Menübefehle, und wählen Sie dann **Ausschneiden** (zum Verschieben) oder **Kopie**.

   1. Wenn Sie die Elemente zu einer anderen Menüressource verschieben, Ressource oder Ressourcenskriptdatei [öffnen Sie es in ein anderes Fenster](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

   1. Wählen Sie die Position des Menüs oder Menübefehls aus, zu der Sie das Verschieben oder Kopieren vornehmen möchten.

   1. Wählen Sie im Kontextmenü **Einfügen**aus. Das verschobene oder kopierte Element wird vor dem von Ihnen ausgewählten Element platziert.

> [!NOTE]
> Sie können Elemente auch ziehen und kopieren und sie in anderen Menüs in anderen Menüfenstern einfügen.

### <a name="to-delete-a-menu-or-menu-command"></a>So löschen Sie ein Menü oder einen Menübefehl

Mit der rechten Maustaste den Menünamen oder den Befehl aus, und wählen Sie **löschen**.

> [!NOTE]
> Entsprechend können Sie mit dem Kontextmenü andere Aktionen ausführen, wie z. B. Kopieren, Ausschneiden, Einfügen, Neue einfügen, Trennzeichen einfügen, IDs bearbeiten, Als Popup anzeigen, Mnemonik überprüfen usw.

## <a name="pop-up-menus"></a>Popup-Menüs

[Popupmenüs](../mfc/menus-mfc.md) enthalten häufig verwendete Befehle. Sie können kontextbezogen für die Position des Zeigers sein. Für das Verwenden von Popupmenüs in Ihrer Anwendung muss das Menü selbst erstellt und anschließend mit dem Anwendungscode verbunden werden.

Nachdem Sie die Menüressource erstellt haben, muss der Anwendungscode die Menüressource laden und verwenden [TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu) auf das Menü angezeigt wird. Sobald der Benutzer das Popupmenü dazu außerhalb davon geschlossen oder einen Befehl ausgewählt hat, wird die Funktion zurückgegeben. Wenn der Benutzer einen Befehl auswählt, wird dessen Befehlsmeldung an das Fenster gesendet, dessen Handle übergeben wurde.

> [!NOTE]
> Verwenden Sie für Microsoft Foundation Class (MFC)-Library-Programmen und ATL-Programmen **Codeassistenten** um Menübefehle mit Code zu verknüpfen. Weitere Informationen finden Sie unter [Hinzufügen eines Ereignisses](../ide/adding-an-event-visual-cpp.md) und [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).

- Um ein Popup-Menü zu erstellen, erstellen Sie ein Menüelement mit einem leeren Titel, und bieten keine *Beschriftung*. Klicken Sie dann ein Menübefehls zum neuen Menü hinzufügen, verschieben Sie in der ersten Menübefehl unter dem leeren Menütitel mit der temporäre Beschriftung *Text hier eingeben* , und geben Sie einen *Beschriftung* und andere Informationen.

   Wiederholen Sie diesen Vorgang für alle anderen Menübefehle im Popupmenü aus, und achten Sie darauf, dass Sie die Menüressource zu speichern.

- Zum Verbinden eines Popupmenüs mit Ihrer Anwendung z. B. Hinzufügen eines meldungshandlers für WM_CONTEXTMENU, und fügen der Message-Handler den folgenden Code hinzu:

    ```cpp
    CMenu menu;
    VERIFY(menu.LoadMenu(IDR_MENU1));
    CMenu* pPopup = menu.GetSubMenu(0);
    ASSERT(pPopup != NULL);
    pPopup->TrackPopupMenu(TPM_LEFTALIGN | TPM_RIGHTBUTTON, point.x, point.y, AfxGetMainWnd());
    ```

   > [!NOTE]
   > Die [CPoint](../atl-mfc-shared/reference/cpoint-class.md) übergeben durch die Nachricht Handler ist, in Bildschirmkoordinaten.

Normalerweise, wenn Sie arbeiten der **Menü-Editor**, eine Menüressource als Menüleiste angezeigt wird. Sie verfügen jedoch möglicherweise über Menüressourcen, die während der Ausführung des Programms zur Menüleiste der Anwendung hinzugefügt werden.

- Klicken Sie zum Anzeigen einer Menüressource als Popupmenü mit der rechten Maustaste im Menüs, und wählen Sie **als Popup anzeigen**.

   Diese Option ist nur eine anzeigeeinstellung, und es ändert sich das Menü nicht.

> [!TIP]
> Um zur Ansicht Menüleiste zu ändern, wählen **als Popup anzeigen** erneut aus. Diese Aktion entfernt das Häkchen, und gibt die Menüleisten-Ansicht.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Menübefehle](../windows/menu-command-properties.md)<br/>
[Benutzeroberflächenobjekte und Befehls-IDs](../mfc/user-interface-objects-and-command-ids.md)<br/>
[Menüs](../mfc/menus-mfc.md)<br/>
[Menüs](/windows/desktop/menurc/menus)