---
title: 'TN014: Benutzerdefinierte Steuerelemente | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.controls
dev_langs:
- C++
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7ab10a6c0c53bd9aba87ddea594e689b3142b4c
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2018
ms.locfileid: "39027260"
---
# <a name="tn014-custom-controls"></a>TN014: Benutzerdefinierte Steuerelemente

In diesem Hinweis wird beschrieben, die MFC-Unterstützung für benutzerdefinierte und selbst zeichnen-Steuerelemente. Außerdem wird beschrieben, dynamische Unterklassen und beschreibt die Beziehung zwischen [CWnd](../mfc/reference/cwnd-class.md) Objekte und `HWND`s.

Die MFC-beispielanwendung CTRLTEST veranschaulicht, wie viele benutzerdefinierte Steuerelemente. Finden Sie unter den Quellcode für die allgemeinen MFC-Beispiel [CTRLTEST](../visual-cpp-samples.md) und online-Hilfe.

## <a name="owner-draw-controlsmenus"></a>Ownerdrawn-Steuerelemente /-Menüs

Windows bietet Unterstützung für Ownerdrawn-Steuerelemente und Menüs, mithilfe von Windows-Nachrichten. Das übergeordnete Fenster eines Steuerelements oder im Menü empfängt diese Nachrichten und Anrufe Funktionen als Antwort. Sie können diese Funktionen zum Anpassen des visuellen Darstellung und Verhalten der Ownerdrawn-Steuerelement oder im Menü überschreiben.

MFC unterstützt direkt Ownerdrawn-mit den folgenden Funktionen:

- [CWnd::OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)

- [CWnd::OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)

- [CWnd::OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)

- [CWnd::OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)

Sie können angeben, überschreiben diese Funktionen in Ihre `CWnd` abgeleitete Klasse, um benutzerdefiniertes Zeichnen-Verhalten zu implementieren.

Dieser Ansatz führt nicht zu wiederverwendbaren Code. Wenn Sie zwei Steuerelemente mit ähnlichen in zwei verschiedenen haben `CWnd` Klassen müssen Sie das Verhalten des benutzerdefinierten Steuerelements sich an zwei Standorten implementieren. Die MFC-Unterstützung selbst zeichnen Steuerarchitektur löst dieses Problem.

## <a name="self-draw-controls-and-menus"></a>Selbst zu zeichnen, Steuerelemente und Menüs

MFC stellt eine Standardimplementierung bereit (in der `CWnd` und [CMenu](../mfc/reference/cmenu-class.md) Klassen) für die standard-Ownerdrawn-Nachrichten. Diese Standardimplementierung wird decodiert die Ownerdrawn-Parameter und Delegieren von Ownerdrawn-Nachrichten an den Steuerelementen oder im Menü. Dies wird selbst zeichnen bezeichnet, da der Code zum Zeichnen in der Klasse des Steuerelements oder im Menü nicht in das besitzende Fenster ist.

Mithilfe der Steuerelemente selbst zeichnen können Sie wiederverwendbaren Klassen erstellen, die Ownerdrawn-Semantik zu verwenden, um das Steuerelement angezeigt werden. Der Code zum Zeichnen des Steuerelements ist in der Steuerelementklasse, nicht mit seinem übergeordneten Element. Dies ist ein objektorientierter Ansatz für die benutzerdefinierte Steuerelement-Programmierung. Fügen Sie die folgende Liste von Funktionen auf Ihre Klassen selbst zeichnen:

- Für Schaltflächen selbst zeichnen:

    ```cpp
    CButton:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw this button
    ```

- Für Menüs selbst zeichnen:

    ```cpp
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
    // insert code to measure the size of an item in this menu
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
    // insert code to draw an item in this menu
    ```

- Für selbst zeichnen Listenfelder:

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

- Für selbst zeichnen Kombinationsfelder:

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

Ausführliche Informationen über die Ownerdrawn-Strukturen ([DRAWITEMSTRUCT](../mfc/reference/drawitemstruct-structure.md), [MEASUREITEMSTRUCT](../mfc/reference/measureitemstruct-structure.md), [COMPAREITEMSTRUCT](../mfc/reference/compareitemstruct-structure.md), und [DELETEITEMSTRUCT](../mfc/reference/deleteitemstruct-structure.md)) finden Sie in der Dokumentation MFC `CWnd::OnDrawItem`, `CWnd::OnMeasureItem`, `CWnd::OnCompareItem`, und `CWnd::OnDeleteItem` bzw.

## <a name="using-self-draw-controls-and-menus"></a>Verwenden von Steuerelementen selbst zeichnen und Menüs

Für Menüs selbst zu zeichnen, müssen Sie beide überschreiben die `OnMeasureItem` und `OnDrawItem` Methoden.

Sie müssen selbst zeichnen Listenfelder und Kombinationsfelder, überschreiben `OnMeasureItem` und `OnDrawItem`. Sie müssen den LBS_OWNERDRAWVARIABLE-Stil für Listenfelder oder CBS_OWNERDRAWVARIABLE-Stil für Kombinationsfelder in der Dialogfeldvorlage angeben. Styl OWNERDRAWFIXED funktioniert nicht mit der Elemente selbst zu zeichnen, da die Höhe des festen Elements bestimmt wird, bevor Steuerelemente selbst zeichnen in die Liste angefügt sind. (Sie können mithilfe der Methoden [CListBox::SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight) und [CComboBox::SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight) , diese Einschränkung zu umgehen.)

