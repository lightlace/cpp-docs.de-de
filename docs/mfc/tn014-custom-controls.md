---
title: "TN014: Benutzerdefinierte Steuerelemente | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benutzerdefinierte Steuerelemente [MFC]"
  - "TN014"
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# TN014: Benutzerdefinierte Steuerelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis beschreibt die MFC\-Unterstützung für benutzerdefinierte Ressource und Selbstzeichnungskontrollen.  Er beschreibt außerdem dynamische Erstellen von Unterklassen und beschreibt die Beziehung zwischen [CWnd](../mfc/reference/cwnd-class.md)\-Objekten und `HWND`s.  
  
 Die MFC\-Beispielanwendung CTRLTEST veranschaulicht, wie viele benutzerdefinierte Steuerelemente verwendet.  Siehe den Quellcode für das allgemeine Beispiel [CTRLTEST](../top/visual-cpp-samples.md) MFC und Onlinehilfe.  
  
## Ownerdrawn\-Kontrollen\/Menüs  
 Windows bietet Unterstützung für Ownerdrawnkontrollen und in Menüs von, indem Windows\-Meldungen verwendet.  Das übergeordnete Fenster eines beliebigen Steuerelements oder Menüs erhält diese Meldungen und ruft Funktionen in der Antwort auf.  Sie können diese Funktionen überschreiben, um das Erscheinungsbild und das Verhalten des Ownerdrawnsteuerelements in Menüs von oder anzupassen.  
  
 MFC unterstützt direkt Ownerdrawn mit den folgenden Features:  
  
-   [CWnd::OnDrawItem](../Topic/CWnd::OnDrawItem.md)  
  
-   [CWnd::OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)  
  
-   [CWnd::OnCompareItem](../Topic/CWnd::OnCompareItem.md)  
  
-   [CWnd::OnDeleteItem](../Topic/CWnd::OnDeleteItem.md)  
  
 Sie können diese Funktionen in der `CWnd` abgeleiteten Klasse überschreiben, um benutzerdefiniertes Verhalten Videofunktionen zu implementieren.  
  
 Dieser Ansatz wird nicht zu wiederverwendbaren Code.  Wenn Sie zwei ähnliche Steuerelemente in zwei verschiedenen `CWnd`\-Klassen haben, müssen Sie das Verhalten des benutzerdefinierten Steuerelements an zwei Orten implementieren.  Die MFC\-unterstützte Selbstzeichnungssteuerarchitektur wird das Problem.  
  
## Selbstzeichnungs\-Kontrollen und Menüs  
 MFC stellt eine Standardimplementierung \(in der `CWnd` und [CMenu](../mfc/reference/cmenu-class.md)\-Klassen\) für die Standardownerdrawnmeldungen bereit.  Diese Standardimplementierung decodiert die Ownerdrawnparameter und delegiert die Ownerdrawnmeldungen zu Steuerelementen oder dem Menü.  Dies wird Selbstzeichnung, da der Zeichencode in der Klasse des Steuerelements oder Menüs ist, nicht im Besitzerfenster aufgerufen.  
  
 Mit Selbstzeichnungskontrollen verwenden, können Sie wiederverwendbare Steuerelementklassen erstellen, die Ownerdrawnsemantik verwenden, um das Steuerelement anzuzeigen.  Der Code zum Zeichnen des Steuerelements ist in der Steuerelementklasse, nicht sein übergeordnetes Element.  Dies ist ein Ansatz zur objektorientierten Programmierung des benutzerdefinierten Steuerelements.  Fügen Sie der folgenden Liste mit den Funktionen Selbstzeichnungsklassen hinzu:  
  
-   Für Selbstzeichnungsschaltflächen:  
  
    ```  
    CButton:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw this button  
    ```  
  
-   Für Selbstzeichnungsmenüs:  
  
    ```  
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);  
            // insert code to measure the size of an item in this menu  
    CMenu:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw an item in this menu  
    ```  
  
