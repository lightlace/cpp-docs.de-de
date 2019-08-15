---
title: 'TN014: Benutzerdefinierte Steuerelemente'
ms.date: 06/28/2018
f1_keywords:
- vc.controls
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
ms.openlocfilehash: 2960c5b8585519adb535e5611315ec4ececcf53e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511183"
---
# <a name="tn014-custom-controls"></a>TN014: Benutzerdefinierte Steuerelemente

In diesem Hinweis wird die MFC-Unterstützung für benutzerdefinierte Steuerelemente und selbst Zeichnungs Steuerelemente beschrieben. Außerdem werden dynamische Unterklassen beschrieben und die Beziehung zwischen [CWnd](../mfc/reference/cwnd-class.md) -Objekten und `HWND`s beschrieben.

Die MFC-Beispielanwendung CTRLTEST veranschaulicht, wie viele benutzerdefinierte Steuerelemente verwendet werden. Weitere Informationen finden Sie im Quellcode für das allgemeine MFC-Beispiel [CTRLTEST](../overview/visual-cpp-samples.md) und die Online Hilfe.

## <a name="owner-draw-controlsmenus"></a>Besitzer: Steuerelemente/Menüs

Windows bietet Unterstützung für Steuerelemente und Menüs zum Zeichnen von Besitzern mithilfe von Windows-Meldungen. Das übergeordnete Fenster eines beliebigen Steuer Elements oder Menüs empfängt diese Nachrichten und ruft Funktionen als Reaktion auf. Sie können diese Funktionen überschreiben, um die visuelle Darstellung und das Verhalten des Steuer Elements oder Menüs des Besitzers zu ändern.

MFC unterstützt das Erstellen von Besitzern direkt mit den folgenden Funktionen:

- [CWnd::OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)

- [CWnd::OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)

- [CWnd::OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)

- [CWnd::OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)

Sie können diese Funktionen in der `CWnd` abgeleiteten Klasse überschreiben, um benutzerdefiniertes Zeichnen-Verhalten zu implementieren.

Diese Vorgehensweise führt nicht zu wiederverwendbarem Code. Wenn zwei ähnliche Steuerelemente in zwei unterschiedlichen `CWnd` Klassen vorhanden sind, müssen Sie das benutzerdefinierte Steuerelement Verhalten an zwei Orten implementieren. Die von MFC unterstützte Self-Drawing-Steuerelement Architektur löst dieses Problem.

## <a name="self-draw-controls-and-menus"></a>Selbst zeichnen von Steuerelementen und Menüs

MFC stellt eine Standard Implementierung (in den `CWnd` [CMenu](../mfc/reference/cmenu-class.md) -Klassen und) für die standardmäßigen Besitzer zeichnenden Nachrichten bereit. Diese Standard Implementierung decodiert die Parameter, die vom Besitzer gezeichnet werden, und delegiert die Owner-Draw-Meldungen an die Steuerelemente oder das Menü. Dies wird als "selbst gezeichnet" bezeichnet, da sich der Zeichnungs Code in der Klasse des Steuer Elements oder Menüs befindet, nicht im Besitzer Fenster.

Mithilfe von selbst zeichnen-Steuerelementen können Sie wiederverwendbare Steuerelement Klassen erstellen, die die Semantik zum Anzeigen des Steuer Elements mithilfe von Besitzer zeichnen verwenden. Der Code zum Zeichnen des Steuer Elements befindet sich in der Steuerelement Klasse, nicht im übergeordneten Element. Dabei handelt es sich um einen objektorientierten Ansatz für die Programmierung von benutzerdefinierten Steuerelementen. Fügen Sie die folgende Liste von Funktionen zu ihren selbst Draw-Klassen hinzu:

- Für selbst zeichnende Schaltflächen:

    ```cpp
    CButton:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw this button
    ```

- Für selbst zeichnende Menüs:

    ```cpp
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this menu
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this menu
    ```

- Für selbst zeichnende Listenfelder:

    ```cpp
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this list box
    CListBox:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this list box

    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);
    // insert code to compare two items in this list box if LBS_SORT
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);
    // insert code to delete an item from this list box
    ```

- Für selbst zeichnende Kombinations Felder:

    ```cpp
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this combo box
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this combo box

    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);
    // insert code to compare two items in this combo box if CBS_SORT
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);
    // insert code to delete an item from this combo box
    ```

Ausführliche Informationen zu den Besitzer Zeichnungs Strukturen ([drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct), [measureitemstruct](/windows/win32/api/winuser/ns-winuser-measureitemstruct), [compareitemstruct](/windows/win32/api/winuser/ns-winuser-compareitemstruct)und [deleteitemstruct](/windows/win32/api/winuser/ns-winuser-deleteitemstruct)) finden Sie in der MFC-Dokumentation `CWnd::OnDrawItem`für `CWnd::OnMeasureItem`, `CWnd::OnCompareItem`, und .`CWnd::OnDeleteItem` bzw.

## <a name="using-self-draw-controls-and-menus"></a>Verwenden von selbst zeichnenden Steuerelementen und Menüs

Für selbst zeichnende Menüs müssen Sie sowohl die-Methode `OnMeasureItem` als `OnDrawItem` auch die-Methode überschreiben.