Wechsel zu einer OWNERDRAWVARIABLE Stil erzwingt, dass das System den NOINTEGRALHEIGHT-Stil auf das Steuerelement angewendet wird. Da das Steuerelement eine ganzzahlige Höhe mit variabler Größe berechnet werden kann, der Standardstil der INTEGRALHEIGHT wird ignoriert, und das Steuerelement ist immer NOINTEGRALHEIGHT. Wenn Ihre Elemente Höhe behoben sind, können Sie verhindern, dass Elemente, die durch die Angabe der Steuerelementgröße um eine ganze Zahl Multiplikator der Elementgröße gezeichnet wird.

Sie müssen für das Zeichnen Self, Listenfelder und Kombinationsfelder, die mit der Formatvorlage LBS_SORT oder CBS_SORT, überschreiben die `OnCompareItem` Methode.

Für das selbst zeichnen, Listenfelder und Kombinationsfelder, `OnDeleteItem` wird nicht in der Regel überschrieben. Sie können außer Kraft setzen `OnDeleteItem` , wenn Sie spezielle Verarbeitung ausführen möchten. Ein Fall, in denen diese anwendbar wäre, ist zusätzlichen Arbeitsspeicher oder andere Ressourcen zusammen mit jeder Listenfeldelement Listenfeld- oder Kombinationsfeld gespeichert werden.

## <a name="examples-of-self-drawing-controls-and-menus"></a>Beispiele für Steuerelemente und Menüs selbst zu zeichnen

Im allgemeinen MFC-Beispiel [CTRLTEST](../visual-cpp-samples.md) bietet Beispiele für ein Menü selbst zeichnen und ein Listenfeld mit selbst zeichnen.

Das häufigste Beispiel eine selbst zeichnen-Schaltfläche ist eine Bitmapschaltfläche. Eine Bitmapschaltfläche wird eine Schaltfläche, die einem, zwei oder drei Bitmap-Images für die unterschiedlichen Zustände angezeigt werden. Ein Beispiel hierfür finden Sie im MFC-Klasse [CBitmapButton](../mfc/reference/cbitmapbutton-class.md).

## <a name="dynamic-subclassing"></a>Dynamische Unterklassen

Gelegentlich möchten Sie die Funktionalität eines Objekts zu ändern, die bereits vorhanden ist. In den vorherigen Beispielen mussten Sie die Steuerelemente anpassen, bevor sie erstellt wurden. Dynamische Unterklassen können Sie einem Steuerelement anpassen, die bereits erstellt wurde.

Unterklasse ist der Windows-Begriff für das Ersetzen der [WndProc](http://msdn.microsoft.com/94ba8ffa-3c36-46d4-ac74-9bd10b1ffd26) eines Fensters mit einer benutzerdefinierten `WndProc` und das Aufrufen der alten `WndProc` für Standardfunktionen.

Dies sollte nicht mit der Ableitung von C++-Klassen verwechselt werden. Um Informationen, die C++-Begriffe *Basisklasse* und *abgeleitete Klasse* sind analog zu den *übergeordnete Klasse* und *Unterklasse* in die Windows Das Objektmodell. C++-Ableitung mit Unterklassen von MFC und Windows sind mit ähnlichen, außer dynamische Unterklassen von C++ nicht unterstützt wird.

Die `CWnd` -Klasse stellt die Verbindung zwischen einem C++-Objekt (abgeleitet `CWnd`) und ein Windows-Window-Objekt (bekannt als ein `HWND`).

Es gibt drei Möglichkeiten, die diese verknüpft sind:

- `CWnd` erstellt die `HWND`. Sie können das Verhalten in einer abgeleiteten Klasse ändern, indem das Erstellen einer Klasse abgeleitet `CWnd`. Die `HWND` wird erstellt, wenn die Anwendung aufruft [CWnd:: Create](../mfc/reference/cwnd-class.md#create).

- Die Anwendung fügt eine `CWnd` zu einem vorhandenen `HWND`. Das Verhalten der vorhandenen Fenster wird nicht geändert werden. Dies ist ein Fall der Delegierung und erfolgt durch Aufrufen von möglichen [CWnd::Attach](../mfc/reference/cwnd-class.md#attach) alias einer vorhandenen `HWND` zu einem `CWnd` Objekt.

- `CWnd` angefügt ist, zu einem vorhandenen `HWND` und Sie können das Verhalten in einer abgeleiteten Klasse ändern. Wird aufgerufen, dynamische Unterklassen, da wir das Verhalten, und daher die Klasse, eines Windows-Objekts zur Laufzeit ändern.

Erreichen Sie mithilfe der Methoden dynamische Unterklassen [CWnd:: SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow) und[CWnd::SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem).

Fügen Sie beiden Routinen ein `CWnd` Objekt zu einem vorhandenen `HWND`. `SubclassWindow` nimmt die `HWND` direkt. `SubclassDlgItem` ist eine Hilfsfunktion, die eine Steuerelement-ID und das übergeordnete Fenster verwendet. `SubclassDlgItem` Dient zum Anfügen von C++-Objekten für Dialogfeld-Steuerelemente, die aus einer Dialogfeldvorlage erstellt.

Finden Sie unter den [CTRLTEST](../visual-cpp-samples.md) Beispiel für mehrere Beispiele dafür, wann mit `SubclassWindow` und `SubclassDlgItem`.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)  
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)  
