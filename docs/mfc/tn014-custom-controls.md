---
title: 'TN014: Benutzerdefinierte Steuerelemente | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.controls
dev_langs: C++
helpviewer_keywords:
- TN014
- custom controls [MFC]
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4ffc4f26ed365673cdfb525c2bf3653827cc4ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn014-custom-controls"></a>TN014: Benutzerdefinierte Steuerelemente
Dieser Hinweis beschreibt die MFC-Unterstützung für benutzerdefinierte und selbst zeichnen-Steuerelemente. Außerdem wird die dynamische Erstellung von Unterklassen von beschrieben, und beschreibt die Beziehung zwischen [CWnd](../mfc/reference/cwnd-class.md) Objekte und `HWND`s.  
  
 Die MFC-beispielanwendung CTRLTEST wird veranschaulicht, wie viele benutzerdefinierte Steuerelemente verwenden. Finden Sie im Quellcode für den allgemeinen MFC-Beispiel [CTRLTEST](../visual-cpp-samples.md) und online-Hilfe.  
  
## <a name="owner-draw-controlsmenus"></a>Ownerdrawn-Steuerelemente /-Menüs  
 Windows bietet Unterstützung für Ownerdrawn-Steuerelemente und Menüs, mit der Windows-Meldungen. Das übergeordnete Fenster eines Steuerelements oder im Menü empfängt diese Nachrichten und Anrufe-Funktionen in der Antwort. Sie können diese Funktionen zum Anpassen des visuelle Darstellung und Verhalten der Besitzer gezeichnetes Steuerelement oder Menü überschreiben.  
  
 MFC unterstützt direkt Ownerdrawn-mit den folgenden Funktionen:  
  