Für selbst zeichnende Listenfelder und Kombinations Felder müssen Sie und `OnMeasureItem` `OnDrawItem`überschreiben. Sie müssen den LBS_OWNERDRAWVARIABLE-Stil für Listenfelder oder den CBS_OWNERDRAWVARIABLE-Stil für Kombinations Felder in der Dialogfeld Vorlage angeben. Der "besitzdrawfixed"-Stil funktioniert nicht mit selbst zeichnenden Elementen, da die Höhe des fixierten Elements bestimmt wird, bevor selbst zeichnende Steuerelemente an das Listenfeld angefügt werden. (Sie können die Methoden [CListBox::](../mfc/reference/clistbox-class.md#setitemheight) [CComboBox:: abtitemheight](../mfc/reference/ccombobox-class.md#setitemheight) verwenden, um diese Einschränkung zu überwinden.)

Wenn Sie zu einem "besitzdrawvariable"-Stilwechseln, wird das System gezwungen, den nointegralheight-Stil auf das Steuerelement anzuwenden. Da das Steuerelement keine ganzzahlige Höhe mit Elementen variabler Größe berechnen kann, wird der Standardstil von IntegralHeight ignoriert, und das Steuerelement ist immer nointegralheight. Wenn Ihre Elemente eine festgelegte Höhe aufweisen, können Sie verhindern, dass partielle Elemente gezeichnet werden, indem Sie die Steuerelement Größe als ganzzahligen Multiplikator der Elementgröße angeben.

Für selbst Zeichnungs Listenfelder und Kombinations Felder mit dem LBS_SORT-oder CBS_SORT-Format müssen Sie die `OnCompareItem` -Methode überschreiben.

Für selbst Zeichnungs Listenfelder und Kombinations Felder `OnDeleteItem` wird in der Regel nicht überschrieben. Sie können über `OnDeleteItem` schreiben, wenn Sie eine spezielle Verarbeitung ausführen möchten. Dies gilt auch dann, wenn zusätzlicher Arbeitsspeicher oder andere Ressourcen mit jedem Listenfeld oder Kombinations Feld Element gespeichert werden.

## <a name="examples-of-self-drawing-controls-and-menus"></a>Beispiele für selbst Zeichnens von Steuerelementen und Menüs

Das allgemeine MFC-Beispiel [CTRLTEST](../overview/visual-cpp-samples.md) enthält Beispiele für ein selbst zeichnetes Menü und ein selbst zeichnetes Listenfeld.

Das typische Beispiel für eine selbst Zeichnungs Schaltfläche ist eine Bitmap-Schaltfläche. Eine Bitmap-Schaltfläche ist eine Schaltfläche, die ein, zwei oder drei Bitmap-Bilder für die verschiedenen Zustände anzeigt. Ein Beispiel hierfür finden Sie in der MFC-Klasse [CBitmapButton](../mfc/reference/cbitmapbutton-class.md).

## <a name="dynamic-subclassing"></a>Dynamische Unterklassen

Gelegentlich möchten Sie die Funktionalität eines Objekts ändern, das bereits vorhanden ist. In den vorherigen Beispielen mussten Sie die Steuerelemente vor der Erstellung anpassen. Mithilfe dynamischer Unterklassen können Sie ein Steuerelement anpassen, das bereits erstellt wurde.

Unterklassen sind der Windows-Begriff zum Ersetzen der <xref:System.Windows.Forms.Control.WndProc%2A> eines Fensters durch einen angepassten `WndProc` und zum Aufrufen des alten `WndProc` für die Standardfunktionalität.

Dies sollte nicht mit C++ der Klassen Ableitung verwechselt werden. Zur Verdeutlichung entsprechen C++ die Begriffe- *Basisklasse* und die *abgeleitete Klasse* der- *Klasse* und der- *Unterklasse* im Windows-Objektmodell. C++die Ableitung mit MFC und Windows-Unterklassen ist funktional ähnlich, außer C++ unterstützt keine dynamische Unterklassen.

Die `CWnd` -Klasse stellt die Verbindung zwischen C++ einem-Objekt ( `CWnd`abgeleitet von) und einem `HWND`Windows-Fenster Objekt (als bezeichnet) bereit.

Es gibt drei gängige Möglichkeiten, wie diese miteinander verknüpft sind:

- `CWnd`erstellt die `HWND`. Sie können das Verhalten in einer abgeleiteten Klasse ändern, indem Sie eine Klasse `CWnd`erstellen, die von abgeleitet ist. Wird erstellt, wenn Ihre Anwendung [CWnd:: Create aufruft.](../mfc/reference/cwnd-class.md#create) `HWND`

- Die Anwendung fügt eine `CWnd` an eine vorhandene `HWND`an. Das Verhalten des vorhandenen Fensters wird nicht geändert. Dies ist ein Fall der Delegierung und wird durch Aufrufen von [CWnd:: Attach](../mfc/reference/cwnd-class.md#attach) ermöglicht, um einen `HWND` vorhandenen an `CWnd` ein-Objekt zu Alias.

- `CWnd`wird an ein vorhandenes `HWND` angefügt, und Sie können das Verhalten in einer abgeleiteten Klasse ändern. Dies wird als dynamische Unterklassen bezeichnet, da wir das Verhalten und somit die Klasse eines Windows-Objekts zur Laufzeit ändern.

Dynamische Unterklassen können mithilfe der Methoden [CWnd:: SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow) und[CWnd:: SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem)erreicht werden.

Beide Routinen fügen ein `CWnd` -Objekt an ein `HWND`vorhandenes-Objekt an. `SubclassWindow``HWND` nimmt direkt an. `SubclassDlgItem`ist eine Hilfsfunktion, die eine Steuerelement-ID und das übergeordnete Fenster annimmt. `SubclassDlgItem`dient zum Anfügen C++ von Objekten an Dialogfeld Steuerelemente, die aus einer Dialogfeld Vorlage erstellt wurden

Im [CTRLTEST](../overview/visual-cpp-samples.md) -Beispiel finden Sie einige Beispiele für die Verwendung `SubclassWindow` von `SubclassDlgItem`und.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
