---
title: "CEdit Class"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEdit class"
  - "Steuerelemente [MFC], edit"
  - "edit controls"
  - "edit controls, Klassen"
  - "line separators in multiline edit controls"
  - "multiline edit control"
  - "Trennzeichen, in multiline edit controls"
  - "text editors"
  - "text editors, CEdit class"
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
caps.latest.revision: 22
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CEdit Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität eines Windows\-Bearbeitungssteuerelements bereit.  
  
## Syntax  
  
```  
class CEdit : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CEdit::CEdit](../Topic/CEdit::CEdit.md)|Erstellt ein `CEdit`\-Steuerelementobjekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CEdit::CanUndo](../Topic/CEdit::CanUndo.md)|Bestimmt, ob ein Edit\-Steuerelement\-Vorgang rückgängig gemacht werden kann.|  
|[CEdit::CharFromPos](../Topic/CEdit::CharFromPos.md)|Ruft die Zeilen\- und die Zeichenindizes für das Zeichen, das zu einer angegebenen Position am nächsten ist.|  
|[CEdit::Clear](../Topic/CEdit::Clear.md)|Löscht die \(Leerzeichen\) die aktuelle Auswahl \(falls vorhanden\) im Bearbeitungssteuerelement.|  
|[CEdit::Copy](../Topic/CEdit::Copy.md)|Kopiert die aktuelle Auswahl \(falls vorhanden\) im Bearbeitungssteuerelement in die Zwischenablage in **CF\_TEXT** Format.|  
|[CEdit::Create](../Topic/CEdit::Create.md)|Erstellt das Windows\-Bearbeitungssteuerelement und fügt es dem `CEdit`\-Objekt.|  
|[CEdit::Cut](../Topic/CEdit::Cut.md)|Löscht \(Schnitte\) die aktuelle Auswahl \(falls vorhanden\) im Bearbeitungssteuerelement sowie in den Kopien der gelöschte Text in die Zwischenablage in **CF\_TEXT** Format.|  
|[CEdit::EmptyUndoBuffer](../Topic/CEdit::EmptyUndoBuffer.md)|Setzt die \(Leerzeichen\) das Rückgängigflag eines Bearbeitungssteuerelements zurück.|  
|[CEdit::FmtLines](../Topic/CEdit::FmtLines.md)|Legt die Aufnahme von den weichgezeichneten Unterstreichung fest, die in einem mehrzeiligen Bearbeitungssteuerelements oder deaktiviert sind.|  
|[CEdit::GetCueBanner](../Topic/CEdit::GetCueBanner.md)|Ruft den Text ab, der während der Text\-Hinweis oder Tipp, in einem Bearbeitungssteuerelement angezeigt wird, wenn das Steuerelement leer ist und nicht den Fokus.|  
|[CEdit::GetFirstVisibleLine](../Topic/CEdit::GetFirstVisibleLine.md)|Bestimmt die oberste sichtbare Zeile in einem Bearbeitungssteuerelement.|  
|[CEdit::GetHandle](../Topic/CEdit::GetHandle.md)|Ruft ein Handle für den Arbeitsspeicher ab, der gerade für ein mehrzeiliges Bearbeitungssteuerelement zugeordnet ist.|  
|[CEdit::GetHighlight](../Topic/CEdit::GetHighlight.md)|Ruft die Indizes des Starten und der abschließendes Zeichen in einem Bereich des Texts ab, der im aktuellen Bearbeitungssteuerelement hervorgehoben wird.|  
|[CEdit::GetLimitText](../Topic/CEdit::GetLimitText.md)|Ruft die maximale Größe des Texts ab, den dieses `CEdit` enthalten kann.|  
|[CEdit::GetLine](../Topic/CEdit::GetLine.md)|Ruft eine Textzeile aus einem Bearbeitungssteuerelement ab.|  
|[CEdit::GetLineCount](../Topic/CEdit::GetLineCount.md)|Ruft die Anzahl der Zeilen in einem mehrzeiligen Bearbeitungssteuerelement ab.|  
|[CEdit::GetMargins](../Topic/CEdit::GetMargins.md)|Ruft die linken und rechten Rand für dieses `CEdit` ab.|  
|[CEdit::GetModify](../Topic/CEdit::GetModify.md)|Bestimmt, ob der Inhalt eines Bearbeitungssteuerelements geändert wurde.|  
|[CEdit::GetPasswordChar](../Topic/CEdit::GetPasswordChar.md)|Ruft das Kennwortzeichen ab, das in einem Bearbeitungssteuerelement angezeigt wird, wenn der Benutzer Text ein.|  
|[CEdit::GetRect](../Topic/CEdit::GetRect.md)|Ruft das Formatierungsrechteck eines Bearbeitungssteuerelements ab.|  
|[CEdit::GetSel](../Topic/CEdit::GetSel.md)|Ruft das erste und Positionen des letzten Zeichens der aktuellen Auswahl in einem Bearbeitungssteuerelement ab.|  
|[CEdit::HideBalloonTip](../Topic/CEdit::HideBalloonTip.md)|Blendet alle QuickInfo\-Sprechblase aus, die dem aktuellen Bearbeitungssteuerelement zugeordnet ist.|  
|[CEdit::LimitText](../Topic/CEdit::LimitText.md)|Beschränkt die Länge des Texts ein, den der Benutzer in ein Bearbeitungssteuerelement eingeben kann.|  
|[CEdit::LineFromChar](../Topic/CEdit::LineFromChar.md)|Ruft die Zeilennummer der Zeile ab, die den angegebenen Zeichenindex enthält.|  
|[CEdit::LineIndex](../Topic/CEdit::LineIndex.md)|Ruft den Zeichenindex einer Zeile innerhalb eines mehrzeiligen Bearbeitungssteuerelements ab.|  
|[CEdit::LineLength](../Topic/CEdit::LineLength.md)|Ruft die Länge einer Zeile in einem Bearbeitungssteuerelement ab.|  
|[CEdit::LineScroll](../Topic/CEdit::LineScroll.md)|Führt den Text eines mehrzeiligen Bearbeitungssteuerelements aus.|  
|[CEdit::Paste](../Topic/CEdit::Paste.md)|Fügt die Daten aus der Zwischenablage in das Bearbeitungssteuerelement in der aktuellen Cursorposition ein.  Daten eingefügt werden, wenn die Zwischenablage Daten in **CF\_TEXT** Format enthält.|  
|[CEdit::PosFromChar](../Topic/CEdit::PosFromChar.md)|Ruft die Koordinaten der linken oberen Ecke eines angegebenen Zeichenindexes ab.|  
|[CEdit::ReplaceSel](../Topic/CEdit::ReplaceSel.md)|Ersetzt die aktuelle Auswahl in einem Bearbeitungssteuerelement durch den angegebenen Text.|  
|[CEdit::SetCueBanner](../Topic/CEdit::SetCueBanner.md)|Legt den Text fest, der während der Text\-Hinweis oder Tipp, in einem Bearbeitungssteuerelement angezeigt wird, wenn das Steuerelement leer ist und nicht den Fokus.|  
|[CEdit::SetHandle](../Topic/CEdit::SetHandle.md)|Legt das Handle für den lokalen Arbeitsspeicher fest, der durch ein mehrzeiliges Bearbeitungssteuerelement verwendet wird.|  
|[CEdit::SetHighlight](../Topic/CEdit::SetHighlight.md)|Hebt einen Textbereich hervor, die im aktuellen Bearbeitungssteuerelement angezeigt wird.|  
|[CEdit::SetLimitText](../Topic/CEdit::SetLimitText.md)|Legt die maximale Menge Text fest, den dieses `CEdit` enthalten kann.|  
|[CEdit::SetMargins](../Topic/CEdit::SetMargins.md)|Legt die linken und rechten Rand für dieses `CEdit` fest.|  
|[CEdit::SetModify](../Topic/CEdit::SetModify.md)|Setzt oder freie Räume das Änderungsflag für ein Bearbeitungssteuerelement.|  
|[CEdit::SetPasswordChar](../Topic/CEdit::SetPasswordChar.md)|Legt fest oder entfernt ein Kennwortzeichen, das in einem Bearbeitungssteuerelement angezeigt wird, wenn der Benutzer Text ein.|  
|[CEdit::SetReadOnly](../Topic/CEdit::SetReadOnly.md)|Legt den schreibgeschützten Status eines Bearbeitungssteuerelements fest.|  
|[CEdit::SetRect](../Topic/CEdit::SetRect.md)|Legt das Formatierungsrechteck eines mehrzeiligen Bearbeitungssteuerelements fest und aktualisiert das Steuerelement.|  
|[CEdit::SetRectNP](../Topic/CEdit::SetRectNP.md)|Legt das Formatierungsrechteck eines mehrzeiligen Bearbeitungssteuerelements fest, ohne das Steuerelementfenster neu zu zeichnen.|  
|[CEdit::SetSel](../Topic/CEdit::SetSel.md)|Wählt einen Bereich von Zeichen in einem Bearbeitungssteuerelement aus.|  
|[CEdit::SetTabStops](../Topic/CEdit::SetTabStops.md)|Legt die Tabstopps in einem mehrzeiligen Bearbeitungssteuerelement fest.|  
|[CEdit::ShowBalloonTip](../Topic/CEdit::ShowBalloonTip.md)|Zeigt eine QuickInfo\-Sprechblase an, die dem aktuellen Bearbeitungssteuerelement zugeordnet ist.|  
|[CEdit::Undo](../Topic/CEdit::Undo.md)|Gibt den letzten Edit\-Steuerelement\-Vorgang um.|  
  
## Hinweise  
 Ein Bearbeitungssteuerelement ist ein rechteckiges untergeordnetes Fenster, in dem der Benutzer Text eingeben kann.  
  
 Sie können ein Bearbeitungssteuerelement entweder einer Dialogfeldvorlage oder direkt im Code erstellen.  In beiden Fällen zunächst der Konstruktor `CEdit`, um `CEdit` des Objekts zu erstellen, dann der [Erstellen Sie](../Topic/CEdit::Create.md)\-Memberfunktion aufzurufen, um das Windows\-Bearbeitungssteuerelement zu erstellen und diese dem `CEdit`\-Objekt anzufügen.  
  
 Konstruktion kann ein nur einen Schritt umfassender Prozess in einer Klasse sein, die von `CEdit` abgeleitet wird.  Schreiben Sie einen Konstruktor für die abgeleitete Klasse und rufen Sie **Create** aus dem Konstruktor auf.  
  
 `CEdit` erbt signifikante Funktionalität von `CWnd`.  Um Text aus einem `CEdit`\-Objekt festzulegen und abzurufen, verwenden Sie die `CWnd`\-Memberfunktionen [SetWindowText](../Topic/CWnd::SetWindowText.md) und [GetWindowText](../Topic/CWnd::GetWindowText.md), die festlegen oder den gesamten Inhalt eines Bearbeitungssteuerelements abrufen, selbst wenn ein mehrzeiliges \- Steuerelement ist.  Textzeilen in einem mehrzeiligen Steuerelement werden durch "\\ r \\ n" Zeichensequenzen getrennt.  Wenn ein Bearbeitungssteuerelement mehrzeilig ist, rufen Sie und Textteil des Steuerelements ab, indem Sie die `CEdit`\-Memberfunktionen [GetLine](../Topic/CEdit::GetLine.md), [SetSel](../Topic/CEdit::SetSel.md), [GetSel](../Topic/CEdit::GetSel.md) und [ReplaceSel](../Topic/CEdit::ReplaceSel.md) aufrufen.  
  
 Wenn Sie Windows\-Benachrichtigungsmeldungen bearbeiten möchten, die durch ein Bearbeitungssteuerelement zu seinem übergeordneten Element gesendet werden \(normalerweise eine Klasse wird von abgeleitet `CDialog`\), fügen Sie eine Meldungszuordnungseintrags\- und Meldungshandlermemberfunktion der übergeordneten Klasse für jede Meldung hinzu.  
  
 Jeder Eintrag in der Meldungszuordnung weist folgende Form auf:  
  
 **ON\_**Notification**\(***id, memberFxn***\)**  
  
 wobei `id` die ID des untergeordneten Fensters des Bearbeitungssteuerelements sendenden angibt, ist die Benachrichtigungen und `memberFxn` der Name der übergeordneten Memberfunktion, die Sie geschrieben haben, um die Benachrichtigung zu bearbeiten.  
  
 Der Funktionsprototyp des übergeordneten Elements ist, wie folgt:  
  
 memberFxn **\( \);afx\_msg** void  
  
 Im Folgenden finden Sie eine Liste der möglichen Meldungszuordnungseinträgen und von Beschreibung der Fälle, in denen es zum übergeordneten gesendet werden:  
  
-   **ON\_EN\_CHANGE** hat der Benutzer Aktionen ausgeführt, die möglicherweise Text in einem Bearbeitungssteuerelement geändert.  Im Gegensatz zur **EN\_UPDATE** Benachrichtigung wird diese Benachrichtigung gesendet, nachdem Windows die Anzeige aktualisiert.  
  
-   **ON\_EN\_ERRSPACE** das Bearbeitungssteuerelement kann nicht genügend Arbeitsspeicher zuordnen, um eine bestimmte Anforderung zu erfüllen.  
  
-   **ON\_EN\_HSCROLL** der Benutzer klickt auf die horizontale Bildlaufleiste eines Bearbeitungssteuerelements.  Das übergeordnete Fenster wird benachrichtigt, bevor der Bildschirm aktualisiert wird.  
  
-   **ON\_EN\_KILLFOCUS** das Bearbeitungssteuerelement verliert den Eingabefokus.  
  
-   **ON\_EN\_MAXTEXT** die aktuelle Einfügung hat die angegebene Anzahl von Zeichen für das Bearbeitungssteuerelement überschritten und ist abgeschnitten wurde.  Außerdem gesendet, wenn ein Bearbeitungssteuerelement nicht verfügt, dem **ES\_AUTOHSCROLL** Format und der Anzahl der einzufügenden Zeichen würde die Breite des Bearbeitungssteuerelements überschreiten.  Außerdem gesendet, wenn ein Bearbeitungssteuerelement nicht verfügt, dem **ES\_AUTOVSCROLL** Format und der Gesamtanzahl der Zeilen würde Zurückhalten von einer Texteinfügung die Höhe des Bearbeitungssteuerelements überschreiten.  
  
-   **ON\_EN\_SETFOCUS** gesendet hat, wann ein Bearbeitungssteuerelement den Eingabefokus erhält.  
  
-   **ON\_EN\_UPDATE** das Bearbeitungssteuerelement ist ungefähr zur Anzeige geändertem Text.  Gesendet, nachdem das Steuerelement den Text formatiert hat, aber bevor der Text rastert, damit die Fenstergröße geändert werden kann, ggf.  
  
-   **ON\_EN\_VSCROLL** der Benutzer klickt auf der vertikalen Bildlaufleiste eines Bearbeitungssteuerelements.  Das übergeordnete Fenster wird benachrichtigt, bevor der Bildschirm aktualisiert wird.  
  
 Wenn Sie ein `CEdit`\-Objekt innerhalb eines Dialogfelds erstellen, wird das Objekt `CEdit` automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie ein `CEdit`\-Objekt aus einer Dialogfeldressource mithilfe des Dialog\-Editors erstellen, wird das Objekt `CEdit` automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie ein `CEdit`\-Objekt innerhalb eines Fensters erstellen, müssen Sie möglicherweise auch es zerstören.  Wenn Sie das `CEdit`\-Objekt auf dem Stapel erstellen, wird er automatisch zerstört.  Wenn Sie das `CEdit`\-Objekt auf dem Heap erstellen, indem Sie die **new**\-Funktion verwenden, müssen Sie **delete** für das Objekt aufrufen, um es zu zerstören, wenn der Benutzer das Windows\-Bearbeitungssteuerelement beendet.  Wenn Sie einen Arbeitsspeicher im `CEdit`\-Objekt zuordnen, überschreiben Sie den `CEdit` Destruktor, um die Zuordnungen freizugeben.  
  
 Um bestimmte Formate in einem Bearbeitungssteuerelement zu ändern \(z **ES\_READONLY**\) müssen Sie bestimmte Meldungen an das Steuerelement senden anstatt [ModifyStyle](../Topic/CWnd::ModifyStyle.md) zu verwenden.  Siehe [Bearbeitungssteuerelement\-Formate](http://msdn.microsoft.com/library/windows/desktop/bb775464) in [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu `CEdit`, finden Sie unter:  
  
-   [Steuerelemente](../../mfc/controls-mfc.md)  
  
-   Knowledge Base\-Artikel Q259949: INFO: SetCaretPos\(\) ist nicht mit CEdit oder CRichEditCtrl\-Steuerelementen geeignet  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CEdit`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC\-Beispiel CALCDRIV](../../top/visual-cpp-samples.md)   
 [Das MFC\-Beispiel](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)