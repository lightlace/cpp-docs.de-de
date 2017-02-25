---
title: "CListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListBox-Klasse"
  - "Listenfelder"
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität eines Windows\-Listenfelds bereit.  
  
## Syntax  
  
```  
class CListBox : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CListBox::CListBox](../Topic/CListBox::CListBox.md)|Erstellt ein `CListBox`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CListBox::AddString](../Topic/CListBox::AddString.md)|Fügt eine Zeichenfolge ein Listenfeld hinzu.|  
|[CListBox::CharToItem](../Topic/CListBox::CharToItem.md)|Überschreiben Sie, um von benutzerdefiniertem `WM_CHAR`, das für Ownerdrawnlistenfelder bereitzustellen behandelt, die nicht Zeichenfolgen haben.|  
|[CListBox::CompareItem](../Topic/CListBox::CompareItem.md)|Aufgerufen durch das Framework, um die Position eines neuen Elements in einem sortierten Ownerdrawn Listenfeld zu bestimmen.|  
|[CListBox::Create](../Topic/CListBox::Create.md)|Stellt das Windows\-Listenfeld erstellt und fügt es an den `CListBox`\-Objekt.|  
|[CListBox::DeleteItem](../Topic/CListBox::DeleteItem.md)|Aufgerufen vom Framework, wenn der Benutzer ein Element aus einem Ownerdrawn Listenfeld gelöscht wird.|  
|[CListBox::DeleteString](../Topic/CListBox::DeleteString.md)|Löscht eine Zeichenfolge aus einem Listenfeld.|  
|[CListBox::Dir](../Topic/CListBox::Dir.md)|Fügt Dateinamen, Laufwerk oder beide vom aktuellen Verzeichnis einem Listenfeld hinzu.|  
|[CListBox::DrawItem](../Topic/CListBox::DrawItem.md)|Aufgerufen vom Framework ausgelöst, wenn ein visueller Aspekt eines Ownerdrawnlistenfelds ändert.|  
|[CListBox::FindString](../Topic/CListBox::FindString.md)|Sucht eine Zeichenfolge in einem Listenfeld.|  
|[CListBox::FindStringExact](../Topic/CListBox::FindStringExact.md)|Sucht die erste Listenfeldzeichenfolge, die eine angegebene Zeichenfolge.|  
|[CListBox::GetAnchorIndex](../Topic/CListBox::GetAnchorIndex.md)|Ruft den nullbasierten Index des aktuellen Ankerelements in einem Listenfeld ab.|  
|[CListBox::GetCaretIndex](../Topic/CListBox::GetCaretIndex.md)|Bestimmt den Index des Elements, das das Fokusrechteck in einem Mehrfachauswahllistenfeld verfügt.|  
|[CListBox::GetCount](../Topic/CListBox::GetCount.md)|Gibt die Anzahl von Zeichenfolgen in einem Listenfeld zurück.|  
|[CListBox::GetCurSel](../Topic/CListBox::GetCurSel.md)|Gibt den nullbasierten Index der aktuell ausgewählten Zeichenfolge in einem Listenfeld zurück.|  
|[CListBox::GetHorizontalExtent](../Topic/CListBox::GetHorizontalExtent.md)|Gibt die Breite in Pixel zurück, dass ein Listenfeld einen horizontalen Bildlauf durchgeführt werden kann.|  
|[CListBox::GetItemData](../Topic/CListBox::GetItemData.md)|Gibt den 32\-Bit\-Wert zurück, der mit dem Listenfeldelement zugeordnet ist.|  
|[CListBox::GetItemDataPtr](../Topic/CListBox::GetItemDataPtr.md)|Gibt einen Zeiger auf einen Listenfeldelement zurück.|  
|[CListBox::GetItemHeight](../Topic/CListBox::GetItemHeight.md)|Bestimmt die Höhe Elemente in einem Listenfeld.|  
|[CListBox::GetItemRect](../Topic/CListBox::GetItemRect.md)|Gibt das umschließende Rechteck des Listenfeldelements zurück, das gerade angezeigt wird.|  
|[CListBox::GetListBoxInfo](../Topic/CListBox::GetListBoxInfo.md)|Ruft die Anzahl von Elementen pro Spalte ab.|  
|[CListBox::GetLocale](../Topic/CListBox::GetLocale.md)|Ruft den Gebietsschemabezeichner für ein Listenfeld ab.|  
|[CListBox::GetSel](../Topic/CListBox::GetSel.md)|Gibt den Auswahlzustand eines Listenfeldelements zurück.|  
|[CListBox::GetSelCount](../Topic/CListBox::GetSelCount.md)|Gibt die Anzahl von Zeichenfolgen zurück, die derzeit in einem Mehrfachauswahllistenfeld ausgewählt werden.|  
|[CListBox::GetSelItems](../Topic/CListBox::GetSelItems.md)|Gibt die Indizes der Zeichenfolgen zurück, die derzeit in einem Listenfeld ausgewählt werden.|  
|[CListBox::GetText](../Topic/CListBox::GetText.md)|Kopiert ein Listenfeldelement in einen Puffer.|  
|[CListBox::GetTextLen](../Topic/CListBox::GetTextLen.md)|Gibt die Länge in Bytes eines Listenfeldelements zurück.|  
|[CListBox::GetTopIndex](../Topic/CListBox::GetTopIndex.md)|Gibt den Index der ersten sichtbaren Zeichenfolge in einem Listenfeld zurück.|  
|[CListBox::InitStorage](../Topic/CListBox::InitStorage.md)|Teilt Speicherblöcke für Listenfeldelemente und Zeichenfolgen zu.|  
|[CListBox::InsertString](../Topic/CListBox::InsertString.md)|Fügt eine Zeichenfolge an einer bestimmten Position in einem Listenfeld ein.|  
|[CListBox::ItemFromPoint](../Topic/CListBox::ItemFromPoint.md)|Gibt den Index des Listenfeldelements neben ein Punkt zurück.|  
|[CListBox::MeasureItem](../Topic/CListBox::MeasureItem.md)|Aufgerufen vom Framework ausgelöst, wenn ein Ownerdrawn Listenfeld erstellt wird, um Listenfelddimensionen zu bestimmen.|  
|[CListBox::ResetContent](../Topic/CListBox::ResetContent.md)|Löscht alle Einträge von einem Listenfeld.|  
|[CListBox::SelectString](../Topic/CListBox::SelectString.md)|Suchen und wählt eine Zeichenfolge in einem Liste, die die Einzelauswahl unterstützt, dies aus.|  
|[CListBox::SelItemRange](../Topic/CListBox::SelItemRange.md)|Wählt aus oder wählt einen Bereich von Zeichenfolgen in einem Mehrfachauswahllistenfeld ab.|  
|[CListBox::SetAnchorIndex](../Topic/CListBox::SetAnchorIndex.md)|Legt den Ankerpunkt in einem Mehrfachauswahllistenfeld fest, um eine erweiterte Auswahl zu starten.|  
|[CListBox::SetCaretIndex](../Topic/CListBox::SetCaretIndex.md)|Legt das Fokusrechteck auf das Element am angegebenen Index in einem Mehrfachauswahllistenfeld fest.|  
|[CListBox::SetColumnWidth](../Topic/CListBox::SetColumnWidth.md)|Legt die Spaltenbreite eines mehrspaltigen Listenfelds fest.|  
|[CListBox::SetCurSel](../Topic/CListBox::SetCurSel.md)|Wählt eine Listenfeldzeichenfolge aus.|  
|[CListBox::SetHorizontalExtent](../Topic/CListBox::SetHorizontalExtent.md)|Gibt die Breite in Pixel fest, dass ein Listenfeld einen horizontalen Bildlauf durchgeführt werden kann.|  
|[CListBox::SetItemData](../Topic/CListBox::SetItemData.md)|Legt den 32\-Bit\-Wert fest, der mit dem Listenfeldelement zugeordnet ist.|  
|[CListBox::SetItemDataPtr](../Topic/CListBox::SetItemDataPtr.md)|Legt einen Zeiger auf das Listenfeldelement fest.|  
|[CListBox::SetItemHeight](../Topic/CListBox::SetItemHeight.md)|Gibt die Höhe Elemente in einem Listenfeld fest.|  
|[CListBox::SetLocale](../Topic/CListBox::SetLocale.md)|Legt den Gebietsschemabezeichner für ein Listenfeld fest.|  
|[CListBox::SetSel](../Topic/CListBox::SetSel.md)|Wählt aus oder wählt ein Listenfeldelement in einem Mehrfachauswahllistenfeld ab.|  
|[CListBox::SetTabStops](../Topic/CListBox::SetTabStops.md)|Legt die Tabulationspositionen in einem Listenfeld fest.|  
|[CListBox::SetTopIndex](../Topic/CListBox::SetTopIndex.md)|Legt den nullbasierten Index der ersten sichtbaren Zeichenfolge in einem Listenfeld fest.|  
|[CListBox::VKeyToItem](../Topic/CListBox::VKeyToItem.md)|Überschreiben Sie, um von benutzerdefiniertem `WM_KEYDOWN`, das für Listenfelder mit dem **LBS\_WANTKEYBOARDINPUT** Formatsatz bereitzustellen behandelt.|  
  
## Hinweise  
 Ein Listenfeld zeigt eine Liste von Elementen, wie Dateinamen an, die der Benutzer anzeigen und auswählen kann.  
  
 In einem Liste, die die Einzelauswahl unterstützt, dies kann der Benutzer nur ein Element auswählen.  In einem Mehrfachauswahllistenfeld kann ein Bereich von Elementen ausgewählt werden.  Wenn der Benutzer ein Element auswählt, wird es hervorgehoben und das Listenfeld sendet eine Benachrichtigung zum übergeordneten Fenster.  
  
 Sie können ein Listenfeld entweder einer Dialogfeldvorlage oder direkt im Code erstellen.  Um diesen direkt zu erstellen, erstellen Sie das `CListBox`\-Objekt, und rufen Sie dann die [Erstellen Sie](../Topic/CListBox::Create.md)\-Memberfunktion auf um das Windows\-Listenfeld\-Steuerelement zu erstellen und auf `CListBox`\-Objekt anzufügen.  So fügen Sie ein Listenfeld in einer Dialogfeldvorlage verwenden, eine Listenfeldvariable in der Dialogfeldklasse deklarieren, `DDX_Control` in `DoDataExchange`\-Funktion der Dialogfeldklasse nutzen, um die Membervariable an das Steuerelement zu verbinden.  \(wird automatisch ausgeführt, wenn Sie eine Steuerungsvariable der Dialogfeldklasse hinzufügen.\)  
  
 Konstruktion kann ein nur einen Schritt umfassender Prozess in einer Klasse sein, die von `CListBox` abgeleitet wird.  Schreiben Sie einen Konstruktor für die abgeleitete Klasse und rufen Sie **Create** aus dem Konstruktor auf.  
  
 Wenn Sie Windows\-Benachrichtigungsmeldungen bearbeiten möchten, die durch ein Listenfeld zu seinem übergeordneten Element gesendet werden \(normalerweise eine Klasse wird von abgeleitet [CDialog\-Klasse](../../mfc/reference/cdialog-class.md)\), fügen Sie eine Meldungszuordnungseintrags\- und Meldungshandlermemberfunktion der übergeordneten Klasse für jede Meldung hinzu.  
  
 Jeder Eintrag in der Meldungszuordnung weist folgende Form auf:  
  
 `ON_Notification( id, memberFxn )`  
  
 wobei `id` die ID des untergeordneten Fensters des sendenden Listenfeld\-Steuerelements angibt, ist die Benachrichtigungen und `memberFxn` der Name der übergeordneten Memberfunktion, die Sie geschrieben haben, um die Benachrichtigung zu bearbeiten.  
  
 Der Funktionsprototyp des übergeordneten Elements ist, wie folgt:  
  
 `afx_msg void memberFxn( );`  
  
 Im Folgenden finden Sie eine Liste der möglichen Meldungszuordnungseinträgen und von Beschreibung der Fälle, in denen es zum übergeordneten gesendet werden:  
  
-   **ON\_LBN\_DBLCLK** der Benutzer doppelklickt auf eine Zeichenfolge in einem Listenfeld.  Nur ein Listenfeld, das das [LBS\_NOTIFY](../../mfc/reference/list-box-styles.md) Format hat, sendet diese Benachrichtigung.  
  
-   **ON\_LBN\_ERRSPACE** das Listenfeld kann nicht genügend Arbeitsspeicher zuordnen, um die Anforderung zu erfüllen.  
  
-   **ON\_LBN\_KILLFOCUS** das Listenfeld verliert den Eingabefokus.  
  
-   **ON\_LBN\_SELCANCEL** die aktuelle Listenfeld\-Auswahl wird abgebrochen.  Diese Meldung wird nur gesendet, wenn ein Listenfeld das **LBS\_NOTIFY** Format hat.  
  
-   **ON\_LBN\_SELCHANGE**, das die Auswahl im Listenfeld sich geändert hat.  Diese Benachrichtigung wird nicht gesendet, wenn die Auswahl durch die [CListBox::SetCurSel](../Topic/CListBox::SetCurSel.md)\-Memberfunktion geändert wird.  Diese Benachrichtigung gilt nur für ein Listenfeld zu, das das **LBS\_NOTIFY** Format hat.  Die **LBN\_SELCHANGE** Benachrichtigung wird für ein Mehrfachauswahllistenfeld gesendet, wenn der Benutzer eine Pfeiltaste gedrückt wird, auch wenn die Auswahl nicht ändert.  
  
-   **ON\_LBN\_SETFOCUS** das Listenfeld empfängt den Eingabefokus.  
  
-   **ON\_WM\_CHARTOITEM** ein Ownerdrawn Listenfeld, das keine Zeichenfolgen hat, empfängt eine `WM_CHAR` Meldung.  
  
-   Ein mit dem Listenfeld **ON\_WM\_VKEYTOITEMLBS\_WANTKEYBOARDINPUT** Format empfängt eine `WM_KEYDOWN` Meldung.  
  
 Wenn Sie ein `CListBox`\-Objekt innerhalb eines Dialogfelds \(durch eine Dialogfeldressource\) erstellen, wird das Objekt `CListBox` automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie ein `CListBox`\-Objekt innerhalb eines Fensters erstellen, müssen Sie möglicherweise das `CListBox`\-Objekt zerstören.  Wenn Sie das `CListBox`\-Objekt auf dem Stapel erstellen, wird er automatisch zerstört.  Wenn Sie das `CListBox`\-Objekt auf dem Heap erstellen, indem Sie die **new**\-Funktion verwenden, müssen Sie **delete** für das Objekt aufrufen, um es zu zerstören, wenn der Benutzer das übergeordnete Fenster geschlossen wird.  
  
 Wenn Sie einen Arbeitsspeicher im `CListBox`\-Objekt zuordnen, überschreiben Sie den `CListBox` Destruktor, um die Zuordnung freizugeben.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListBox`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC Sampling CTRLTEST](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)