-   Für Selbstzeichnungslistenfelder:  
  
    ```  
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);  
            // insert code to measure the size of an item in this list box  
    CListBox:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw an item in this list box  
  
    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);  
            // insert code to compare two items in this list box if LBS_SORT  
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);  
            // insert code to delete an item from this list box  
    ```  
  
-   Für Selbstzeichnungskombinationsfelder:  
  
    ```  
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);  
            // insert code to measure the size of an item in this combo box  
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw an item in this combo box  
  
    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);  
            // insert code to compare two items in this combo box if CBS_SORT  
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);  
            // insert code to delete an item from this combo box  
    ```  
  
 Ausführliche Informationen über die Ownerdrawnstrukturen \([DRAWITEMSTRUCT](../mfc/reference/drawitemstruct-structure.md), [MEASUREITEMSTRUCT](../mfc/reference/measureitemstruct-structure.md), [COMPAREITEMSTRUCT](../mfc/reference/compareitemstruct-structure.md) und [DELETEITEMSTRUCT](../mfc/reference/deleteitemstruct-structure.md)\) finden Sie die MFC\-Dokumentation für `CWnd::OnDrawItem`, `CWnd::OnMeasureItem`, `CWnd::OnCompareItem` bzw. `CWnd::OnDeleteItem`.  
  
## Verwenden der Selbstzeichnungskontrollen und in Menüs von  
 Für Selbstzeichnungsmenüs müssen Sie die Methoden `OnMeasureItem` und `OnDrawItem` überschreiben.  
  
 Für Selbstzeichnungslistenfelder und \-Kombinationsfelder müssen Sie `OnMeasureItem` und `OnDrawItem` überschreiben.  Sie müssen dem `LBS_OWNERDRAWVARIABLE` Format für Listenfelder oder `CBS_OWNERDRAWVARIABLE` Format für Kombinationsfelder in der Dialogfeldvorlage angeben.  Das Format `OWNERDRAWFIXED` funktioniert nicht mit Selbstzeichnungselementen, da die feste Elementhöhe bestimmt wird, bevor Selbstzeichnungskontrollen dem Listenfeld angefügt werden. \(Sie können die Methoden [CListBox::SetItemHeight](../Topic/CListBox::SetItemHeight.md) und [CComboBox::SetItemHeight](../Topic/CComboBox::SetItemHeight.md) verwenden, um diese Einschränkung zu beseitigen.\)  
  
 Wechseln zu einem Format `OWNERDRAWVARIABLE` erzwingt das System, um das Format `NOINTEGRALHEIGHT` auf das Steuerelement anzuwenden.  Da das Steuerelement eine integrale Höhe mit variablen groß \- Elementen nicht abgeleitet werden kann, ist der Standardstil von `INTEGRALHEIGHT` ignoriert und das Steuerelement ist immer `NOINTEGRALHEIGHT`.  Wenn die Elemente Höhe fest werden, können Sie Elemente an partielle gezeichneten verhindern, indem Sie der der Steuerelementgröße angeben, dass ein ganzzahliger Multiplikator der Elementgröße zu umfassen.  
  
 Für Selbstzeichnungslistenfelder und \-Kombinationsfelder mit dem Format `LBS_SORT` oder `CBS_SORT`, müssen Sie die `OnCompareItem`\-Methode überschreiben.  
  
 Für Selbstzeichnungslistenfelder und \-Kombinationsfelder ist `OnDeleteItem` normalerweise nicht überschrieben.  Sie können `OnDeleteItem` überschreiben, wenn Sie alle das spezielle Verarbeitung ausführen möchten.  Ein Fall, in dem dieser anwendbar ist, ist, wenn zusätzliche Arbeitsspeicher oder andere Ressourcen mit jedem Listenfeld\- oder ComboBox\-Steuerelement gespeichert werden.  
  