- [CWnd::OnDrawItem](../mfc/reference/cwnd-class.md#ondrawitem)  
  
- [CWnd::OnMeasureItem](../mfc/reference/cwnd-class.md#onmeasureitem)  
  
- [CWnd::OnCompareItem](../mfc/reference/cwnd-class.md#oncompareitem)  
  
- [CWnd::OnDeleteItem](../mfc/reference/cwnd-class.md#ondeleteitem)  
  
 Sie können diese Funktionen in überschreiben Ihre `CWnd` abgeleitete Klasse zum benutzerdefinierten Zeichnen Verhalten zu implementieren.  
  
 Dieser Ansatz ist nicht zu wiederverwendbarem Code führen. Wenn sich zwei Steuerelemente mit ähnlichen Funktionen in zwei verschiedenen `CWnd` Klassen, müssen Sie das Verhalten des benutzerdefinierten Steuerelements an zwei Orten implementieren. Die MFC-Unterstützung selbst zeichnen Steuerarchitektur löst dieses Problem.  
  
## <a name="self-draw-controls-and-menus"></a>Self-zeichnen Sie Steuerelemente und Menüs  
 MFC stellt eine Standardimplementierung (in der `CWnd` und [CMenu](../mfc/reference/cmenu-class.md) Klassen) für die standard-Ownerdrawn-Nachrichten. Diese Standardimplementierung wird die Ownerdrawn-Parameter zu decodieren und die Ownerdrawn-Nachrichten an den Steuerelementen oder im Menü delegieren können. Dies wird selbst zeichnen bezeichnet, da der Code zum Zeichnen der Klasse des Steuerelements oder im Menü nicht in das besitzende Fenster wird.  
  
 Mithilfe der Steuerelemente selbst zeichnen können Sie wiederverwendbare Klassen erstellen, die Ownerdrawn-Semantik verwendet wird, um das Steuerelement anzuzeigen. Der Code zum Zeichnen des Steuerelements wird in der Steuerelementklasse nicht seinem übergeordneten Element. Dies ist ein mit dem objektorientierten Ansatz für die benutzerdefinierte Steuerelement-Programmierung. Fügen Sie die folgende Liste von Funktionen in Ihren Klassen selbst zeichnen hinzu:  
  
-   Für selbst zeichnen Schaltflächen:  
  
 ```  
    CButton:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw this button  
 ```  
  
-   Für selbst zeichnen Menüs:  
  
 ```  
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this menu  
    CMenu:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this menu  
 ```  
  
-   Für selbst zeichnen Listenfelder:  
  
 ```  
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this list box  
    CListBox:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this list box  
 
    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);
*// insert code to compare two items in this list box if LBS_SORT  
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);
*// insert code to delete an item from this list box  
 ```  
  
-   Für selbst zeichnen Kombinationsfelder:  
  
 ```  
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);
*// insert code to measure the size of an item in this combo box  
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);
*// insert code to draw an item in this combo box  
 
    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);
*// insert code to compare two items in this combo box if CBS_SORT  
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);
*// insert code to delete an item from this combo box  
 ```  
  
 Ausführliche Informationen über die Ownerdrawn-Strukturen ([DRAWITEMSTRUCT](../mfc/reference/drawitemstruct-structure.md), [MEASUREITEMSTRUCT](../mfc/reference/measureitemstruct-structure.md), [COMPAREITEMSTRUCT](../mfc/reference/compareitemstruct-structure.md), und [DELETEITEMSTRUCT](../mfc/reference/deleteitemstruct-structure.md)) finden Sie in der MFC-Dokumentation für `CWnd::OnDrawItem`, `CWnd::OnMeasureItem`, `CWnd::OnCompareItem`, und `CWnd::OnDeleteItem` bzw.  
  
## <a name="using-self-draw-controls-and-menus"></a>Mit den Steuerelementen selbst zeichnen und Menüs  
 Für Menüs selbst zeichnen, müssen Sie beide überschreiben die `OnMeasureItem` und `OnDrawItem` Methoden.  
  
 Für selbst zeichnen Listenfelder und Kombinationsfelder, müssen Sie überschreiben `OnMeasureItem` und `OnDrawItem`. Sie müssen angeben, die `LBS_OWNERDRAWVARIABLE` Stil für Listenfelder oder `CBS_OWNERDRAWVARIABLE` Stil für Kombinationsfelder, die in der Dialogfeldvorlage Felder. Die `OWNERDRAWFIXED` Stil selbst funktioniert nicht mit Elemente selbst zeichnen, da die Höhe des festen Elements bestimmt wird, bevor selbst zeichnen-Steuerelemente in das Listenfeld angefügt sind. (Sie können mithilfe der Methoden [CListBox::SetItemHeight](../mfc/reference/clistbox-class.md#setitemheight) und [CComboBox::SetItemHeight](../mfc/reference/ccombobox-class.md#setitemheight) , diese Einschränkung zu umgehen.)  
  
 Wechsel zu einer `OWNERDRAWVARIABLE` Stil erzwingt das System Anwenden der `NOINTEGRALHEIGHT` Stil für das Steuerelement. Da das Steuerelement eine Gesamthöhe mit variabler Größe berechnen kann Elemente, den Standardstil der `INTEGRALHEIGHT` wird ignoriert, und das Steuerelement ist immer `NOINTEGRALHEIGHT`. Wenn Ihre Elemente Höhe behoben sind, können Sie verhindern, dass Elemente abgeschnitten durch Angabe der Steuerelementgröße, um eine ganze Zahl Multiplikator der Elementgröße werden gezeichnet werden.  
  
 Für das Self-zeichnen, Listenfelder und Kombinationsfelder, mit der `LBS_SORT` oder `CBS_SORT` Stil, müssen Sie überschreiben die `OnCompareItem` Methode.  
  
 Für das Self-zeichnen, Listenfelder und Kombinationsfelder, `OnDeleteItem` normalerweise nicht überschrieben. Sie können außer Kraft setzen `OnDeleteItem` Wenn jegliche spezielle Verarbeitung ausgeführt werden sollen. Einen Fall, in dem anwendbar dies wäre, wird mit jeder Listenfeldelement oder Kombinationsfeld zusätzlichen Arbeitsspeicher oder andere Ressourcen gespeichert sind.  
  
## <a name="examples-of-self-drawing-controls-and-menus"></a>Beispiele für Steuerelemente und Menüs selbst zeichnen  
 Im allgemeinen MFC-Beispiel [CTRLTEST](../visual-cpp-samples.md) bietet Beispiele für ein Menü selbst zeichnen und eines Listenfelds mit sich selbst zu zeichnen.  
  
 Das liegt meist daran Beispiel eine selbst zeichnen-Schaltfläche ist eine Bitmapschaltfläche. Eine Bitmapschaltfläche ist eine Schaltfläche, die einem, zwei oder drei Bitmap-Images für die verschiedenen Zustände angezeigt werden. Ein Beispiel hierfür finden Sie im MFC-Klasse [CBitmapButton](../mfc/reference/cbitmapbutton-class.md).  
  
## <a name="dynamic-subclassing"></a>Dynamische Erstellung von Unterklassen von  
 Gelegentlich möchten die Funktionalität eines Objekts ändern, die bereits vorhanden ist. In den vorherigen Beispielen erforderte die Steuerelemente anpassen, bevor sie erstellt wurden. Dynamische Erstellung von Unterklassen von ermöglicht es Ihnen, ein Steuerelement anzupassen, die bereits erstellt wurde.  
  
 Unterklassen ist der Windows-Begriff zum Ersetzen der [WndProc](http://msdn.microsoft.com/en-us/94ba8ffa-3c36-46d4-ac74-9bd10b1ffd26) eines Fensters mit einer benutzerdefinierten `WndProc` und Aufrufen der alte `WndProc` für Standardfunktionen.  
  
 Dies sollte nicht mit C++ klassenableitung verwechselt werden. Um Informationen, die C++-Begriffe *Basisklasse* und *abgeleitete Klasse* sind analog zu den *übergeordneten* und *Unterklasse* in Windows Objektmodell. C++-Ableitung mit Erstellung von Unterklassen von MFC und Windows sind mit ähnlichen, außer C++ die dynamische Erstellung von Unterklassen von nicht unterstützt.  
  
 Die `CWnd` -Klasse stellt die Verbindung zwischen einem C++-Objekt (abgeleitet `CWnd`) und einem Windows-Fensterobjekt (bekannt als ein `HWND`).  
  
 Es gibt drei Arten, die diese verknüpft sind:  
  
- `CWnd`erstellt die `HWND`. Sie können das Verhalten in einer abgeleiteten Klasse durch Erstellen einer Klasse abgeleitet wurde. ändern `CWnd`. Die `HWND` wird erstellt, wenn die Anwendung aufruft [CWnd:: Create](../mfc/reference/cwnd-class.md#create).  
  
-   Die Anwendung fügt eine `CWnd` zu einem vorhandenen `HWND`. Das Verhalten des Fensters vorhandenen wird nicht geändert. Dies ist ein Fall der Delegierung und erfolgt durch Aufrufen von möglichen [CWnd::Attach](../mfc/reference/cwnd-class.md#attach) alias einer vorhandenen `HWND` zu einem `CWnd` Objekt.  
  
- `CWnd`gehört zu einem vorhandenen `HWND` und Sie können das Verhalten in einer abgeleiteten Klasse ändern. Hierbei spricht dynamische Unterklasse erstellen, da wir das Verhalten und daher die Klasse eines Windows-Objekts zur Laufzeit geändert werden.  
  
 Sie können dynamische Erstellung von Unterklassen von erzielen, indem Sie die Methoden [CWnd:: SubclassWindow](../mfc/reference/cwnd-class.md#subclasswindow) und[CWnd::SubclassDlgItem](../mfc/reference/cwnd-class.md#subclassdlgitem).  
  
 Fügen Sie beide Routinen eine `CWnd` zu einem vorhandenen Objekt `HWND`. `SubclassWindow`nimmt die `HWND` direkt. `SubclassDlgItem`ist eine Hilfsfunktion, die eine Steuerelement-ID und das übergeordnete Fenster annimmt. `SubclassDlgItem`Dient zum Anfügen von C++-Objekte für Dialogfeld-Steuerelemente, die aus einer Dialogfeldvorlage erstellt.  
  
 Finden Sie unter der [CTRLTEST](../visual-cpp-samples.md) Beispiel mehrere Beispiele für die Verwendung von `SubclassWindow` und `SubclassDlgItem`.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

