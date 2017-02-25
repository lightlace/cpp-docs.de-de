---
title: "CComboBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComboBox-Klasse"
  - "Kombinationsfelder, CComboBox objects"
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität eines Windows\-Kombinationsfelds bereit.  
  
## Syntax  
  
```  
class CComboBox : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComboBox::CComboBox](../Topic/CComboBox::CComboBox.md)|Erstellt ein `CComboBox`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComboBox::AddString](../Topic/CComboBox::AddString.md)|Fügt eine Zeichenfolge dem Ende der Liste im Listenfeld eines Kombinationsfelds oder in der sortierten Position für Listenfelder mit dem **CBS\_SORT** Format hinzu.|  
|[CComboBox::Clear](../Topic/CComboBox::Clear.md)|Löscht die \(Leerzeichen\) die aktuelle Auswahl ggf. im Bearbeitungssteuerelement.|  
|[CComboBox::CompareItem](../Topic/CComboBox::CompareItem.md)|Aufgerufen vom Framework, um die relative Position eines neuen Listenelements in einem sortierten Ownerdrawnkombinationsfeld zu bestimmen.|  
|[CComboBox::Copy](../Topic/CComboBox::Copy.md)|Kopiert die aktuelle Auswahl ggf. auf die Zwischenablage in **CF\_TEXT** Format.|  
|[CComboBox::Create](../Topic/CComboBox::Create.md)|Stellt das Kombinationsfeld erstellt und fügt es an den `CComboBox`\-Objekt.|  
|[CComboBox::Cut](../Topic/CComboBox::Cut.md)|Löscht \(Schnitte\) die aktuelle Auswahl ggf. im Bearbeitungssteuerelement sowie in den Kopien der gelöschte Text in die Zwischenablage in **CF\_TEXT** Format.|  
|[CComboBox::DeleteItem](../Topic/CComboBox::DeleteItem.md)|Aufgerufen vom Framework ausgelöst, wenn ein Listenelement von einem Ownerdrawnkombinationsfeld gelöscht wird.|  
|[CComboBox::DeleteString](../Topic/CComboBox::DeleteString.md)|Löscht eine Zeichenfolge im Listenfeld eines Kombinationsfelds.|  
|[CComboBox::Dir](../Topic/CComboBox::Dir.md)|Fügt eine Liste von Dateinamen dem Listenfeld eines Kombinationsfelds hinzu.|  
|[CComboBox::DrawItem](../Topic/CComboBox::DrawItem.md)|Aufgerufen vom Framework ausgelöst, wenn ein visueller Aspekt eines Ownerdrawnkombinationsfelds ändert.|  
|[CComboBox::FindString](../Topic/CComboBox::FindString.md)|Sucht die erste Zeichenfolge, die das angegebene Präfix im Listenfeld eines Kombinationsfelds enthält.|  
|[CComboBox::FindStringExact](../Topic/CComboBox::FindStringExact.md)|Sucht die erste Listenfeldzeichenfolge \(in einem Kombinationsfeld\) diese entspricht die angegebene Zeichenfolge.|  
|[CComboBox::GetComboBoxInfo](../Topic/CComboBox::GetComboBoxInfo.md)|Ruft Informationen zum `CComboBox`\-Objekt ab.|  
|[CComboBox::GetCount](../Topic/CComboBox::GetCount.md)|Ruft die Anzahl der Elemente im Listenfeld eines Kombinationsfelds ab.|  
|[CComboBox::GetCueBanner](../Topic/CComboBox::GetCueBanner.md)|Ruft den Hinweistext ab, der für ein Kombinationsfeld\-Steuerelement angezeigt wird.|  
|[CComboBox::GetCurSel](../Topic/CComboBox::GetCurSel.md)|Ruft den Index des aktuell ausgewählten Elements ggf. im Listenfeld eines Kombinationsfelds ab.|  
|[CComboBox::GetDroppedControlRect](../Topic/CComboBox::GetDroppedControlRect.md)|Ruft die Bildschirmkoordinaten des sichtbaren \(unten abgelegt\) eines Listenfelds Dropdown\-Kombinationsfelds ab.|  
|[CComboBox::GetDroppedState](../Topic/CComboBox::GetDroppedState.md)|Bestimmt, ob das Listenfeld eines Dropdown\-Kombinationsfelds sichtbar ist \(unten\) abgelegt.|  
|[CComboBox::GetDroppedWidth](../Topic/CComboBox::GetDroppedWidth.md)|Ruft die minimale zulässigen Breite für den Dropdown\-Listenfeld\-Teil eines Kombinationsfelds ab.|  
|[CComboBox::GetEditSel](../Topic/CComboBox::GetEditSel.md)|Ruft die beginnenden und Endzeichenpositionen der aktuellen Auswahl im Bearbeitungssteuerelement eines Kombinationsfelds ab.|  
|[CComboBox::GetExtendedUI](../Topic/CComboBox::GetExtendedUI.md)|Bestimmt, ob ein Kombinationsfeld die Standardbenutzeroberfläche oder die erweiterte Benutzeroberfläche.|  
|[CComboBox::GetHorizontalExtent](../Topic/CComboBox::GetHorizontalExtent.md)|Gibt die Breite in Pixel zurück, die der Listenfeldbereich des Kombinationsfelds horizontalen Bildlauf durchgeführt werden kann.|  
|[CComboBox::GetItemData](../Topic/CComboBox::GetItemData.md)|Ruft den von der Anwendung bereitgestellten 32\-Bit\-Wert ab, der mit dem angegebenen Kombinationsfeldelement zugeordnet ist.|  
|[CComboBox::GetItemDataPtr](../Topic/CComboBox::GetItemDataPtr.md)|Ruft den von der Anwendung bereitgestellten 32\-Bit\-Zeiger ab, der mit dem angegebenen Kombinationsfeldelement zugeordnet ist.|  
|[CComboBox::GetItemHeight](../Topic/CComboBox::GetItemHeight.md)|Ruft die Höhe Listenelemente in einem Kombinationsfeld ab.|  
|[CComboBox::GetLBText](../Topic/CComboBox::GetLBText.md)|Ruft eine Zeichenfolge im Listenfeld eines Kombinationsfelds ab.|  
|[CComboBox::GetLBTextLen](../Topic/CComboBox::GetLBTextLen.md)|Ruft die Länge einer Zeichenfolge im Listenfeld eines Kombinationsfelds ab.|  
|[CComboBox::GetLocale](../Topic/CComboBox::GetLocale.md)|Ruft den Gebietsschemabezeichner für ein Kombinationsfeld ab.|  
|[CComboBox::GetMinVisible](../Topic/CComboBox::GetMinVisible.md)|Ruft die Mindestanzahl der sichtbaren Elemente in der Dropdownliste des aktuellen Kombinationsfelds ab.|  
|[CComboBox::GetTopIndex](../Topic/CComboBox::GetTopIndex.md)|Gibt den Index des ersten Elements sichtbaren im Listenfeldbereich des Kombinationsfelds zurück.|  
|[CComboBox::InitStorage](../Topic/CComboBox::InitStorage.md)|Teilt Speicherblöcke für Elemente und Zeichenfolgen im Listenfeldbereich des Kombinationsfelds auf.|  
|[CComboBox::InsertString](../Topic/CComboBox::InsertString.md)|Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds ein.|  
|[CComboBox::LimitText](../Topic/CComboBox::LimitText.md)|Beschränkt die Länge des Texts ein, den der Benutzer in das Bearbeitungssteuerelement eines Kombinationsfelds eingeben kann.|  
|[CComboBox::MeasureItem](../Topic/CComboBox::MeasureItem.md)|Aufgerufen durch das Framework, um Kombinationsfelddimensionen zu bestimmen, ob ein Ownerdrawnkombinationsfeld erstellt wird.|  
|[CComboBox::Paste](../Topic/CComboBox::Paste.md)|Fügt die Daten aus der Zwischenablage in das Bearbeitungssteuerelement in der aktuellen Cursorposition ein.  Daten eingefügt werden, wenn die Zwischenablage Daten in **CF\_TEXT** Format enthält.|  
|[CComboBox::ResetContent](../Topic/CComboBox::ResetContent.md)|Entfernt alle Elemente aus dem Listenfeld und vom Bearbeitungssteuerelement eines Kombinationsfelds.|  
|[CComboBox::SelectString](../Topic/CComboBox::SelectString.md)|Sucht eine Zeichenfolge im Listenfeld eines Kombinationsfelds und, wenn die Zeichenfolge gefunden wird, wählt die Zeichenfolge im Listenfeld und kopiert die Zeichenfolge an den Bearbeitungssteuerelement.|  
|[CComboBox::SetCueBanner](../Topic/CComboBox::SetCueBanner.md)|Legt den Hinweistext fest, der für ein Kombinationsfeld\-Steuerelement angezeigt wird.|  
|[CComboBox::SetCurSel](../Topic/CComboBox::SetCurSel.md)|Wählt eine Zeichenfolge im Listenfeld eines Kombinationsfelds aus.|  
|[CComboBox::SetDroppedWidth](../Topic/CComboBox::SetDroppedWidth.md)|Legt die minimale zulässigen Breite für den Dropdown\-Listenfeld\-Teil eines Kombinationsfelds fest.|  
|[CComboBox::SetEditSel](../Topic/CComboBox::SetEditSel.md)|Wählt Zeichen im Bearbeitungssteuerelement eines Kombinationsfelds aus.|  
|[CComboBox::SetExtendedUI](../Topic/CComboBox::SetExtendedUI.md)|Wählt entweder die Standardbenutzeroberfläche oder die erweiterte Benutzeroberfläche für ein Kombinationsfeld aus, das das **CBS\_DROPDOWN** oder **CBS\_DROPDOWNLIST** Format hat.|  
|[CComboBox::SetHorizontalExtent](../Topic/CComboBox::SetHorizontalExtent.md)|Gibt die Breite in Pixel fest, die der Listenfeldbereich des Kombinationsfelds horizontalen Bildlauf durchgeführt werden kann.|  
|[CComboBox::SetItemData](../Topic/CComboBox::SetItemData.md)|Legt den 32\-Bit\-Wert fest, der mit dem angegebenen Element in einem Kombinationsfeld zugeordnet ist.|  
|[CComboBox::SetItemDataPtr](../Topic/CComboBox::SetItemDataPtr.md)|Legt den 32\-Bit\-Zeiger fest, der mit dem angegebenen Element in einem Kombinationsfeld zugeordnet ist.|  
|[CComboBox::SetItemHeight](../Topic/CComboBox::SetItemHeight.md)|Gibt die Höhe Listenelemente in einem Kombinationsfeld oder die Höhe des Teils des Edit\-Steuerelements \(oder statischen Text\) eines Kombinationsfelds fest.|  
|[CComboBox::SetLocale](../Topic/CComboBox::SetLocale.md)|Legt den Gebietsschemabezeichner für ein Kombinationsfeld fest.|  
|[CComboBox::SetMinVisibleItems](../Topic/CComboBox::SetMinVisibleItems.md)|Legt die Mindestanzahl der sichtbaren Elemente in der Dropdownliste des aktuellen Kombinationsfelds fest.|  
|[CComboBox::SetTopIndex](../Topic/CComboBox::SetTopIndex.md)|Weist den Listenfeldbereich des Kombinationsfelds mit, um das Element mit dem angegebenen Index zu anzuzeigen.|  
|[CComboBox::ShowDropDown](../Topic/CComboBox::ShowDropDown.md)|Zeigt an oder blendet das Listenfeld eines Kombinationsfelds aus, das das **CBS\_DROPDOWN** oder **CBS\_DROPDOWNLIST** Format hat.|  
  
## Hinweise  
 Ein Kombinationsfeld besteht aus einem Listenfeld, das entweder mit einem statischen Steuerelement oder Bearbeitungssteuerelement kombiniert wird.  Der Listenfeldbereich des Steuerelements wird möglicherweise angezeigt jederzeit oder legt möglicherweise nur unten ab, wenn der Benutzer den Dropdownpfeil angezeigt.  
  
 Das derzeit ausgewählte Element \(falls vorhanden\) im Listenfeld wird in dem statischen oder im Bearbeitungssteuerelement angezeigt.  Wenn das Kombinationsfeld das Dropdownlistenformat hat, kann der Benutzer das erste Zeichen eines der Elemente in der Liste eingeben, und das Listenfeld, wenn sichtbar, hebt den nächsten Element mit diesem ersten Zeichen hervor.  
  
 In der folgenden Tabelle wird das Kombinationsfeld drei [Stile](../../mfc/reference/combo-box-styles.md).  
  
|Format|Wann wird Listenfeld sichtbar?|Statisch oder Bearbeitungssteuerelement?|  
|------------|------------------------------------|----------------------------------------------|  
|Einfach|Immer|Edit|  
|Dropdownlisten|Wenn Sie unten abgelegt werden|Edit|  
|Dropdownliste|Wenn Sie unten abgelegt werden|Static|  
  
 Sie können ein `CComboBox`\-Objekt entweder einer Dialogfeldvorlage oder direkt im Code erstellen.  In beiden Fällen zunächst der Konstruktor `CComboBox`, um `CComboBox` des Objekts zu erstellen; Rufen Sie dann die [Erstellen Sie](../Topic/CComboBox::Create.md)\-Memberfunktion auf, um das Steuerelement zu erstellen und auf `CComboBox`\-Objekt anzufügen.  
  
 Wenn Sie Windows\-Benachrichtigungsmeldungen bearbeiten möchten, die von einem Kombinationsfeld zu seinem übergeordneten Element gesendet werden \(normalerweise eine Klasse wird von abgeleitet `CDialog`\), fügen Sie eine Meldungszuordnungseintrags\- und Meldungshandlermemberfunktion der übergeordneten Klasse für jede Meldung hinzu.  
  
 Jeder Eintrag in der Meldungszuordnung weist folgende Form auf:  
  
 **ON\_** Benachrichtigung **\(**`id`**,**`memberFxn`**\)**  
  
 wobei `id` die ID des untergeordneten Fensters des sendenden Kombinationsfeldsteuerelements angibt, ist die Benachrichtigungen und `memberFxn` der Name der übergeordneten Memberfunktion, die Sie geschrieben haben, um die Benachrichtigung zu bearbeiten.  
  
 Der Funktionsprototyp des übergeordneten Elements ist, wie folgt:  
  
 **afx\_msg** `void` `memberFxn` **\(**\);  
  
 Die Reihenfolge, in der bestimmte Benachrichtigungen gesendet werden, kann nicht vorhergesagt werden.  Insbesondere wird eine Benachrichtigung **CBN\_SELCHANGE** möglicherweise entweder vor oder nach einer **CBN\_CLOSEUP** Benachrichtigung auf.  
  
 Mögliche Meldungszuordnungseinträge sind die folgenden:  
  
-   **ON\_CBN\_CLOSEUP** \(Windows 3.1 und höher\). Im Listenfeld eines Kombinationsfelds geschlossen hat.  Diese Benachrichtigung wird nicht für ein Kombinationsfeld gesendet, das das [CBS\_SIMPLE](../../mfc/reference/combo-box-styles.md) Format hat.  
  
-   **ON\_CBN\_DBLCLK** der Benutzer doppelklickt auf eine Zeichenfolge im Listenfeld eines Kombinationsfelds.  Diese Benachrichtigung wird nur für ein Kombinationsfeld mit dem **CBS\_SIMPLE** Format gesendet.  Ein Kombinationsfeld mit dem [CBS\_DROPDOWN](../../mfc/reference/combo-box-styles.md) oder [CBS\_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) Format, kann ein Doppelklick nicht auftreten, da ein einzelnen Mausklick das Listenfeld ausblendet.  
  
-   **ON\_CBN\_DROPDOWN** das Listenfeld eines Kombinationsfelds ist im Begriff, unten abzulegen \(sind sichtbar gemacht Sie\).  Diese Benachrichtigung kann nur für ein Kombinationsfeld mit dem **CBS\_DROPDOWN** oder **CBS\_DROPDOWNLIST** Format auftreten.  
  
-   **ON\_CBN\_EDITCHANGE** hat der Benutzer Aktionen ausgeführt, die den Text im Edit\-Steuerelement\-Teil eines Kombinationsfelds geändert.  Im Gegensatz zur **CBN\_EDITUPDATE** Meldung wird diese Meldung gesendet, nachdem Windows den Bildschirm aktualisiert.  Es wird nicht gesendet, wenn das Kombinationsfeld **CBS\_DROPDOWNLIST** hat das Format.  
  
-   **ON\_CBN\_EDITUPDATE** der Edit\-Steuerelement\-Teil eines Kombinationsfelds ist ungefähr zur Anzeige geändertem Text.  Diese Benachrichtigung gesendet wird, nachdem das Steuerelement den Text formatiert hat, aber bevor der Text anzeigt.  Es wird nicht gesendet, wenn das Kombinationsfeld **CBS\_DROPDOWNLIST** hat das Format.  
  
-   **ON\_CBN\_ERRSPACE** das Kombinationsfeld kann nicht genügend Arbeitsspeicher zuordnen, um eine bestimmte Anforderung zu erfüllen.  
  
-   **ON\_CBN\_SELENDCANCEL** \(Windows 3.1 und höher\). Gibt die Auswahl des Benutzers sollte abgebrochen werden.  Der Benutzer klickt auf ein Element klickt und dann ein anderes Fenster oder Steuerelement auf, um das Listenfeld eines Kombinationsfelds auszublenden.  Diese Benachrichtigung wird vor der **CBN\_CLOSEUP** Benachrichtigung gesendet, um anzugeben, dass die Auswahl des Benutzers ignoriert werden soll.  Die **CBN\_SELENDCANCEL** oder **CBN\_SELENDOK** Benachrichtigung gesendet wird, wenn die **CBN\_CLOSEUP** Benachrichtigungsmeldung nicht übermittelt wird \(wie im Fall eines Kombinationsfelds mit dem **CBS\_SIMPLE** Format\).  
  
-   **ON\_CBN\_SELENDOK** wählt der Benutzer ein Element aus und dann entweder drückt die EINGABETASTE oder klickt auf die NACH\-UNTEN\-TASTE, um das Listenfeld eines Kombinationsfelds auszublenden.  Diese Benachrichtigung wird vor der **CBN\_CLOSEUP** Meldung gesendet, um anzugeben, dass die Auswahl des Benutzers als gültig betrachtet werden sollte.  Die **CBN\_SELENDCANCEL** oder **CBN\_SELENDOK** Benachrichtigung gesendet wird, wenn die **CBN\_CLOSEUP** Benachrichtigungsmeldung nicht übermittelt wird \(wie im Fall eines Kombinationsfelds mit dem **CBS\_SIMPLE** Format\).  
  
-   **ON\_CBN\_KILLFOCUS** das Kombinationsfeld verliert den Eingabefokus.  
  
-   **ON\_CBN\_SELCHANGE** die Auswahl im Listenfeld eines Kombinationsfelds ist im Begriff, aufgrund des Benutzers geändert werden, der im Listenfeld klickt oder die Auswahl ändert, indem die Pfeiltasten verwendet.  Wenn Sie diese Meldung verarbeitet, kann der Text im Bearbeitungssteuerelement des Kombinationsfelds über `GetLBText` oder eine andere ähnliche Funktion nur abgerufen werden.  `GetWindowText` kann nicht verwendet werden.  
  
-   **ON\_CBN\_SETFOCUS** das Kombinationsfeld empfängt den Eingabefokus.  
  
 Wenn Sie ein `CComboBox`\-Objekt innerhalb eines Dialogfelds \(durch eine Dialogfeldressource\) erstellen, wird das Objekt `CComboBox` automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie ein `CComboBox`\-Objekt innerhalb eines anderen Fensterobjekts einbetten, müssen Sie nicht, um es zu zerstören.  Wenn Sie das `CComboBox`\-Objekt auf dem Stapel erstellen, wird er automatisch zerstört.  Wenn Sie das `CComboBox`\-Objekt auf dem Heap erstellen, indem Sie die **new**\-Funktion verwenden, müssen Sie **delete** für das Objekt aufrufen, um es zu zerstören, wenn das Windows\-Kombinationsfeld zerstört wird.  
  
 **Hinweis**, wenn Sie `WM_KEYDOWN` und `WM_CHAR` Meldungen bearbeiten möchten, müssen Sie die Bearbeitung und die Listenfeld\-Steuerelemente Kombinationsfelds unterordnen, Klassen von `CEdit` und von `CListBox` berechnen, und Handler für diese Nachrichten abgeleiteten Klassen hinzufügen.  Weitere Informationen finden Sie unter [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;Q174667](http://support.microsoft.com/default.aspx?scid=kb;en-us;Q174667) und [CWnd::SubclassWindow](../Topic/CWnd::SubclassWindow.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC Sampling CTRLBARS](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)