## Beispiele für Selbstzeichnungs\-Kontrollen und Menüs  
 Das allgemeine Beispiel [CTRLTEST](../top/visual-cpp-samples.md) MFC stellt Beispiele für Selbstzeichnungsmenüs und des Selbstzeichnungslistenfelds.  
  
 Das häufigste Beispiel einer Selbstzeichnungsschaltfläche ist eine Bitmapschaltfläche.  Eine Bitmapschaltfläche ist eine Schaltfläche, die eine, zwei oder drei Bitmapbilder für die unterschiedlichen Zustände anzeigt.  Ein Beispiel hierfür wird in der MFC\-Klasse [CBitmapButton](../mfc/reference/cbitmapbutton-class.md).  
  
## Dynamische Erstellen von Unterklassen  
 Gelegentlich möchten Sie die Funktionalität eines Objekt ändern, das bereits vorhanden ist.  In den vorherigen Beispielen benötigen Sie, Steuerelemente anzupassen, bevor sie erstellt wurden.  Dynamische Erstellen von Unterklassen ermöglichen Ihnen, ein Steuerelement an, das bereits erstellt wurde.  
  
 Erstellen von Unterklassen sind der Windows\-Begriff zum Ersetzen [WndProc](assetId:///94ba8ffa-3c36-46d4-ac74-9bd10b1ffd26) eines Fensters mit benutzerdefinierten `WndProc` und Aufruf alten `WndProc` für Standardfunktionalität.  
  
 Dies darf nicht mit C\+\+\-Klassenableitung verwechselt werden.  Ausführliche Erläuterung sind die C\+\+\-Begriffe *Basisklasse* und *die abgeleitete Klasse* *übergeordneten Klasse* analog und *ordnen* im Windows\-Objektmodell unter.  C\+\+\-Ableitung mit MFC\- und Windows\-Unterordnen sind funktional ähnlich, außer C\+\+ nicht dynamischen Erstellen von Unterklassen unterstützt.  
  
 Die `CWnd`\-Klasse stellt die Verbindung zwischen ein C\+\+\-Objekt \(abgeleitet von `CWnd`\) und einem Windows\-Fensterobjekt \(bezeichnet als `HWND`\).  
  
 Es gibt drei übliche Möglichkeiten, die diese verknüpft sind:  
  
-   `CWnd` `HWND` erstellt.  Sie können das Verhalten in einer abgeleiteten Klasse ändern, indem Sie eine Klasse erstellen, die von `CWnd` abgeleitet wird.  `HWND` wird erstellt, wenn die Anwendung [CWnd::Create](../Topic/CWnd::Create.md).  
  
-   Die Anwendung fügt `CWnd` zu vorhandenen `HWND`.  Das Verhalten des vorhandenen Fensters wird nicht geändert.  Dies ist ein Fall der Delegierung möglich und wird ausgeführt, indem es [CWnd::Attach](../Topic/CWnd::Attach.md) \- Alias vorhandenes `HWND` auf ein `CWnd`\-Objekt aufruft.  
  
-   `CWnd` wird zu vorhandenen `HWND` angefügt und Sie können das Verhalten in einer abgeleiteten Klasse ändern.  Dies wird dynamische Erstellen von Unterklassen aus, weil wir das Verhalten ändern, sodass die Klasse, eines Windows\-Objekts zur Laufzeit bezeichnet.  
  
 Sie können dynamische Erstellen von Unterklassen erzielen, indem Sie die Methoden [CWnd::SubclassWindow](../Topic/CWnd::SubclassWindow.md) und [CWnd::SubclassDlgItem](../Topic/CWnd::SubclassDlgItem.md) verwenden.  
  
 Beide Routinen fügen ein `CWnd`\-Objekt zu vorhandenen `HWND`.  `SubclassWindow` erfordert `HWND` direkt.  `SubclassDlgItem` ist eine Hilfsfunktion, die eine Steuerelement\-ID und das übergeordnete Fenster führt.  `SubclassDlgItem` ist für das Anfügen von C\+\+\-Objekten zu den Dialogfeldkontrollen vorgesehen, die von einer Dialogfeldvorlage erstellt werden.  
  
 Siehe das Beispiel [CTRLTEST](../top/visual-cpp-samples.md) für einige Beispiele dafür, wann `SubclassWindow` und `SubclassDlgItem` verwendet.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)