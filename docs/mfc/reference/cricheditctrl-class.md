---
title: "CRichEditCtrl Class"
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
  - "CRichEditCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCtrl class"
  - "CRichEditCtrl class, Allgemeine Steuerelemente"
  - "formatted text [C++]"
ms.assetid: 2be52788-822c-4c27-aafd-2471231e74eb
caps.latest.revision: 26
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# CRichEditCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität des Rich\-Edit\-Steuerelements bereit.  
  
## Syntax  
  
```  
class CRichEditCtrl : public CWnd  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditCtrl::CRichEditCtrl](../Topic/CRichEditCtrl::CRichEditCtrl.md)|Erstellt ein `CRichEditCtrl`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRichEditCtrl::CanPaste](../Topic/CRichEditCtrl::CanPaste.md)|Bestimmt, ob der Inhalt der Zwischenablage in dieses RichEdit\-Steuerelement eingefügt werden kann.|  
|[CRichEditCtrl::CanRedo](../Topic/CRichEditCtrl::CanRedo.md)|Bestimmt, ob es Aktionen in der Wiederholungswarteschlange des Steuerelements haben.|  
|[CRichEditCtrl::CanUndo](../Topic/CRichEditCtrl::CanUndo.md)|Bestimmt, ob ein Bearbeitungsvorgang rückgängig gemacht werden kann.|  
|[CRichEditCtrl::CharFromPos](../Topic/CRichEditCtrl::CharFromPos.md)|Ruft Informationen über das Zeichen, das zu einem angegebenen Punkt im Clientbereich eines Bearbeitungssteuerelements am nächsten ist.|  
|[CRichEditCtrl::Clear](../Topic/CRichEditCtrl::Clear.md)|Löscht die aktuelle Auswahl.|  
|[CRichEditCtrl::Copy](../Topic/CRichEditCtrl::Copy.md)|Kopiert die aktuelle Auswahl in die Zwischenablage.|  
|[CRichEditCtrl::Create](../Topic/CRichEditCtrl::Create.md)|Erstellt das Windows\-Rich\-Edit\-Steuerelement und ordnet mit diesem `CRichEditCtrl`\-Objekt zu.|  
|[CRichEditCtrl::CreateEx](../Topic/CRichEditCtrl::CreateEx.md)|Erstellt das Windows\-Rich\-Edit\-Steuerelement mit den angegebenen erweiterten Windows\-Formaten und ordnet mit diesem `CRichEditCtrl`\-Objekt zu.|  
|[CRichEditCtrl::Cut](../Topic/CRichEditCtrl::Cut.md)|Schneidet die aktuelle Auswahl in die Zwischenablage aus.|  
|[CRichEditCtrl::DisplayBand](../Topic/CRichEditCtrl::DisplayBand.md)|Zeigt einen Teil des Inhalts `CRichEditCtrl` dieses Objekts an.|  
|[CRichEditCtrl::EmptyUndoBuffer](../Topic/CRichEditCtrl::EmptyUndoBuffer.md)|Setzt die \(Leerzeichen\) das Rückgängigflag `CRichEditCtrl` dieses Objekts zurück.|  
|[CRichEditCtrl::FindText](../Topic/CRichEditCtrl::FindText.md)|Die Text innerhalb dieses `CRichEditCtrl`\-Objekts.|  
|[CRichEditCtrl::FindWordBreak](../Topic/CRichEditCtrl::FindWordBreak.md)|Sucht den folgenden Wortumbruch vor oder nach der angegebenen Zeichenposition oder ruft Informationen über das Zeichen an dieser Position ab.|  
|[CRichEditCtrl::FormatRange](../Topic/CRichEditCtrl::FormatRange.md)|Formatiert einen Textbereich für den Zielausgabe\-Ausgabemechanismus.|  
|[CRichEditCtrl::GetCharPos](../Topic/CRichEditCtrl::GetCharPos.md)|Bestimmt die Position eines angegebenen Zeichens innerhalb dieses `CRichEditCtrl`\-Objekts.|  
|[CRichEditCtrl::GetDefaultCharFormat](../Topic/CRichEditCtrl::GetDefaultCharFormat.md)|Ruft die aktuellen Standardzeichenformatierungsattribute in diesem `CRichEditCtrl`\-Objekt ab.|  
|[CRichEditCtrl::GetEventMask](../Topic/CRichEditCtrl::GetEventMask.md)|Ruft die Ereignismaske `CRichEditCtrl` für dieses Objekt ab.|  
|[CRichEditCtrl::GetFirstVisibleLine](../Topic/CRichEditCtrl::GetFirstVisibleLine.md)|Bestimmt die oberste sichtbare Zeile in diesem `CRichEditCtrl`\-Objekt.|  
|[CRichEditCtrl::GetIRichEditOle](../Topic/CRichEditCtrl::GetIRichEditOle.md)|Ruft einen Zeiger auf die `IRichEditOle`\-Schnittstelle für dieses RichEdit\-Steuerelement ab.|  
|[CRichEditCtrl::GetLimitText](../Topic/CRichEditCtrl::GetLimitText.md)|Ruft die Begrenzung auf der Textmenge ab, den der Benutzer in `CRichEditCtrl` dieses Objekt eingeben kann.|  
|[CRichEditCtrl::GetLine](../Topic/CRichEditCtrl::GetLine.md)|Ruft eine Textzeile aus diesem `CRichEditCtrl`\-Objekt ab.|  
|[CRichEditCtrl::GetLineCount](../Topic/CRichEditCtrl::GetLineCount.md)|Ruft die Anzahl der Zeilen in diesem `CRichEditCtrl`\-Objekt ab.|  
|[CRichEditCtrl::GetModify](../Topic/CRichEditCtrl::GetModify.md)|Bestimmt, ob der Inhalt dieses `CRichEditCtrl`\-Objekts geändert hat, da speichern Sie dauern.|  
|[CRichEditCtrl::GetOptions](../Topic/CRichEditCtrl::GetOptions.md)|Ruft die Rich\-Edit\-Steuerelement\-Optionen ab.|  
|[CRichEditCtrl::GetParaFormat](../Topic/CRichEditCtrl::GetParaFormat.md)|Ruft die Absatzformatierungsattribute in der aktuellen Auswahl in diesem `CRichEditCtrl`\-Objekt ab.|  
|[CRichEditCtrl::GetPunctuation](../Topic/CRichEditCtrl::GetPunctuation.md)|Ruft die aktuellen Satzzeichen für das RichEdit\-Steuerelement ab.  Diese Meldung ist nur in Asiatisch\-Sprache Versionen des Betriebssystems verfügbar.|  
|[CRichEditCtrl::GetRect](../Topic/CRichEditCtrl::GetRect.md)|Ruft das Formatierungsrechteck `CRichEditCtrl` für dieses Objekt ab.|  
|[CRichEditCtrl::GetRedoName](../Topic/CRichEditCtrl::GetRedoName.md)|Ruft den Typ der folgenden Aktion ggf. in der Wiederholungswarteschlange des Steuerelements ab.|  
|[CRichEditCtrl::GetSel](../Topic/CRichEditCtrl::GetSel.md)|Ruft das Anfangs\- und das Zielpositionen der aktuellen Auswahl in diesem `CRichEditCtrl`\-Objekt ab.|  
|[CRichEditCtrl::GetSelectionCharFormat](../Topic/CRichEditCtrl::GetSelectionCharFormat.md)|Ruft die Zeichenformatierungsattribute in der aktuellen Auswahl in diesem `CRichEditCtrl`\-Objekt ab.|  
|[CRichEditCtrl::GetSelectionType](../Topic/CRichEditCtrl::GetSelectionType.md)|Ruft den Typ des Inhalts in der aktuellen Auswahl in diesem `CRichEditCtrl`\-Objekt ab.|  
|[CRichEditCtrl::GetSelText](../Topic/CRichEditCtrl::GetSelText.md)|Ruft den Text der aktuellen Auswahl in diesem Objekt ab `CRichEditCtrl`|  
|[CRichEditCtrl::GetTextLength](../Topic/CRichEditCtrl::GetTextLength.md)|Ruft die Länge des Texts, in Zeichen, in diesem `CRichEditCtrl`\-Objekt ab.  enthält nicht das NULL ein.|  
|[CRichEditCtrl::GetTextLengthEx](../Topic/CRichEditCtrl::GetTextLengthEx.md)|Ruft die Anzahl von Zeichen oder Bytes in der Rich\-Edit\-Ansicht ab.  Akzeptiert eine Liste von Flags, um die Methode zum Bestimmen der Länge des Texts in einem RichEdit\-Steuerelement anzugeben|  
|[CRichEditCtrl::GetTextMode](../Topic/CRichEditCtrl::GetTextMode.md)|Ruft den aktuellen Textmodus und die Rückgängig\-Ebene eines Rich\-Edit\-Steuerelements ab.|  
|[CRichEditCtrl::GetTextRange](../Topic/CRichEditCtrl::GetTextRange.md)|Ruft den angegebenen Textbereich ab.|  
|[CRichEditCtrl::GetUndoName](../Topic/CRichEditCtrl::GetUndoName.md)|Ruft den Typ der folgenden Rückgängigaktion, sofern ab.|  
|[CRichEditCtrl::GetWordWrapMode](../Topic/CRichEditCtrl::GetWordWrapMode.md)|Ruft die aktuellen Wortumbruchs\- und \-Worttrennungsoptionen für das RichEdit\-Steuerelement ab.  Diese Meldung ist nur in Asiatisch\-Sprache Versionen des Betriebssystems verfügbar.|  
|[CRichEditCtrl::HideSelection](../Topic/CRichEditCtrl::HideSelection.md)|In oder aus die aktuelle Auswahl.|  
|[CRichEditCtrl::LimitText](../Topic/CRichEditCtrl::LimitText.md)|Schränkt die Textmenge ein, den der Benutzer in das Objekt `CRichEditCtrl` eingeben kann.|  
|[CRichEditCtrl::LineFromChar](../Topic/CRichEditCtrl::LineFromChar.md)|Bestimmt, dem Zeile das angegebene Zeichen enthält.|  
|[CRichEditCtrl::LineIndex](../Topic/CRichEditCtrl::LineIndex.md)|Ruft den Zeichenindex einer bestimmten Zeile in diesem `CRichEditCtrl`\-Objekt ab.|  
|[CRichEditCtrl::LineLength](../Topic/CRichEditCtrl::LineLength.md)|Ruft die Länge einer bestimmten Zeile in diesem `CRichEditCtrl`\-Objekt ab.|  
|[CRichEditCtrl::LineScroll](../Topic/CRichEditCtrl::LineScroll.md)|Führt den Text in diesem `CRichEditCtrl`\-Objekt aus.|  
|[CRichEditCtrl::Paste](../Topic/CRichEditCtrl::Paste.md)|Fügt den Inhalt der Zwischenablage in dieses RichEdit\-Steuerelement ein.|  
|[CRichEditCtrl::PasteSpecial](../Topic/CRichEditCtrl::PasteSpecial.md)|Fügt den Inhalt der Zwischenablage in dieses RichEdit\-Steuerelement im angegebenen Datenformat ein.|  
|[CRichEditCtrl::PosFromChar](../Topic/CRichEditCtrl::PosFromChar.md)|Ruft die Clientbereichskoordinaten eines angegebenen Zeichens in einem Bearbeitungssteuerelement ab.|  
|[CRichEditCtrl::Redo](../Topic/CRichEditCtrl::Redo.md)|Wiederholt die nächste Aktion in der Wiederholungswarteschlange des Steuerelements.|  
|[CRichEditCtrl::ReplaceSel](../Topic/CRichEditCtrl::ReplaceSel.md)|Ersetzt die aktuelle Auswahl in diesem `CRichEditCtrl`\-Objekt durch angegebenen Text.|  
|[CRichEditCtrl::RequestResize](../Topic/CRichEditCtrl::RequestResize.md)|Erzwingt `CRichEditCtrl` dieses Objekt, um Anforderung gesendet werden Benachrichtigungen Größe ändern.|  
|[CRichEditCtrl::SetAutoURLDetect](../Topic/CRichEditCtrl::SetAutoURLDetect.md)|Gibt an, ob die Erkennung der Autos URL in einem RichEdit\-Steuerelement aktiv ist.|  
|[CRichEditCtrl::SetBackgroundColor](../Topic/CRichEditCtrl::SetBackgroundColor.md)|Legt die Hintergrundfarbe in diesem `CRichEditCtrl`\-Objekt fest.|  
|[CRichEditCtrl::SetDefaultCharFormat](../Topic/CRichEditCtrl::SetDefaultCharFormat.md)|Legt die aktuellen Standardzeichenformatierungsattribute in diesem `CRichEditCtrl`\-Objekt fest.|  
|[CRichEditCtrl::SetEventMask](../Topic/CRichEditCtrl::SetEventMask.md)|Legt die Ereignismaske `CRichEditCtrl` für dieses Objekt fest.|  
|[CRichEditCtrl::SetModify](../Topic/CRichEditCtrl::SetModify.md)|Setzt oder freie Räume das Änderungsflag `CRichEditCtrl` für dieses Objekt.|  
|[CRichEditCtrl::SetOLECallback](../Topic/CRichEditCtrl::SetOLECallback.md)|Legt das `IRichEditOleCallback` COM\-Objekt für dieses RichEdit\-Steuerelement fest.|  
|[CRichEditCtrl::SetOptions](../Topic/CRichEditCtrl::SetOptions.md)|Legt die Optionen für den `CRichEditCtrl`\-Objekt fest.|  
|[CRichEditCtrl::SetParaFormat](../Topic/CRichEditCtrl::SetParaFormat.md)|Legt die Absatzformatierungsattribute in der aktuellen Auswahl in diesem `CRichEditCtrl`\-Objekt fest.|  
|[CRichEditCtrl::SetPunctuation](../Topic/CRichEditCtrl::SetPunctuation.md)|Legt die Satzzeichen für ein RichEdit\-Steuerelement fest.  Diese Meldung ist nur in Asiatisch\-Sprache Versionen des Betriebssystems verfügbar.|  
|[CRichEditCtrl::SetReadOnly](../Topic/CRichEditCtrl::SetReadOnly.md)|Legt die schreibgeschützte Option für dieses Objekt `CRichEditCtrl` fest.|  
|[CRichEditCtrl::SetRect](../Topic/CRichEditCtrl::SetRect.md)|Legt das Formatierungsrechteck `CRichEditCtrl` für dieses Objekt fest.|  
|[CRichEditCtrl::SetSel](../Topic/CRichEditCtrl::SetSel.md)|Legt die Auswahl in diesem `CRichEditCtrl`\-Objekt fest.|  
|[CRichEditCtrl::SetSelectionCharFormat](../Topic/CRichEditCtrl::SetSelectionCharFormat.md)|Legt die Zeichenformatierungsattribute in der aktuellen Auswahl in diesem `CRichEditCtrl`\-Objekt fest.|  
|[CRichEditCtrl::SetTargetDevice](../Topic/CRichEditCtrl::SetTargetDevice.md)|Legt den Zielausgabe\-Ausgabemechanismus `CRichEditCtrl` für dieses Objekt fest.|  
|[CRichEditCtrl::SetTextMode](../Topic/CRichEditCtrl::SetTextMode.md)|Legt den Textmodus oder die Rückgängig\-Ebene eines Rich\-Edit\-Steuerelements fest.  Die Meldung schlägt fehl, wenn das Steuerelement Text enthält.|  
|[CRichEditCtrl::SetUndoLimit](../Topic/CRichEditCtrl::SetUndoLimit.md)|Legt die maximale Anzahl von Aktionen fest, die in der Rückgängigwarteschlange können.|  
|[CRichEditCtrl::SetWordCharFormat](../Topic/CRichEditCtrl::SetWordCharFormat.md)|Legt die Zeichenformatierungsattribute im aktuellen Wort in diesem `CRichEditCtrl`\-Objekt fest.|  
|[CRichEditCtrl::SetWordWrapMode](../Topic/CRichEditCtrl::SetWordWrapMode.md)|Legt den Zeilenumbruch und die Worttrennungsoptionen für das RichEdit\-Steuerelement fest.  Diese Meldung ist nur in Asiatisch\-Sprache Versionen des Betriebssystems verfügbar.|  
|[CRichEditCtrl::StopGroupTyping](../Topic/CRichEditCtrl::StopGroupTyping.md)|Beendet das Steuerelement aus dem Sammeln zusätzlicher Typisierungsaktionen in eine aktuelle Rückgängigaktion.  Das Steuerelement speichert die folgenden Typisierungsaktion ggf. in eine neue Aktion in der Rückgängigwarteschlange.|  
|[CRichEditCtrl::StreamIn](../Topic/CRichEditCtrl::StreamIn.md)|fügt Text aus einem Eingabestream in dieses `CRichEditCtrl`\-Objekt.|  
|[CRichEditCtrl::StreamOut](../Topic/CRichEditCtrl::StreamOut.md)|Speicher Text aus diesem `CRichEditCtrl`\-Objekt in einen Ausgabestream.|  
|[CRichEditCtrl::Undo](../Topic/CRichEditCtrl::Undo.md)|Gibt den letzten Bearbeitungsvorgang um.|  
  
## Hinweise  
 Ein "RichEdit\-Steuerelement" ist ein Fenster, in dem der Benutzer Text eingeben und bearbeiten kann.  Der Text kann Zeichen und Absatzformatierung zugewiesen und kann eingebettete OLE\-Objekte einschließen.  derzeit stellen eine Programmierschnittstelle zum Formatieren von Text bereit.  muss jedoch eine Anwendung alle Benutzeroberflächenkomponenten implementieren, die erforderlich sind, Formatierungsvorgänge zu machen für den Benutzer.  
  
 Dieses allgemeine Windows\-Steuerelement \(und daher die `CRichEditCtrl`\-Klasse\) ist nur für \- Programmen verfügbar, die unter Windows 95\/98\- und Windows NT\-Versionen 3,51 und höher ausgeführt werden.  Die `CRichEditCtrl`\-Klasse unterstützt Versionen 2,0 und 3,0 des [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Rich\-Edit\-Steuerelements.  
  
> [!CAUTION]
>  Wenn Sie ein RichEdit\-Steuerelement in einem Dialogfeld verwenden \(unabhängig davon, ob die SDI\-Anwendung, die oder auf Dialogfeldern basierte\), müssen Sie [AfxInitRichEdit](../Topic/AfxInitRichEdit.md) einmal aufrufen, bevor das Dialogfeld angezeigt wird.  Ein typischer Platz, um diese Funktion aufzurufen ist in `InitInstance`\-Memberfunktion des Programms.  Sie müssen nicht, um ihn für jedes Mal, wenn Sie das Dialogfeld anzeigen, nur beim ersten aufzurufen.  Sie müssen `AfxInitRichEdit` nicht aufrufen, wenn Sie mit `CRichEditView` arbeiten.  
  
 Weitere Informationen zur Verwendung von `CRichEditCtrl`, finden Sie unter:  
  
-   [Steuerelemente](../../mfc/controls-mfc.md)  
  
-   [Verwenden CRichEditCtrl](../../mfc/using-cricheditctrl.md)  
  
-   Knowledge Base\-Artikel Q259949: INFO: SetCaretPos\(\) ist nicht mit CEdit oder CRichEditCtrl\-Steuerelementen geeignet  
  
 Ein Beispiel für die Verwendung eines Rich\-Edit\-Steuerelements in einer MFC\-Anwendung, finden Sie die [WORDPAD](../../top/visual-cpp-samples.md) Beispielanwendung.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CRichEditCtrl`  
  
## Anforderungen  
 **Header:**  afxcmn.h  
  
## Siehe auch  
 [MFC Sampling WORDPAD](../../top/visual-cpp-samples.md)   
 [CWnd\-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)