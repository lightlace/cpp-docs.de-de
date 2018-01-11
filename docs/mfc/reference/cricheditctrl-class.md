---
title: CRichEditCtrl-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditCtrl
- AFXCMN/CRichEditCtrl
- AFXCMN/CRichEditCtrl::CRichEditCtrl
- AFXCMN/CRichEditCtrl::CanPaste
- AFXCMN/CRichEditCtrl::CanRedo
- AFXCMN/CRichEditCtrl::CanUndo
- AFXCMN/CRichEditCtrl::CharFromPos
- AFXCMN/CRichEditCtrl::Clear
- AFXCMN/CRichEditCtrl::Copy
- AFXCMN/CRichEditCtrl::Create
- AFXCMN/CRichEditCtrl::CreateEx
- AFXCMN/CRichEditCtrl::Cut
- AFXCMN/CRichEditCtrl::DisplayBand
- AFXCMN/CRichEditCtrl::EmptyUndoBuffer
- AFXCMN/CRichEditCtrl::FindText
- AFXCMN/CRichEditCtrl::FindWordBreak
- AFXCMN/CRichEditCtrl::FormatRange
- AFXCMN/CRichEditCtrl::GetCharPos
- AFXCMN/CRichEditCtrl::GetDefaultCharFormat
- AFXCMN/CRichEditCtrl::GetEventMask
- AFXCMN/CRichEditCtrl::GetFirstVisibleLine
- AFXCMN/CRichEditCtrl::GetIRichEditOle
- AFXCMN/CRichEditCtrl::GetLimitText
- AFXCMN/CRichEditCtrl::GetLine
- AFXCMN/CRichEditCtrl::GetLineCount
- AFXCMN/CRichEditCtrl::GetModify
- AFXCMN/CRichEditCtrl::GetOptions
- AFXCMN/CRichEditCtrl::GetParaFormat
- AFXCMN/CRichEditCtrl::GetPunctuation
- AFXCMN/CRichEditCtrl::GetRect
- AFXCMN/CRichEditCtrl::GetRedoName
- AFXCMN/CRichEditCtrl::GetSel
- AFXCMN/CRichEditCtrl::GetSelectionCharFormat
- AFXCMN/CRichEditCtrl::GetSelectionType
- AFXCMN/CRichEditCtrl::GetSelText
- AFXCMN/CRichEditCtrl::GetTextLength
- AFXCMN/CRichEditCtrl::GetTextLengthEx
- AFXCMN/CRichEditCtrl::GetTextMode
- AFXCMN/CRichEditCtrl::GetTextRange
- AFXCMN/CRichEditCtrl::GetUndoName
- AFXCMN/CRichEditCtrl::GetWordWrapMode
- AFXCMN/CRichEditCtrl::HideSelection
- AFXCMN/CRichEditCtrl::LimitText
- AFXCMN/CRichEditCtrl::LineFromChar
- AFXCMN/CRichEditCtrl::LineIndex
- AFXCMN/CRichEditCtrl::LineLength
- AFXCMN/CRichEditCtrl::LineScroll
- AFXCMN/CRichEditCtrl::Paste
- AFXCMN/CRichEditCtrl::PasteSpecial
- AFXCMN/CRichEditCtrl::PosFromChar
- AFXCMN/CRichEditCtrl::Redo
- AFXCMN/CRichEditCtrl::ReplaceSel
- AFXCMN/CRichEditCtrl::RequestResize
- AFXCMN/CRichEditCtrl::SetAutoURLDetect
- AFXCMN/CRichEditCtrl::SetBackgroundColor
- AFXCMN/CRichEditCtrl::SetDefaultCharFormat
- AFXCMN/CRichEditCtrl::SetEventMask
- AFXCMN/CRichEditCtrl::SetModify
- AFXCMN/CRichEditCtrl::SetOLECallback
- AFXCMN/CRichEditCtrl::SetOptions
- AFXCMN/CRichEditCtrl::SetParaFormat
- AFXCMN/CRichEditCtrl::SetPunctuation
- AFXCMN/CRichEditCtrl::SetReadOnly
- AFXCMN/CRichEditCtrl::SetRect
- AFXCMN/CRichEditCtrl::SetSel
- AFXCMN/CRichEditCtrl::SetSelectionCharFormat
- AFXCMN/CRichEditCtrl::SetTargetDevice
- AFXCMN/CRichEditCtrl::SetTextMode
- AFXCMN/CRichEditCtrl::SetUndoLimit
- AFXCMN/CRichEditCtrl::SetWordCharFormat
- AFXCMN/CRichEditCtrl::SetWordWrapMode
- AFXCMN/CRichEditCtrl::StopGroupTyping
- AFXCMN/CRichEditCtrl::StreamIn
- AFXCMN/CRichEditCtrl::StreamOut
- AFXCMN/CRichEditCtrl::Undo
dev_langs: C++
helpviewer_keywords:
- CRichEditCtrl [MFC], CRichEditCtrl
- CRichEditCtrl [MFC], CanPaste
- CRichEditCtrl [MFC], CanRedo
- CRichEditCtrl [MFC], CanUndo
- CRichEditCtrl [MFC], CharFromPos
- CRichEditCtrl [MFC], Clear
- CRichEditCtrl [MFC], Copy
- CRichEditCtrl [MFC], Create
- CRichEditCtrl [MFC], CreateEx
- CRichEditCtrl [MFC], Cut
- CRichEditCtrl [MFC], DisplayBand
- CRichEditCtrl [MFC], EmptyUndoBuffer
- CRichEditCtrl [MFC], FindText
- CRichEditCtrl [MFC], FindWordBreak
- CRichEditCtrl [MFC], FormatRange
- CRichEditCtrl [MFC], GetCharPos
- CRichEditCtrl [MFC], GetDefaultCharFormat
- CRichEditCtrl [MFC], GetEventMask
- CRichEditCtrl [MFC], GetFirstVisibleLine
- CRichEditCtrl [MFC], GetIRichEditOle
- CRichEditCtrl [MFC], GetLimitText
- CRichEditCtrl [MFC], GetLine
- CRichEditCtrl [MFC], GetLineCount
- CRichEditCtrl [MFC], GetModify
- CRichEditCtrl [MFC], GetOptions
- CRichEditCtrl [MFC], GetParaFormat
- CRichEditCtrl [MFC], GetPunctuation
- CRichEditCtrl [MFC], GetRect
- CRichEditCtrl [MFC], GetRedoName
- CRichEditCtrl [MFC], GetSel
- CRichEditCtrl [MFC], GetSelectionCharFormat
- CRichEditCtrl [MFC], GetSelectionType
- CRichEditCtrl [MFC], GetSelText
- CRichEditCtrl [MFC], GetTextLength
- CRichEditCtrl [MFC], GetTextLengthEx
- CRichEditCtrl [MFC], GetTextMode
- CRichEditCtrl [MFC], GetTextRange
- CRichEditCtrl [MFC], GetUndoName
- CRichEditCtrl [MFC], GetWordWrapMode
- CRichEditCtrl [MFC], HideSelection
- CRichEditCtrl [MFC], LimitText
- CRichEditCtrl [MFC], LineFromChar
- CRichEditCtrl [MFC], LineIndex
- CRichEditCtrl [MFC], LineLength
- CRichEditCtrl [MFC], LineScroll
- CRichEditCtrl [MFC], Paste
- CRichEditCtrl [MFC], PasteSpecial
- CRichEditCtrl [MFC], PosFromChar
- CRichEditCtrl [MFC], Redo
- CRichEditCtrl [MFC], ReplaceSel
- CRichEditCtrl [MFC], RequestResize
- CRichEditCtrl [MFC], SetAutoURLDetect
- CRichEditCtrl [MFC], SetBackgroundColor
- CRichEditCtrl [MFC], SetDefaultCharFormat
- CRichEditCtrl [MFC], SetEventMask
- CRichEditCtrl [MFC], SetModify
- CRichEditCtrl [MFC], SetOLECallback
- CRichEditCtrl [MFC], SetOptions
- CRichEditCtrl [MFC], SetParaFormat
- CRichEditCtrl [MFC], SetPunctuation
- CRichEditCtrl [MFC], SetReadOnly
- CRichEditCtrl [MFC], SetRect
- CRichEditCtrl [MFC], SetSel
- CRichEditCtrl [MFC], SetSelectionCharFormat
- CRichEditCtrl [MFC], SetTargetDevice
- CRichEditCtrl [MFC], SetTextMode
- CRichEditCtrl [MFC], SetUndoLimit
- CRichEditCtrl [MFC], SetWordCharFormat
- CRichEditCtrl [MFC], SetWordWrapMode
- CRichEditCtrl [MFC], StopGroupTyping
- CRichEditCtrl [MFC], StreamIn
- CRichEditCtrl [MFC], StreamOut
- CRichEditCtrl [MFC], Undo
ms.assetid: 2be52788-822c-4c27-aafd-2471231e74eb
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 03ef5135130590d142e9725e1d064b932cc7ff4d
ms.sourcegitcommit: 2aeb507a426fc7881ea59115b1d5139c0a30ba91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2018
---
# <a name="cricheditctrl-class"></a>CRichEditCtrl-Klasse
Stellt die Funktionalität des Rich-Edit-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRichEditCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditCtrl::CRichEditCtrl](#cricheditctrl)|Erstellt ein `CRichEditCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditCtrl::CanPaste](#canpaste)|Bestimmt, ob der Inhalt der Zwischenablage in dieses rich-Edit-Steuerelement eingefügt werden können.|  
|[CRichEditCtrl::CanRedo](#canredo)|Bestimmt, ob die notwendigen Aktionen in der Wiederholungswarteschlange des Steuerelements.|  
|[CRichEditCtrl::CanUndo](#canundo)|Bestimmt, ob ein Bearbeitungsvorgang rückgängig gemacht werden kann.|  
|[CRichEditCtrl::CharFromPos](#charfrompos)|Ruft Informationen über das Zeichen, die einem bestimmten Punkt im Clientbereich Edit-Steuerelement am nächsten ab.|  
|[CRichEditCtrl::Clear](#clear)|Löscht die aktuelle Auswahl an.|  
|[CRichEditCtrl::Copy](#copy)|Kopiert die aktuelle Auswahl in die Zwischenablage.|  
|[CRichEditCtrl::Create](#create)|Erstellt das rich-Edit-Steuerelement von Windows und ordnet sie dies `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::CreateEx](#createex)|Erstellt das rich-Edit-Steuerelement von Windows mit dem angegebenen erweiterten Fensterstile und ordnet sie dies `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::Cut](#cut)|Schneidet die aktuelle Auswahl in die Zwischenablage.|  
|[CRichEditCtrl::DisplayBand](#displayband)|Zeigt einen Teil des Inhalts dieses `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::EmptyUndoBuffer](#emptyundobuffer)|Zurücksetzen von Kennwörtern (löscht) das Flag zum Rückgängigmachen dieses `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::FindText](#findtext)|Sucht nach Text innerhalb dieser `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::FindWordBreak](#findwordbreak)|Sucht nach der nächsten Word Pause vor oder nach der angegebenen Zeichenposition, oder ruft Informationen über das Zeichen an dieser Position ab.|  
|[CRichEditCtrl::FormatRange](#formatrange)|Formatiert einen Textbereich für das Zielgerät für die Ausgabe an.|  
|[CRichEditCtrl::GetCharPos](#getcharpos)|Bestimmt die Position eines angegebenen Zeichens in dieser `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetDefaultCharFormat](#getdefaultcharformat)|Ruft das aktuelle Standardzeichen, die Formatierungsattribute in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetEventMask](#geteventmask)|Ruft die Ereignismaske für diesen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetFirstVisibleLine](#getfirstvisibleline)|Bestimmt die oberste sichtbare Zeile in dieser `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetIRichEditOle](#getiricheditole)|Ruft einen Zeiger auf die `IRichEditOle` -Schnittstelle für diese Rich--Steuerelement Edit.|  
|[CRichEditCtrl::GetLimitText](#getlimittext)|Ruft den Grenzwert für die Menge an Text in diese ein Benutzer eingeben kann `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetLine](#getline)|Ruft eine Textzeile aus diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetLineCount](#getlinecount)|Ruft die Anzahl der Zeilen in dieser `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetModify](#getmodify)|Bestimmt, ob der Inhalt dieses `CRichEditCtrl` Objekt seit der letzten Speicherung geändert worden sein.|  
|[CRichEditCtrl::GetOptions](#getoptions)|Ruft die rich-Edit-Steuerelement-Optionen ab.|  
|[CRichEditCtrl::GetParaFormat](#getparaformat)|Ruft die Attribute in der aktuellen Auswahl in diesem Formatieren von Absätzen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetPunctuation](#getpunctuation)|Ruft den aktuellen Interpunktionszeichen für das rich-Edit-Steuerelement ab. Diese Meldung ist nur in einer asiatischen Version des Betriebssystems verfügbar.|  
|[CRichEditCtrl::GetRect](#getrect)|Ruft die Formatierung Rechteck für dieses `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetRedoName](#getredoname)|Ruft den Typ der nächsten Aktion ab, wenn vorhanden, in der Warteschlange wiederholen.|  
|[CRichEditCtrl::GetSel](#getsel)|Ruft ab die Start- und Endposition des die aktuelle Auswahl in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetSelectionCharFormat](#getselectioncharformat)|Ruft das Zeichen, die Formatierung der Attribute in der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetSelectionType](#getselectiontype)|Ruft den Typ des Inhalts in der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetSelText](#getseltext)|Ruft den Text der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt|  
|[CRichEditCtrl::GetTextLength](#gettextlength)|Ruft die Länge des Texts, in Zeichen, die in diesem `CRichEditCtrl` Objekt. Umfasst nicht das abschließende Nullzeichen.|  
|[CRichEditCtrl::GetTextLengthEx](#gettextlengthex)|Ruft die Anzahl von Zeichen oder Bytes in der rich-Edit-Ansicht ab. Akzeptiert eine Liste von Flags an, dass die Methode zur Bestimmung der Länge des Texts in einem rich-Edit-Steuerelement|  
|[CRichEditCtrl::GetTextMode](#gettextmode)|Ruft die aktuelle Text-Modus und Rückgängigmachen Ebene eines rich-Edit-Steuerelements ab.|  
|[CRichEditCtrl::GetTextRange](#gettextrange)|Ruft den angegebenen Bereich des Texts ab.|  
|[CRichEditCtrl::GetUndoName](#getundoname)|Ruft den Typ der nächsten Rückgängigaktion ab, sofern vorhanden.|  
|[CRichEditCtrl::GetWordWrapMode](#getwordwrapmode)|Ruft den aktuellen Wortumbruch und Word wichtige Optionen für das rich-Edit-Steuerelement ab. Diese Meldung ist nur in einer asiatischen Version des Betriebssystems verfügbar.|  
|[CRichEditCtrl::HideSelection](#hideselection)|Zeigt an oder blendet Sie aus der aktuellen Auswahl.|  
|[CRichEditCtrl::LimitText](#limittext)|Schränkt die Menge des Texts, die ein Benutzer, in eingeben kann der `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::LineFromChar](#linefromchar)|Bestimmt, welche Zeile das angegebene Zeichen enthält.|  
|[CRichEditCtrl::LineIndex](#lineindex)|Ruft den Zeichenindex einer bestimmten Zeile in dieser `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::LineLength](#linelength)|Ruft die Länge einer bestimmten Zeile in dieser `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::LineScroll](#linescroll)|Scrollt den Text in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::Paste](#paste)|Fügt den Inhalt der Zwischenablage in diese rich-Edit-Steuerelement.|  
|[CRichEditCtrl::PasteSpecial](#pastespecial)|Fügt den Inhalt der Zwischenablage in diese rich-Edit-Steuerelement in das angegebene Datenformat.|  
|[CRichEditCtrl::PosFromChar](#posfromchar)|Ruft den Bereich Clientkoordinaten eines angegebenen Zeichens in einem Bearbeitungssteuerelement ab.|  
|[CRichEditCtrl::Redo](#redo)|Wiederholen die nächste Aktion in der Wiederholungswarteschlange des Steuerelements.|  
|[CRichEditCtrl::ReplaceSel](#replacesel)|Ersetzt die aktuelle Auswahl in diesem `CRichEditCtrl` Objekt mit dem angegebenen Text.|  
|[CRichEditCtrl::RequestResize](#requestresize)|Erzwingt die `CRichEditCtrl` Objekt zum Senden von Benachrichtigungen für Anforderung zum Ändern der Größe.|  
|[CRichEditCtrl::SetAutoURLDetect](#setautourldetect)|Gibt an, ob die Erkennung der Auto-URL in einem rich-Edit-Steuerelement aktiv ist.|  
|[CRichEditCtrl::SetBackgroundColor](#setbackgroundcolor)|Legt die Farbe des Hintergrunds in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetDefaultCharFormat](#setdefaultcharformat)|Legt die aktuelle Standardeinstellung Formatierungsattribute in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetEventMask](#seteventmask)|Legt die Ereignismaske für diesen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetModify](#setmodify)|Aktiviert oder deaktiviert das Flag für die Änderung für diesen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetOLECallback](#setolecallback)|Legt die `IRichEditOleCallback` COM-Objekt für dieses rich-Edit-Steuerelement.|  
|[CRichEditCtrl::SetOptions](#setoptions)|Festlegen der Optionen für diesen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetParaFormat](#setparaformat)|Legt die Attribute in der aktuellen Auswahl in diesem Formatieren von Absätzen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetPunctuation](#setpunctuation)|Legt die Interpunktionszeichen für ein rich-Edit-Steuerelement fest. Diese Meldung ist nur in einer asiatischen Version des Betriebssystems verfügbar.|  
|[CRichEditCtrl::SetReadOnly](#setreadonly)|Legt die Schreibschutzoption für diesen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetRect](#setrect)|Legt die Formatierung Rechteck für dieses `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetSel](#setsel)|Legt die Auswahl in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetSelectionCharFormat](#setselectioncharformat)|Legt die Formatierung der Attribute in der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetTargetDevice](#settargetdevice)|Legt das Zielgerät für die Ausgabe für diesen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetTextMode](#settextmode)|Legt den Text-Modus oder zum Rückgängigmachen eines rich-Edit-Steuerelements fest. Die Nachricht schlägt fehl, wenn das Steuerelement den Text enthält.|  
|[CRichEditCtrl::SetUndoLimit](#setundolimit)|Legt die maximale Anzahl von Aktionen, die in der Rückgängig-Warteschlange gespeichert werden können.|  
|[CRichEditCtrl::SetWordCharFormat](#setwordcharformat)|Legt die Formatierung der Attribute im aktuellen Wort in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetWordWrapMode](#setwordwrapmode)|Legt der Zeilenumbruch und wörtertrennung Optionen für das Rich edit-Steuerelement. Diese Meldung ist nur in einer asiatischen Version des Betriebssystems verfügbar.|  
|[CRichEditCtrl::StopGroupTyping](#stopgrouptyping)|Beendet das Steuerelement Sammeln von zusätzlichen Aktionen in der aktuellen Rückgängig-Aktion eingeben. Das Steuerelement speichert den nächsten Vorgang eingeben, ggf. in eine neue Aktion in der Warteschlange rückgängig.|  
|[CRichEditCtrl::StreamIn](#streamin)|Fügt Text aus einem Eingabedatenstrom in diese `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::StreamOut](#streamout)|Aus diesem Text speichert `CRichEditCtrl` Objekt in einen Ausgabestream.|  
|[CRichEditCtrl::Undo](#undo)|Kehrt die letzte Bearbeitung des.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "rich-Edit-Steuerelement" ist ein Fenster, in dem der Benutzer eingeben kann, und Bearbeiten von Text. Der Text kann Zeichen- und absatzformatierung zugewiesen werden und kann eingebettete OLE-Objekte enthalten. Rich-Edit-Steuerelemente bieten eine Programmierschnittstelle für die Formatierung von Text an. Komponenten der Benutzeroberfläche zum Formatierungsvorgänge für den Benutzer verfügbar machen muss jedoch eine Anwendung implementiert werden.  
  
 Diese allgemeinen Windows-Steuerelements (und somit die `CRichEditCtrl` Klasse) und höher verfügbar nur für Programme, die unter Windows 95-und Windows 98 und Windows NT, Version 3.51 ausgeführt wird. Die `CRichEditCtrl` Klasse unterstützt die Versionen 2.0 und 3.0 von der Windows-SDK für Rich-edit-Steuerelement.  
  
> [!CAUTION]
>  Bei Verwendung von einem rich-Edit-Steuerelement in einem Dialogfeld (unabhängig davon, ob Ihre Anwendung SDI, MDI oder Dialogfeldern basierende), rufen Sie [AfxInitRichEdit](application-information-and-management.md#afxinitrichedit) nach bevor das Dialogfeld im Feld angezeigt wird. Eine typische zum Aufrufen dieser Funktion ist in Ihrem Programms `InitInstance` Memberfunktion. Sie müssen nicht jedes Mal aufrufen, Sie das Dialogfeld nur beim ersten Mal anzeigen. Sie müssen keine Aufrufen `AfxInitRichEdit` bei Verwendung mit `CRichEditView`.  
  
 Weitere Informationen zur Verwendung von `CRichEditCtrl`, finden Sie unter:  
  
- [Steuerelemente](../../mfc/controls-mfc.md)  
  
- [Verwenden von CRichEditCtrl](../../mfc/using-cricheditctrl.md)  
  
-   Knowledge Base-Artikel Q259949: INFO: SetCaretPos() ist nicht geeignet mit CEdit oder CRichEditCtrl-Steuerelementen  
  
 Ein Beispiel für ein rich-Edit-Steuerelement in einer MFC_Anwendung verwenden, finden Sie unter der [WORDPAD](../../visual-cpp-samples.md) beispielanwendung.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CRichEditCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="canpaste"></a>CRichEditCtrl::CanPaste  
 Bestimmt, ob das rich-Edit-Steuerelement auf das angegebene Format der Zwischenablage einfügen kann.  
  
```  
BOOL CanPaste(UINT nFormat = 0) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nFormat`  
 Das Datenformat der Zwischenablage an der Abfrage. Dieser Parameter kann eine der vordefinierten Zwischenablageformate oder den Rückgabewert von [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049).  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Format der Zwischenablage eingefügt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nFormat` ist 0, `CanPaste` versucht jedes Format der Zwischenablage.  
  
 Weitere Informationen finden Sie unter [EM_CANPASTE](http://msdn.microsoft.com/library/windows/desktop/bb787993) Nachricht und [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) Funktion im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#1](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_1.cpp)]  
  
##  <a name="canredo"></a>CRichEditCtrl::CanRedo  
 Bestimmt, ob die Wiederholungswarteschlange alle Aktionen enthält.  
  
```  
BOOL CanRedo() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Wiederholungswarteschlange Aktionen, andernfalls 0 enthält.  
  
### <a name="remarks"></a>Hinweise  
 Um den Namen des Vorgangs in der Wiederholungswarteschlange zu ermitteln, rufen [CRichEditCtrl::GetRedoName](#getredoname). Rufen Sie zum Wiederherstellen des letzten Rückgängig-Vorgangs [wiederholen](#redo).  
  
 Weitere Informationen finden Sie unter [EM_CANREDO](http://msdn.microsoft.com/library/windows/desktop/bb787995) im Windows SDK.  
  
##  <a name="canundo"></a>CRichEditCtrl::CanUndo  
 Bestimmt, ob die letzte Bearbeitung des rückgängig gemacht werden kann.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die letzte Bearbeitung durch einen Aufruf von rückgängig gemacht werden, kann die [Rückgängig](#undo) Memberfunktion; 0, wenn sie kann nicht rückgängig gemacht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#2](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_2.cpp)]  
  
##  <a name="charfrompos"></a>CRichEditCtrl::CharFromPos  
 Ruft Informationen über das Zeichen an der durch den Parameter angegebene Punkt `pt`.  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt, das die Koordinaten der angegebenen Punkt enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Zeichenindex des Zeichens am nächsten angegebenen Punkt. Wenn der angegebene Zeitpunkt hinter dem letzten Zeichen in das Steuerelement ist, gibt der Rückgabewert das letzte Zeichen im Steuerelement an.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion funktioniert mit einem rich-Edit-Steuerelement. Rufen Sie zum Abrufen der Informationen für ein Bearbeitungssteuerelement [CEdit::CharFromPos](../../mfc/reference/cedit-class.md#charfrompos).  
  
 Weitere Informationen finden Sie unter [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) im Windows SDK.  
  
##  <a name="clear"></a>CRichEditCtrl::Clear  
 Löscht (deaktiviert) die aktuelle Auswahl (sofern vorhanden) in das Rich-edit-Steuerelement.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Löschen von ausgeführten **deaktivieren** können rückgängig gemacht werden, durch Aufrufen der [Rückgängig](#undo) Memberfunktion.  
  
 Rufen Sie zum Löschen der aktuellen Auswahl, und fügen Sie den gelöschten Inhalt in die Zwischenablage, die [Ausschneiden](#cut) Memberfunktion.  
  
 Weitere Informationen finden Sie unter [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#3](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_3.cpp)]  
  
##  <a name="copy"></a>CRichEditCtrl::Copy  
 Kopiert die aktuelle Auswahl (sofern vorhanden) im rich-Edit-Steuerelement in die Zwischenablage.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#4](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_4.cpp)]  
  
##  <a name="create"></a>CRichEditCtrl::Create  
 Erstellt das rich-Edit-Steuerelement von Windows und ordnet sie dies `CRichEditCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Bearbeitungssteuerelement-Stil. Wenden Sie eine Kombination der Fensterstile aufgeführt, die der **"Hinweise"** Abschnitt unten, und [bearbeiten Steuerelementtypen für die](http://msdn.microsoft.com/library/windows/desktop/bb775464), im Windows SDK beschrieben.  
  
 `rect`  
 Gibt des Bearbeitungssteuerelements Größe und Position. Kann eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 `pParentWnd`  
 Gibt an, das Steuerelement zum Bearbeiten des übergeordneten Fensters (häufig eine [CDialog](../../mfc/reference/cdialog-class.md)). Es muss nicht **NULL**.  
  
 `nID`  
 Gibt den Edit-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CRichEditCtrl` Objekt in zwei Schritten. Rufen Sie zunächst die [CRichEditCtrl](#cricheditctrl) Konstruktor, rufen Sie anschließend **erstellen**, das erstellt die Windows-Bearbeitungssteuerelements und fügt es der `CRichEditCtrl` Objekt.  
  
 Wenn Sie ein rich-Edit-Steuerelement mit dieser Funktion erstellen, müssen zunächst die erforderlichen-Bibliothek für Standardsteuerelemente laden. Um die Bibliothek zu laden, rufen Sie die globale Funktion [AfxInitRichEdit](application-information-and-management.md#afxinitrichedit), der wiederum die Bibliothek für Standardsteuerelemente initialisiert. Aufrufen, müssen Sie `AfxInitRichEdit` nur einmal innerhalb des Prozesses.  
  
 Wenn **erstellen** ausgeführt wird, sendet Windows die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), und [WM_ GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Nachrichten an das Steuerelement zum Bearbeiten.  
  
 Diese Nachrichten werden standardmäßig verarbeitet der [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), und [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standard-Meldungsbehandlung zu erweitern, leiten Sie eine Klasse von `CRichEditCtrl`, eine meldungszuordnung an die neue Klasse hinzufügen und die oben genannten Meldungshandler Memberfunktionen überschreiben. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für die neue Klasse.  
  
 Übernehmen Sie die folgenden [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) auf das Bearbeitungssteuerelement.  
  
- **WS_CHILD** immer.  
  
- **WS_VISIBLE** in der Regel.  
  
- **WS_DISABLED** selten.  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen.  
  
- **WS_TABSTOP** Edit-Steuerelement in der Tabulatorreihenfolge eingeschlossen.  
  
 Weitere Informationen zu Fensterstile, finden Sie unter [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#5](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_5.cpp)]  
  
##  <a name="createex"></a>CRichEditCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster) und ordnet sie der `CRichEditCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
 `dwStyle`  
 Gibt das Bearbeitungssteuerelement-Stil. Eine Kombination der Fensterstile abgelesen gelten die **"Hinweise"** Abschnitt [erstellen](#create) und [bearbeiten Steuerelementtypen für die](http://msdn.microsoft.com/library/windows/desktop/bb775464), im Windows SDK beschrieben.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die beschreibt, die Größe und Position des Fensters erstellt werden, in Clientkoordinaten der `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement übergeordnet ist.  
  
 `nID`  
 Das Steuerelement untergeordnete Fenster-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von **erstellen** anzuwendende erweiterten Fensterstile, angegeben durch die Windows-erweiterten Stil ihm etwas voranzustellen **WS_EX_**.  
  
##  <a name="cricheditctrl"></a>CRichEditCtrl::CRichEditCtrl  
 Erstellt ein `CRichEditCtrl`-Objekt.  
  
```  
CRichEditCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [erstellen](#create) So erstellen Sie die Windows Rich-edit-Steuerelement.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#6](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_6.cpp)]  
  
##  <a name="cut"></a>CRichEditCtrl::Cut  
 Löschen (Teilstücke) die aktuelle Auswahl (sofern vorhanden) in der Rich edit-Steuerelement und den gelöschten Text in die Zwischenablage kopiert.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Löschen von ausgeführten **Ausschneiden** können rückgängig gemacht werden, durch Aufrufen der [rückgängig machen](#undo) Memberfunktion.  
  
 Um die aktuelle Auswahl ohne platzieren den gelöschten Text in die Zwischenablage zu löschen, rufen die [deaktivieren](#clear) Memberfunktion.  
  
 Weitere Informationen finden Sie unter [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#7](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_7.cpp)]  
  
##  <a name="displayband"></a>CRichEditCtrl::DisplayBand  
 Zeigt einen Teil des Inhalts des rich-Edit-Steuerelements (Text und OLE-Elemente), wie bereits formatiert [FormatRange](#formatrange).  
  
```  
BOOL DisplayBand(LPRECT pDisplayRect);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisplayRect`  
 Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das den Bereich des Geräts anzuzeigenden Text angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Anzeige des formatierten Text, andernfalls 0 erfolgreich ausgeführt wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Text und die OLE-Elemente werden in den Bereich, der vom Zeiger angegeben abgeschnitten `pDisplayRect`.  
  
 Weitere Informationen finden Sie unter [EM_DISPLAYBAND](http://msdn.microsoft.com/library/windows/desktop/bb787997) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditCtrl::FormatRange](#formatrange).  
  
##  <a name="emptyundobuffer"></a>CRichEditCtrl::EmptyUndoBuffer  
 Das Flag "Rückgängig" dieses rich-Edit-Steuerelements (clear) wird zurückgesetzt.  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement werden kann nicht die letzte Bearbeitung des rückgängig gemacht. Der Rückgängig-Flag wird festgelegt, wenn ein Vorgang innerhalb des rich-Edit-Steuerelements rückgängig gemacht werden kann.  
  
 Das Flag zum Rückgängigmachen wird automatisch gelöscht, bei jedem Aufruf der [CWnd](../../mfc/reference/cwnd-class.md) Memberfunktion [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
 Weitere Informationen finden Sie unter [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#8](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_8.cpp)]  
  
##  <a name="findtext"></a>CRichEditCtrl::FindText  
 Sucht nach Text innerhalb des rich-Edit-Steuerelements.  
  
```  
long FindText(
    DWORD dwFlags,  
    FINDTEXTEX* pFindText) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Eine Liste der möglichen Werte finden Sie unter `wParam` in [EM_FINDTEXTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788011) im Windows SDK.  
  
 *pFindText*  
 Zeiger auf die [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) strukturieren, erteilen die Parameter für die Suche und Rückgabe des Bereichs, in dem die Übereinstimmung gefunden wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Zeichenposition mit der nächsten Übereinstimmung; -1, wenn keine Übereinstimmungen vorhanden sind.  
  
### <a name="remarks"></a>Hinweise  
 Suche können Sie entweder nach oben oder unten im richtigen Bereich parametereinstellung der [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur innerhalb der **FINDTEXTEX** Struktur.  
  
 Weitere Informationen finden Sie unter [EM_FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb788011) Nachricht und [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) Struktur im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#9](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_9.cpp)]  
  
##  <a name="findwordbreak"></a>CRichEditCtrl::FindWordBreak  
 Sucht nach der nächsten Word Pause vor oder nach der angegebenen Position `nStart`.  
  
```  
DWORD FindWordBreak(
    UINT nCode,  
    DWORD nStart) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nCode`  
 Gibt die auszuführende Aktion an. Eine Liste der möglichen Werte, finden Sie in der Beschreibung für den Parameter `code` in **EM_FINDWORDBREAK** im Windows SDK.  
  
 `nStart`  
 Die nullbasierte Zeichenposition, ab.  
  
### <a name="return-value"></a>Rückgabewert  
 Basierend auf dem Parameter `nCode`. Weitere Informationen finden Sie unter [EM_FINDWORDBREAK](http://msdn.microsoft.com/library/windows/desktop/bb788018) im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Memberfunktion verwenden, zum Abrufen von Informationen zu einem Zeichen an der angegebenen Position.  
  
##  <a name="formatrange"></a>CRichEditCtrl::FormatRange  
 Formatiert einen Textbereich in einem rich-Edit-Steuerelement für ein bestimmtes Gerät.  
  
```  
long FormatRange(
    FORMATRANGE* pfr,  
    BOOL bDisplay = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *PFR*  
 Zeiger auf die [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) Struktur enthält Informationen zu den Ausgabegerät. **NULL** gibt an, dass die zwischengespeicherten Informationen im rich-Edit-Steuerelement freigegeben werden kann.  
  
 *bDisplay*  
 Gibt an, ob der Text gerendert werden soll. Wenn **"false"**, der Text einfach gemessen wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des letzten Zeichens, die in der Region plus 1 entspricht.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel wird dieser Aufruf folgen, durch einen Aufruf von [DisplayBand](#displayband).  
  
 Weitere Informationen finden Sie unter [EM_FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb788020) Nachricht und [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) Struktur im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#10](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_10.cpp)]  
  
##  <a name="getcharpos"></a>CRichEditCtrl::GetCharPos  
 Ruft die Position (linke obere Ecke) eines angegebenen Zeichens in dieser `CRichEditCtrl` Objekt.  
  
```  
CPoint GetCharPos(long lChar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lChar`  
 Nullbasierter Index des Zeichens.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position der linken oberen Ecke des durch angegebene Zeichen `lChar`.  
  
### <a name="remarks"></a>Hinweise  
 Das Zeichen wird durch die Vergabe ihres nullbasierten Indexwerts angegeben. Wenn `lChar` ist größer als der Index des letzten Zeichens in dieser `CRichEditCtrl` -Objekt, der Rückgabewert gibt die Koordinaten der Position des Zeichens hinter dem letzten Zeichen in dieser `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) im Windows SDK.  
  
##  <a name="getdefaultcharformat"></a>CRichEditCtrl::GetDefaultCharFormat  
 Ruft das Standardzeichen Formatierungsattribute dieses `CRichEditCtrl` Objekt.  
  
```  
DWORD GetDefaultCharFormat(CHARFORMAT& cf) const;  DWORD GetDefaultCharFormat(CHARFORMAT2& cf) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 In der ersten Version, ein Zeiger auf eine **CHARFORMAT** Struktur des Standardzeichensatzes Formatierungsattribute.  
  
 In der zweiten Version, ein Zeiger auf eine **CHARFORMAT2** -Struktur, die eine Rich Edit 2.0-Erweiterung ist auf die **CHARFORMAT** Struktur des Standardzeichensatzes Formatierungsattribute aufrechterhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die **DwMask** Datenmember `cf`. Angabe des Standardzeichensatzes Formatierungsattribute.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter der **EM_GETCHARFORMAT** Nachricht und die **CHARFORMAT** und **CHARFORMAT2** Strukturen im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [SetDefaultCharFormat](#setdefaultcharformat).  
  
##  <a name="geteventmask"></a>CRichEditCtrl::GetEventMask  
 Ruft die Ereignismaske für `CRichEditCtrl` Objekt.  
  
```  
long GetEventMask() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ereignismaske für diesen `CRichEditCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Ereignismaske gibt an, welche Benachrichtigungen der `CRichEditCtrl` Objekt an das übergeordnete Fenster sendet.  
  
 Weitere Informationen finden Sie unter [EM_GETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb788032) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditCtrl::SetEventMask](#seteventmask).  
  
##  <a name="getfirstvisibleline"></a>CRichEditCtrl::GetFirstVisibleLine  
 Bestimmt die oberste sichtbare Zeile in dieser `CRichEditCtrl` Objekt.  
  
```  
int GetFirstVisibleLine() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierten Index des der obersten sichtbaren Zeile in dieser `CRichEditCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#11](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_11.cpp)]  
  
##  <a name="getiricheditole"></a>CRichEditCtrl::GetIRichEditOle  
 Greift auf die **IRichEditOle** für diese Schnittstelle `CRichEditCtrl` Objekt.  
  
```  
IRichEditOle* GetIRichEditOle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf die [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) -Schnittstelle, die verwendet werden kann, den Zugriff auf dieses `CRichEditCtrl` OLE-Funktionalität des Objekts. **NULL** ist die Schnittstelle nicht zugegriffen werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Schnittstelle den Zugriff auf dieses `CRichEditCtrl` OLE-Funktionen des Objekts.  
  
 Weitere Informationen finden Sie unter [EM_GETOLEINTERFACE](http://msdn.microsoft.com/library/windows/desktop/bb788041) Nachricht und [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) Schnittstelle im Windows SDK.  
  
##  <a name="getlimittext"></a>CRichEditCtrl::GetLimitText  
 Ruft den Text-Grenzwert für diesen `CRichEditCtrl` Objekt.  
  
```  
long GetLimitText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Text Grenzwert in Bytes, der für diesen `CRichEditCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Text-Grenzwert die Höchstmenge des Texts an, in Bytes ist, kann das rich-Edit-Steuerelement akzeptieren.  
  
 Weitere Informationen finden Sie unter [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#12](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_12.cpp)]  
  
##  <a name="getline"></a>CRichEditCtrl::GetLine  
 Ruft eine Textzeile aus diesem `CRichEditCtrl` Objekt.  
  
```  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer) const;  
  
int GetLine(
    int nIndex,  
    LPTSTR lpszBuffer,  
    int nMaxLength) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Nullbasierte Index der Zeile abgerufen.  
  
 `lpszBuffer`  
 Verweist auf den Puffer zur Aufnahme von Text. Das erste Wort des Puffers muss die maximale Anzahl von Bytes angeben, die in den Puffer kopiert werden können.  
  
 `nMaxLength`  
 Maximale Anzahl von Zeichen, die in kopiert werden können `lpszBuffer`. Die zweite Form der `GetLine` wird dieser Wert in den das erste Wort des Puffers gemäß `lpszBuffer`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen in kopiert `lpszBuffer`.  
  
### <a name="remarks"></a>Hinweise  
 Der kopierte Zeile enthält kein abschließendes Nullzeichen.  
  
> [!NOTE]
>  Da das erste Wort des Puffers die Anzahl der zu kopierenden Zeichen gespeichert werden, stellen Sie sicher, dass der Puffer mit mindestens 4 Bytes lang ist.  
  
 Weitere Informationen finden Sie unter [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>CRichEditCtrl::GetLineCount  
 Ruft die Anzahl der Zeilen in der `CRichEditCtrl` Objekt.  
  
```  
int GetLineCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeilen in dieser `CRichEditCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#13](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_13.cpp)]  
  
##  <a name="getmodify"></a>CRichEditCtrl::GetModify  
 Bestimmt, ob der Inhalt dieses `CRichEditCtrl` Objekt geändert wurden.  
  
```  
BOOL GetModify() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der Text in diesem `CRichEditCtrl` Objekt geändert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Windows verwaltet ein internes Flag gibt an, ob der Inhalt des rich-Edit-Steuerelements geändert wurde. Dieses Flag wird gelöscht, wenn der Edit-Steuerelement erstellt wird, und auch werden, durch den Aufruf gelöscht kann der [SetModify](#setmodify) Memberfunktion.  
  
 Weitere Informationen finden Sie unter [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#14](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_14.cpp)]  
  
##  <a name="getoptions"></a>CRichEditCtrl::GetOptions  
 Ruft die derzeit für das rich-Edit-Steuerelement festgelegten Optionen ab.  
  
```  
UINT GetOptions() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Kombination der aktuellen Optionswerte-Flag. Eine Liste der folgenden Werte sind, finden Sie unter der *fOptions* Parameter in der [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254) Nachricht, wie im Windows SDK beschrieben.  
  
##  <a name="getparaformat"></a>CRichEditCtrl::GetParaFormat  
 Ruft die Attribute der aktuellen Auswahl absatzformatierung.  
  
```  
DWORD GetParaFormat(PARAFORMAT& pf) const;  DWORD GetParaFormat(PARAFORMAT2& pf) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pf`  
 In der ersten Version, ein Zeiger auf eine [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) Struktur, um die Attribute der aktuellen Auswahl formatieren von Absätzen aufzunehmen.  
  
 In der zweiten Version, ein Zeiger auf eine [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) -Struktur, die eine Rich Edit 2.0-Erweiterung ist auf die **PARAFORMAT** Struktur des Standardzeichensatzes Formatierungsattribute aufrechterhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die **DwMask** Datenmember `pf`. Es gibt die absatzformatierung Attribute, die innerhalb der aktuellen Auswahl konsistent sind.  
  
### <a name="remarks"></a>Hinweise  
 Wenn mehr als ein Absatz ausgewählt ist, `pf` empfängt die Attribute aus dem ersten ausgewählten Absatz. Der Rückgabewert gibt an, welche Attribute in der gesamten die Auswahl konsistent sind.  
  
 Weitere Informationen finden Sie unter der [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) Nachricht und die **PARAFORMAT** und **PARAFORMAT2** Strukturen im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditCtrl::SetParaFormat](#setparaformat).  
  
##  <a name="getpunctuation"></a>CRichEditCtrl::GetPunctuation  
 Ruft den aktuellen Satzzeichen in einem rich-Edit-Steuerelement ab.  
  
```  
BOOL GetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `fType`  
 Satzzeichen Typ-Flag, wie beschrieben in der `fType` Parameter [EM_GETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774184) im Windows SDK.  
  
 `lpPunc`  
 Ein Zeiger auf eine [SATZZEICHEN](http://msdn.microsoft.com/library/windows/desktop/bb787944) strukturieren, wie im Windows SDK beschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist mit nur die asiatischen Versionen des Betriebssystems verfügbar.  
  
##  <a name="getrect"></a>CRichEditCtrl::GetRect  
 Ruft die Formatierung Rechteck für dieses `CRichEditCtrl` Objekt.  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md) oder ein Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) zum Empfangen der Formatierung Rechtecks dieses `CRichEditCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Formatierung Rechteck ist das umschließende Rechteck für den Text. Dieser Wert ist unabhängig von der Größe der `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [LimitText](#limittext).  
  
##  <a name="getredoname"></a>CRichEditCtrl::GetRedoName  
 Ruft den Typ der nächsten verfügbaren Aktion in der Wiederholungswarteschlange ab, sofern vorhanden.  
  
```  
UNDONAMEID GetRedoName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall `GetRedoName` gibt die [UNDONAMEID](http://msdn.microsoft.com/library/windows/desktop/bb774365) Enumerationstyp, der die nächste Aktion in der Wiederholungswarteschlange des Steuerelements angibt. Wenn die Wiederholungswarteschlange leer ist oder wenn die Redo-Aktion in der Warteschlange einen unbekannten Typ ist `GetRedoName` gibt 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Typen von Aktionen, die rückgängig gemacht oder wiederholt werden können umfassen eingeben, Delete, Drag & Drop, Ausschneiden und einfügen. Diese Informationen können bei Anwendungen nützlich sein, die eine erweiterte Benutzeroberfläche für rückgängig und wiederholen-Vorgänge, z. B. ein Dropdown-Listenfeld redoable Aktionen bereitstellen.  
  
##  <a name="getsel"></a>CRichEditCtrl::GetSel  
 Ruft die Grenzen des die aktuelle Auswahl in diesem `CRichEditCtrl` Objekt.  
  
```  
void GetSel(CHARRANGE& cr) const;  
  
void GetSel(
    long& nStartChar,  
    long& nEndChar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `cr`  
 Ein Verweis auf eine [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur, um die Grenzen der aktuellen Auswahl erhalten.  
  
 `nStartChar`  
 Nullbasierte Index des ersten Zeichens in der aktuellen Auswahl.  
  
 `nEndChar`  
 Nullbasierte Index des letzten Zeichens in der aktuellen Auswahl.  
  
### <a name="remarks"></a>Hinweise  
 Die zwei Arten von dieser Funktion geben Sie alternative Möglichkeiten, die Grenzen für die Auswahl zu erhalten. Führen Sie die kurze Beschreibungen der folgenden Formen:  
  
- **Memberfunktion GetSel (** `cr` **)** dieses Formular verwendet die **CHARRANGE** Struktur mit seiner **CpMin** und **CpMax** Elemente, die die Grenzen zurück.  
  
- **Memberfunktion GetSel (** `nStartChar` **,** `nEndChar` **)** dieses Formular gibt die Grenzen in den Parametern `nStartChar` und `nEndChar`.  
  
 Die Auswahl enthält alles, was, wenn der Anfang ( **CpMin** oder `nStartChar`) ist 0 und das Ende ( **CpMax** oder `nEndChar`) ist - 1.  
  
 Weitere Informationen finden Sie unter [EM_EXGETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788001) Nachricht und [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#15](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_15.cpp)]  
  
##  <a name="getselectioncharformat"></a>CRichEditCtrl::GetSelectionCharFormat  
 Ruft das Zeichen, die Attribute der aktuellen Auswahl formatieren.  
  
```  
DWORD GetSelectionCharFormat(CHARFORMAT& cf) const;  DWORD GetSelectionCharFormat(CHARFORMAT2& cf) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 In der ersten Version, ein Zeiger auf eine [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Struktur, um die Attribute der aktuellen Auswahl formatieren von Zeichen zu empfangen.  
  
 In der zweiten Version, ein Zeiger auf eine [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) -Struktur, die eine Rich Edit 2.0-Erweiterung ist auf die **CHARFORMAT** Struktur, um die Attribute der aktuellen Auswahl formatieren von Zeichen zu empfangen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die **DwMask** Datenmember `cf`. Es gibt an, der die zeichenformatierung Attribute, die innerhalb der aktuellen Auswahl konsistent sind.  
  
### <a name="remarks"></a>Hinweise  
 Die `cf` Parameter erhält die Attribute des ersten Zeichens in der aktuellen Auswahl. Der Rückgabewert gibt an, welche Attribute in der gesamten die Auswahl konsistent sind.  
  
 Weitere Informationen finden Sie unter der [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) Nachricht und die **CHARFORMAT** und **CHARFORMAT2** Strukturen im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [SetSelectionCharFormat](#setselectioncharformat).  
  
##  <a name="getselectiontype"></a>CRichEditCtrl::GetSelectionType  
 Bestimmt den Auswahltyp in diesem `CRichEditCtrl` Objekt.  
  
```  
WORD GetSelectionType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Flags, die angibt, den Inhalt der aktuellen Auswahl. Eine Kombination der folgenden Flags:  
  
- `SEL_EMPTY`Gibt an, dass keine aktuelle Auswahl vorhanden ist.  
  
- `SEL_TEXT`Gibt an, dass die aktuelle Auswahl Text enthält.  
  
- `SEL_OBJECT`Gibt an, dass die aktuelle Auswahl mindestens ein OLE-Element enthält.  
  
- `SEL_MULTICHAR`Gibt an, dass die aktuelle Auswahl mehr als ein Zeichen des Texts enthält.  
  
- `SEL_MULTIOBJECT`Gibt an, dass die aktuelle Auswahl mehrere OLE-Objekts enthält.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_SELECTIONTYPE](http://msdn.microsoft.com/library/windows/desktop/bb774223) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#16](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_16.cpp)]  
  
##  <a name="getseltext"></a>CRichEditCtrl::GetSelText  
 Ruft den Text ab, in der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt.  
  
```  
long GetSelText(LPSTR lpBuf) const;  CString GetSelText() const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Zeiger auf den Puffer zur Aufnahme von Text in der aktuellen Auswahl.  
  
### <a name="return-value"></a>Rückgabewert  
 Hängt davon ab, auf dem Formular:  
  
- **Memberfunktion GetSelText (** `lpBuf` **)** die Anzahl der Zeichen in kopiert `lpBuf`, jedoch ohne den null-Terminierung.  
  
- **Memberfunktion GetSelText ()** die Zeichenfolge, die die aktuelle Auswahl enthält.  
  
### <a name="remarks"></a>Hinweise  
 Bei Verwendung die erste Form stellt **Memberfunktion GetSelText (** `lpBuf` **)**, müssen Sie sicherstellen, dass der Puffer groß genug ist, für den Text ist, er erhält. Rufen Sie [Memberfunktion GetSel](#getsel) um die Anzahl der Zeichen in der aktuellen Auswahl zu bestimmen.  
  
 Weitere Informationen finden Sie unter [EM_GETSELTEXT](http://msdn.microsoft.com/library/windows/desktop/bb774190) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditCtrl::GetSelectionType](#getselectiontype).  
  
##  <a name="gettextlength"></a>CRichEditCtrl::GetTextLength  
 Ruft die Länge des Texts, in Zeichen, die in diesem `CRichEditCtrl` Objekts, ohne das abschließende Nullzeichen.  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge des Texts in diesem `CRichEditCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [WM_GETTEXTLENGTH](http://msdn.microsoft.com/library/windows/desktop/ms632628) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#17](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_17.cpp)]  
  
##  <a name="gettextlengthex"></a>CRichEditCtrl::GetTextLengthEx  
 Berechnet die Länge des Texts im rich-Edit-Steuerelement.  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Der Wert gibt die Methode zum Bestimmen der Länge verwendet werden. Dieser Member kann eine oder mehrere der Werte im Flags-Mitglied der aufgeführten [GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) im Windows SDK beschrieben.  
  
 `uCodePage`  
 Die Codepage für die Übersetzung (für ANSI-Codepage, 1200 für Unicode CP_ACP verwendet).  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen oder Bytes in den Edit-Steuerelement. Wenn nicht kompatible Flags, im festgelegt wurden `dwFlags`, diese Memberfunktion gibt `E_INVALIDARG`.  
  
### <a name="remarks"></a>Hinweise  
 `GetTextLengthEx`Stellt zusätzliche Methoden zum Bestimmen der Länge des Texts an. Die Funktionalität des Rich Edit 2.0 unterstützt. Finden Sie unter [über Rich-Edit-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb787873) in der Windows-SDKfor Weitere Informationen.  
  
##  <a name="gettextmode"></a>CRichEditCtrl::GetTextMode  
 Ruft die aktuelle Text-Modus und Rückgängigmachen Ebene eines rich-Edit-Steuerelements ab.  
  
```  
UINT GetTextMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Satz von Bitflags aus der [TEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774364) Enumerationstyp, der im Windows SDK beschrieben. Die Flags geben den aktuellen SMS-Modus und rückgängig-Ebene des Steuerelements.  
  
##  <a name="gettextrange"></a>CRichEditCtrl::GetTextRange  
 Ruft den angegebenen Bereich von Zeichen ab.  
  
```  
int GetTextRange(
    int nFirst,  
    int nLast,  
    CString& refString) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nFirst`  
 Die Zeichenposition indizieren unmittelbar vor das erste Zeichen im Bereich.  
  
 `nLast`  
 Die Zeichenposition, sofort nach dem letzten Zeichen im Bereich.  
  
 `refString`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den Text erhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen kopiert, nicht einschließlich des abschließenden Null-Zeichens.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_GETTEXTRANGE](http://msdn.microsoft.com/library/windows/desktop/bb774199) im Windows SDK.  
  
 `GetTextRange`unterstützt die Funktionalität des Rich Edit 2.0. Finden Sie unter [über Rich-Edit-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb787873) in der Windows-SDKfor Weitere Informationen.  
  
##  <a name="getundoname"></a>CRichEditCtrl::GetUndoName  
 Ruft den Typ der nächsten verfügbaren Aktion in der Warteschlange zum Rückgängigmachen ab, sofern vorhanden.  
  
```  
UNDONAMEID GetUndoName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn eine Rückgängig-Aktion des Steuerelements Rückgängig-Warteschlange wird `GetUndoName` gibt die [UNDONAMEID](http://msdn.microsoft.com/library/windows/desktop/bb774365) Enumerationstyp, der die nächste Aktion in der Warteschlange angibt. Wenn die Rückgängig-Warteschlange leer ist oder die Rückgängig-Aktion in der Warteschlange eines unbekannten Typs ist `GetUndoName` gibt 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Typen von Aktionen, die rückgängig gemacht oder wiederholt werden können umfassen eingeben, Delete, Drag & Drop, Ausschneiden und einfügen. Diese Informationen können bei Anwendungen nützlich sein, die eine erweiterte Benutzeroberfläche für rückgängig und wiederholen-Vorgänge, z. B. ein Dropdown-Listenfeld Aktionen bereitstellen, die rückgängig gemacht werden kann.  
  
##  <a name="getwordwrapmode"></a>CRichEditCtrl::GetWordWrapMode  
 Ruft den aktuellen Wortumbruch und Word wichtige Optionen für das rich-Edit-Steuerelement ab.  
  
```  
UINT GetWordWrapMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Wortumbruch und die Optionen für die wörtertrennung. Diese Optionen werden in beschrieben [EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294) im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist nur für asiatischen Versionen des Betriebssystems verfügbar.  
  
##  <a name="hideselection"></a>CRichEditCtrl::HideSelection  
 Ändert die Sichtbarkeit der Auswahl.  
  
```  
void HideSelection(
    BOOL bHide,  
    BOOL bPerm);
```  
  
### <a name="parameters"></a>Parameter  
 `bHide`  
 Gibt an, ob es sich bei die Auswahl angezeigt oder ausgeblendet ist, werden **"true"** So blenden Sie die Auswahl aus.  
  
 `bPerm`  
 Gibt an, ob diese Änderung der Sichtbarkeit für die Auswahl permanent sein soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bPerm` ist **"true"**, ändert der `ECO_NOHIDESEL` Option dafür `CRichEditCtrl` Objekt. Eine kurze Beschreibung dieser Option, finden Sie unter [SetOptions](#setoptions). Verwenden Sie diese Funktion, legen Sie die Optionen für diesen `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter [EM_HIDESELECTION](http://msdn.microsoft.com/library/windows/desktop/bb774210) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#18](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_18.cpp)]  
  
##  <a name="limittext"></a>CRichEditCtrl::LimitText  
 Beschränkt die Länge des Texts, der der Benutzer in einem Bearbeitungssteuerelement eingeben kann.  
  
```  
void LimitText(long nChars = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nChars`  
 Gibt die Länge (in Bytes) des Texts, der der Benutzer eingeben kann. Wenn dieser Parameter auf 0 (Standardwert) ist, wird die Textlänge auf 64 KB festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Änderungen am Grenzwert der Text wird nur den Text, den der Benutzer eingeben kann, eingeschränkt. Er wirkt sich nicht auf einen beschreibenden Text ein bereits in das Bearbeitungssteuerelement und beeinträchtigt die Länge des Texts in das Bearbeitungssteuerelement durch kopiert die [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) Memberfunktion in `CWnd`. Wenn eine Anwendung verwendet die `SetWindowText` Funktion zum Platzieren von Text in ein Bearbeitungssteuerelement als im Aufruf angegeben ist `LimitText`, der Benutzer kann den Text im Bearbeitungssteuerelement löschen. Jedoch der Grenzwert Text wird verhindert, dass den Benutzer den vorhandenen Text durch neuen Text ersetzen, führt dazu, dass den Text, der unterhalb des Limits Text fallen, sofern nicht die aktuelle Auswahl zu löschen.  
  
> [!NOTE]
>  Für die Beschränkung der Text zählt jeden OLE-Element als ein einzelnes Zeichen ein.  
  
 Weitere Informationen finden Sie unter [EM_EXLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788003) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#19](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_19.cpp)]  
  
##  <a name="linefromchar"></a>CRichEditCtrl::LineFromChar  
 Ruft die Zeilennummer der Zeile mit der angegebenen Zeichenindex ab.  
  
```  
long LineFromChar(long nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Den nullbasierte Indexwert für das gewünschte Zeichen im Text des Bearbeitungssteuerelements enthält, oder-1 enthält. Wenn `nIndex` ist-1, gibt die aktuelle Zeile, d. h. die Zeile, die den Textcursor enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die nullbasierte Zeilennummer der Zeile mit der Zeichenindex gemäß `nIndex`. Wenn `nIndex` ist-1. die Zahl der Zeile, die das erste Zeichen der Auswahl zurückgegeben. Wenn keine Auswahl vorhanden ist, wird die aktuelle Zeilennummer zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Ein Zeichenindex ist die Anzahl der Zeichen vom Anfang des rich-Edit-Steuerelements. Ein OLE-Element ist für das Zählen von Zeichen als ein einzelnes Zeichen gezählt.  
  
 Weitere Informationen finden Sie unter [EM_EXLINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb788005) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#20](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_20.cpp)]  
  
##  <a name="lineindex"></a>CRichEditCtrl::LineIndex  
 Ruft den Zeichenindex einer Zeile in dieser `CRichEditCtrl` Objekt.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nLine`  
 Den Indexwert für die gewünschte Position im Text des Bearbeitungssteuerelements enthält, oder-1 enthält. Wenn `nLine` ist-1, gibt die aktuelle Zeile, d. h. die Zeile, die den Textcursor enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeichenindex der Zeile im angegebenen `nLine` oder-1 zurück, wenn die angegebene Zeilennummer größer wird und dann die Anzahl der Zeilen im Bearbeitungssteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Der Zeichenindex ist die Anzahl der Zeichen vom Anfang des rich-Edit-Steuerelements in die angegebene Zeile.  
  
 Weitere Informationen finden Sie unter [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#21](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_21.cpp)]  
  
##  <a name="linelength"></a>CRichEditCtrl::LineLength  
 Ruft die Länge einer Zeile in einem rich-Edit-Steuerelement ab.  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nLine`  
 Gibt an, der Zeichenindex eines Zeichens in der Zeile, deren Länge abgerufen werden sollen. Wenn dieser Parameter auf-1 festgelegt, die Länge der aktuellen Zeile (die Zeile, die den Textcursor enthält) wird zurückgegeben, ausgenommen die Länge eines beliebigen Text in die Zeile ausgewählt. Wenn `LineLength` wird aufgerufen, für ein Bearbeitungssteuerelement einzeilige dieser Parameter wird ignoriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `LineLength` wird aufgerufen, für ein Bearbeitungssteuerelement für mehrzeiligen ist der Rückgabewert der Länge (in `TCHAR`) der angegebene Zeile `nLine`.  Es umfasst nicht die Zeichen Wagenrücklauf am Ende der Zeile. Wenn `LineLength` wird aufgerufen, bei einem einzeiligen Edit-Steuerelement, ist der Rückgabewert die Länge (in `TCHAR`) des Texts im Bearbeitungssteuerelement. Wenn nLine größer als die Anzahl der Zeichen im Steuerelement ist, ist der Rückgabewert 0 (null).
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [LineIndex](#lineindex) Memberfunktion einen Zeichenindex für eine bestimmte Zeilennummer innerhalb dieser abzurufenden `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [LineIndex](#lineindex).  
  
##  <a name="linescroll"></a>CRichEditCtrl::LineScroll  
 Scrollt den Text eines mehrzeiligen Bearbeitungssteuerelements an.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nLines`  
 Gibt die Anzahl der Zeilen vertikaler Bildlauf durchgeführt wird.  
  
 `nChars`  
 Gibt die Anzahl von Zeichenpositionen einen horizontalen Bildlauf durchführen. Dieser Wert wird ignoriert, wenn das rich-Edit-Steuerelement entweder verfügt die **ES_RIGHT** oder **ES_CENTER** Stil. [Bearbeiten von Stilen](../../mfc/reference/styles-used-by-mfc.md#edit-styles) werden in angegeben [erstellen](#create).  
  
### <a name="remarks"></a>Hinweise  
 Das Bearbeitungssteuerelement Bildlauf vertikal nicht hinter die letzte Zeile des Texts im Bearbeitungssteuerelement. Wenn plus die Anzahl der Zeilen, die gemäß der aktuellen Zeile `nLines` überschreitet die Gesamtanzahl der Zeilen im Bearbeitungssteuerelement, der Wert wird angepasst, damit die letzte Zeile des Bearbeitungssteuerelements an den Anfang der Edit-Steuerelement Fenster ein Bildlauf durchgeführt wird.  
  
 `LineScroll`kann verwendet werden, einen horizontalen Bildlauf hinter dem letzten Zeichen, der eine beliebige Zeile durchführen.  
  
 Weitere Informationen finden Sie unter [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetFirstVisibleLine](#getfirstvisibleline).  
  
##  <a name="paste"></a>CRichEditCtrl::Paste  
 Fügt die Daten aus der Zwischenablage in die `CRichEditCtrl` an der Einfügemarke die Position des Caretzeichens.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Hinweise  
 Daten werden eingefügt, nur dann, wenn die Zwischenablage Daten in einem anerkannten Format enthält.  
  
 Weitere Informationen finden Sie unter [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#22](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_22.cpp)]  
  
##  <a name="pastespecial"></a>CRichEditCtrl::PasteSpecial  
 Fügt Daten in einem bestimmten Zwischenablageformat in diese `CRichEditCtrl` Objekt.  
  
```  
void PasteSpecial(
    UINT nClipFormat,  
    DWORD dvAspect = 0,  
    HMETAFILE hMF = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *nClipFormat*  
 Das Format der Zwischenablage einfügen in diese `CRichEditCtrl` Objekt.  
  
 *dvAspect*  
 Gerät Aspekt für die Daten aus der Zwischenablage abgerufen werden sollen.  
  
 *hMF*  
 Handle für die Metadatei, enthält das Elementsymbol Überblick über das Objekt, das eingefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Neue Material wird an der Einfügemarke die Position der Einfügemarke eingefügt.  
  
 Weitere Informationen finden Sie unter [EM_PASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/bb774214) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#23](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_23.cpp)]  
  
##  <a name="posfromchar"></a>CRichEditCtrl::PosFromChar  
 Ruft den Bereich Clientkoordinaten eines angegebenen Zeichens in einem Bearbeitungssteuerelement ab.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nChar`  
 Der nullbasierte Index des Zeichens.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position des Zeichens, (X, y). Für eine einzeilige Bearbeitungssteuerelement ist die y-Koordinate immer 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) im Windows SDK.  
  
##  <a name="redo"></a>CRichEditCtrl::Redo  
 Wiederholen die nächste Aktion in der Wiederholungswarteschlange des Steuerelements.  
  
```  
BOOL Redo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_REDO](http://msdn.microsoft.com/library/windows/desktop/bb774218) im Windows SDK.  
  
##  <a name="replacesel"></a>CRichEditCtrl::ReplaceSel  
 Ersetzt die aktuelle Auswahl in diesem `CRichEditCtrl` Objekt mit dem angegebenen Text.  
  
```  
void ReplaceSel(
    LPCTSTR lpszNewText,  
    BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszNewText`  
 Ein Zeiger auf eine Null-terminierte Zeichenfolge, die den Ersetzungstext enthält.  
  
 `bCanUndo`  
 Um anzugeben, dass diese Funktion rückgängig gemacht werden kann, legen Sie den Wert dieses Parameters auf **"true"**. Der Standardwert ist **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Ersetzen der gesamten Text in diesem `CRichEditCtrl` -Objekts [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
 Wenn keine aktuelle Auswahl vorhanden ist, wird der Ersetzungstext an der Einfügemarke, d. h. den aktuellen Speicherort Einfügemarke eingefügt.  
  
 Diese Funktion wird mit der vorhandenen Formatieren von Zeichen den eingefügten Text formatieren. Wenn Sie den gesamten Bereich der Text ersetzen (durch Aufrufen `SetSel`(0, -1) vor dem Aufruf `ReplaceSel`), es ist ein Ende der Absatz Zeichen, das Beibehalten des vorhergehenden Absatzes Formatierung, die in durch den neu eingefügten Text geerbt.  
  
 Weitere Informationen finden Sie unter [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [LineIndex](#lineindex).  
  
##  <a name="requestresize"></a>CRichEditCtrl::RequestResize  
 Erzwingt die `CRichEditCtrl` Objekt senden **EN_REQUESTRESIZE** benachrichtigungsmeldungen an das übergeordnete Fenster.  
  
```  
void RequestResize();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nützlich bei [CWnd::OnSize](../../mfc/reference/cwnd-class.md#onsize) Verarbeitung für eine unbeschränkte `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter der [EM_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb774220) Nachricht und die **unbeschränkte Rich-Edit-Steuerelemente** Abschnitt [über Rich-Edit-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb787873) im Windows SDK.  
  
##  <a name="setautourldetect"></a>CRichEditCtrl::SetAutoURLDetect  
 Legt das rich-Edit-Steuerelement, eine URL automatisch zu erkennen.  
  
```  
BOOL SetAutoURLDetect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob das Steuerelement festgelegt ist, um eine URL automatisch zu erkennen. Wenn **"true"**, diese Einstellung aktiviert ist. Wenn **"false"**, er deaktiviert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL Wenn erfolgreich, andernfalls ungleich NULL. Beispielsweise kann die Nachricht aufgrund von unzureichendem Arbeitsspeicher fehlschlagen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn aktiviert, durchsucht das rich-Edit-Steuerelement den Text, um zu bestimmen, ob sie einen standard-URL-Format übereinstimmt. Eine Liste dieser URL-Formate, finden Sie unter [EM_AUTOURLDETECT](http://msdn.microsoft.com/library/windows/desktop/bb787991) im Windows SDK.  
  
> [!NOTE]
>  Legen Sie nicht `SetAutoURLDetect` auf **"true"** Wenn Edit-Steuerelement verwendet die **CFE_LINK** Effekt für Text als URLs. `SetAutoURLDetect`Dieser Effekt für URLs aktiviert und deaktiviert sie für den gesamten anderen Text. Finden Sie unter [EN_LINK](http://msdn.microsoft.com/library/windows/desktop/bb787970) Weitere Informationen zu den **CFE_LINK** wirksam.  
  
##  <a name="setbackgroundcolor"></a>CRichEditCtrl::SetBackgroundColor  
 Legt die Farbe des Hintergrunds für diesen `CRichEditCtrl` Objekt.  
  
```  
COLORREF SetBackgroundColor(
    BOOL bSysColor,  
    COLORREF cr);
```  
  
### <a name="parameters"></a>Parameter  
 `bSysColor`  
 Gibt an, ob die Farbe des Hintergrunds auf den Systemwert festgelegt werden soll. Wenn dieser Wert ist **"true"**, `cr` wird ignoriert.  
  
 `cr`  
 Die angeforderte Hintergrundfarbe. Verwendet nur, wenn `bSysColor` ist **"false"**.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Background-Farbe für dieses `CRichEditCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Farbe des Hintergrunds festgelegt werden kann, auf den Systemwert oder mit einem angegebenen [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert.  
  
 Weitere Informationen finden Sie unter [EM_SETBKGNDCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774228) Nachricht und [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Struktur im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#24](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_24.cpp)]  
  
##  <a name="setdefaultcharformat"></a>CRichEditCtrl::SetDefaultCharFormat  
 Legt die Formatierung der Attribute für den neuen Text in dieser `CRichEditCtrl` Objekt.  
  
```  
BOOL SetDefaultCharFormat(CHARFORMAT& cf);  
BOOL SetDefaultCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 In der ersten Version, ein Zeiger auf eine [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Struktur, die die neue Standardeinstellung zeichenformatierung Attribute enthält.  
  
 In der zweiten Version, ein Zeiger auf eine [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) -Struktur, die eine Rich Edit 2.0-Erweiterung ist auf der **CHARFORMAT** Struktur, die das Standardzeichen Formatierungsattribute enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Nur die Attribute, die gemäß der **DwMask** Mitglied `cf` , die von dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter der [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) Nachricht und die **CHARFORMAT** und **CHARFORMAT2** Strukturen im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#25](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_25.cpp)]  
  
##  <a name="seteventmask"></a>CRichEditCtrl::SetEventMask  
 Legt die Ereignismaske für diesen `CRichEditCtrl` Objekt.  
  
```  
DWORD SetEventMask(DWORD dwEventMask);
```  
  
### <a name="parameters"></a>Parameter  
 *dwEventMask*  
 Das neue Ereignismaske für diesen `CRichEditCtrl` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Ereignismaske.  
  
### <a name="remarks"></a>Hinweise  
 Die Ereignismaske gibt an, welche Benachrichtigungen der `CRichEditCtrl` Objekt an das übergeordnete Fenster sendet.  
  
 Weitere Informationen finden Sie unter [EM_SETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb774238) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#26](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_26.cpp)]  
  
##  <a name="setmodify"></a>CRichEditCtrl::SetModify  
 Aktiviert oder deaktiviert das Änderungsflag für ein Bearbeitungssteuerelement.  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bModified`  
 Der Wert **"true"** gibt an, dass der Text geändert wurde, und der Wert **"false"** gibt an, es ist unverändert. Die geänderten Kennzeichen ist standardmäßig festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Das geänderte Flag gibt an, und zwar unabhängig davon, ob der Text in das Bearbeitungssteuerelement geändert wurde. Es wird automatisch festgelegt, wenn der Benutzer den Text ändert. Der Wert abgerufen werden kann, mit der [GetModify](#getmodify) Memberfunktion.  
  
 Weitere Informationen finden Sie unter [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetModify](#getmodify).  
  
##  <a name="setolecallback"></a>CRichEditCtrl::SetOLECallback  
 Dadurch `CRichEditCtrl` Objekt ein **IRichEditOleCallback** Objekt, mit dem OLE-bezogene Ressourcen und Informationen zu erhalten.  
  
```  
BOOL SetOLECallback(IRichEditOleCallback* pCallback);
```  
  
### <a name="parameters"></a>Parameter  
 `pCallback`  
 Zeiger auf eine [IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308) Objekt, das dieses `CRichEditCtrl` Objekt wird verwenden, um OLE-bezogene Ressourcen und Informationen zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Dies `CRichEditCtrl` Objekt ruft [IUnknown:: AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) zum Erhöhen der Verwendungszähler für die COM-Objekt, das vom angegebenen `pCallback`.  
  
 Weitere Informationen finden Sie unter [EM_SETOLECALLBACK](http://msdn.microsoft.com/library/windows/desktop/bb774252) Nachricht und [IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308) Schnittstelle im Windows SDK.  
  
##  <a name="setoptions"></a>CRichEditCtrl::SetOptions  
 Festlegen der Optionen für diesen `CRichEditCtrl` Objekt.  
  
```  
void SetOptions(
    WORD wOp,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *wOp*  
 Gibt den Typ des Vorgangs an. Einer der folgenden Werte:  
  
- `ECOOP_SET`Festlegen der Optionen für den vom angegebenen `dwFlags`.  
  
- `ECOOP_OR`Kombinieren Sie die aktuellen Optionen mit den vom angegebenen `dwFlags`.  
  
- `ECOOP_AND`Behalten Sie nur die aktuellen Optionen, die auch vom angegebenen `dwFlags`.  
  
- `ECOOP_XOR`Logisch XOR-Operation mit den angegebenen, durch die aktuellen Optionen `dwFlags`.  
  
 `dwFlags`  
 Rich-edit-Optionen. Die Flagwerte sind im Abschnitt "Hinweise" aufgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Die Optionen können eine Kombination der folgenden Werte sein:  
  
- `ECO_AUTOWORDSELECTION`Automatische Auswahl Doppelklicken Sie auf.  
  
- `ECO_AUTOVSCROLL`Text rechts scrollt durch automatisch von 10 Zeichen, wenn der Benutzer am Ende der Zeile ein Zeichen eingibt. Wenn der Benutzer die EINGABETASTE drückt, verschiebt das Steuerelement alle Text an Position 0 (null) zurück.  
  
- `ECO_AUTOHSCROLL`Wenn der Benutzer in der letzten Zeile die EINGABETASTE drückt automatisch den Bildlauf eine Seite nach oben.  
  
- `ECO_NOHIDESEL`Negiert das Standardverhalten für ein Bearbeitungssteuerelement. Das Standardverhalten Blendet die Auswahl auf, wenn das Steuerelement den Eingabefokus verliert und die Auswahl, zeigt Wenn das Steuerelement den Eingabefokus erhält. Bei Angabe von `ECO_NOHIDESEL`, der ausgewählte Text umkehren, auch wenn das Steuerelement den Fokus nicht verfügt.  
  
- `ECO_READONLY`Verhindert, dass der Benutzer eingeben oder Bearbeiten von Text im Bearbeitungssteuerelement.  
  
- `ECO_WANTRETURN`Gibt an, dass ein Wagenrücklauf eingefügt werden, wenn der Benutzer die EINGABETASTE drückt, während der Eingabe von Text in ein mehrzeiliges rich-Edit-Steuerelement in einem Dialogfeld. Wenn Sie dieses Format nicht angeben, sendet das Drücken der EINGABETASTE einen Befehl an das rich-Edit-Steuerelement übergeordnetes Fenster, die imitiert, auf das übergeordnete Fenster Standardschaltfläche (z. B. die Schaltfläche "OK" in einem Dialogfeld). Dieses Format wirkt sich nicht auf ein einzeiliges Steuerelement zu bearbeiten.  
  
- `ECO_SAVESEL`Behält die Auswahl, wenn das Steuerelement den Fokus verliert. Standardmäßig werden der gesamte Inhalt des Steuerelements ausgewählt, wenn es den Fokus erhält wieder.  
  
- `ECO_VERTICAL`Zeichnet Text und Objekte in vertikaler Richtung. Bei nur asiatische Sprachen verfügbar.  
  
 Weitere Informationen finden Sie unter [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#27](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_27.cpp)]  
  
##  <a name="setparaformat"></a>CRichEditCtrl::SetParaFormat  
 Legt die Attribute für die aktuelle Auswahl in diesem Formatieren von Absätzen `CRichEditCtrl` Objekt.  
  
```  
BOOL SetParaFormat(PARAFORMAT& pf);  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>Parameter  
 `pf`  
 In der ersten Version, ein Zeiger auf eine [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) Struktur, die den neuen Standard enthält Absatz Formatierungsattribute.  
  
 In der zweiten Version, ein Zeiger auf eine [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) -Struktur, die eine Rich Edit 2.0-Erweiterung ist auf die **PARAFORMAT** Struktur des Standardzeichensatzes Formatierungsattribute aufrechterhält.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Nur die Attribute, die gemäß der **DwMask** Mitglied `pf` , die von dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter der [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) Nachricht und die **PARAFORMAT** und **PARAFORMAT2** Strukturen im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#28](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_28.cpp)]  
  
##  <a name="setpunctuation"></a>CRichEditCtrl::SetPunctuation  
 Legt die Satzzeichen in einem rich-Edit-Steuerelement fest.  
  
```  
BOOL SetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc);
```  
  
### <a name="parameters"></a>Parameter  
 `fType`  
 Das Flag Satzzeichen. Eine Liste der möglichen Werte finden Sie unter der `fType` -Parameter für [EM_SETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774278) im Windows SDK.  
  
 `lpPunc`  
 Ein Zeiger auf eine [SATZZEICHEN](http://msdn.microsoft.com/library/windows/desktop/bb787944) strukturieren, wie im Windows SDK beschrieben.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL bei Erfolg, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird für nur asiatischen Versionen des Betriebssystems verfügbar.  
  
##  <a name="setreadonly"></a>CRichEditCtrl::SetReadOnly  
 Ändert die `ECO_READONLY` Option dafür `CRichEditCtrl` Objekt.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bReadOnly`  
 Gibt an, wenn diese `CRichEditCtrl` Objekt nur gelesen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Eine kurze Beschreibung dieser Option, finden Sie unter [SetOptions](#setoptions). Verwenden Sie diese Funktion, legen Sie die Optionen für diesen `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#29](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_29.cpp)]  
  
##  <a name="setrect"></a>CRichEditCtrl::SetRect  
 Legt die Formatierung Rechteck für dieses `CRichEditCtrl` Objekt.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md) oder ein Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) , der die neuen Grenzen für die Formatierung Rechteck angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Formatierung Rechteck handelt es sich um die begrenzenden Rechteck für den Text. Die begrenzende Rechteck ist unabhängig von der Größe des Fensters rich-Edit-Steuerelement. Wenn dies `CRichEditCtrl` Objekt zuerst erstellt wird, wird die Formatierung Rechteck ist die gleiche Größe wie das den Clientbereich des Fensters. Verwendung `SetRect` die Formatierung Rechteck größer oder kleiner als das rich-Edit-Fenster erstellt.  
  
 Weitere Informationen finden Sie unter [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#30](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_30.cpp)]  
  
##  <a name="setsel"></a>CRichEditCtrl::SetSel  
 Legt die Auswahl in dieser `CRichEditCtrl` Objekt.  
  
```  
void SetSel(
    long nStartChar,  
    long nEndChar);  
  
void SetSel(CHARRANGE& cr);
```  
  
### <a name="parameters"></a>Parameter  
 `nStartChar`  
 Nullbasierte Index des ersten Zeichens für die Auswahl.  
  
 `nEndChar`  
 Nullbasierte Index des letzten Zeichens, für die Auswahl.  
  
 `cr`  
 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur, die die Grenzen der aktuellen Auswahl enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die zwei Arten von dieser Funktion geben Sie alternative Möglichkeiten, um die Grenzen für die Auswahl festzulegen. Führen Sie die kurze Beschreibungen der folgenden Formen:  
  
- **Memberfunktion SetSel (** `cr` **)** dieses Formular verwendet die **CHARRANGE** Struktur mit seiner **CpMin** und **CpMax** Elemente, die die Grenzen festgelegt.  
  
- **Memberfunktion SetSel (** `nStartChar` **,** `nEndChar` **)** dieser Form verwenden Sie die Parameter `nStartChar` und `nEndChar` des gültigen Bereichs festlegen.  
  
 Die Einfügemarke befindet sich am Ende der Auswahl des Beginns größer erkennbar ( **CpMin** oder `nStartChar`) und Ende ( **CpMax** oder `nEndChar`) Indizes. Diese Funktion führt einen Bildlauf durch den Inhalt der `CRichEditCtrl` , damit der Textcursor angezeigt wird.  
  
 Wählen Sie sämtlichen Text in dieser `CRichEditCtrl` -Objekt, rufen Sie `SetSel` mit einem startIndex von 0 und ein endIndex von - 1.  
  
 Weitere Informationen finden Sie unter [EM_EXSETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788007) Nachricht und [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Memberfunktion GetSel](#getsel).  
  
##  <a name="setselectioncharformat"></a>CRichEditCtrl::SetSelectionCharFormat  
 Legt die Formatierung der Attribute für den Text in der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt.  
  
```  
BOOL SetSelectionCharFormat(CHARFORMAT& cf);  
BOOL SetSelectionCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 In der ersten Version, ein Zeiger auf eine [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Struktur, die die neue Formatierung von Zeichen enthält Attribute, für die aktuelle Auswahl.  
  
 In der zweiten Version, ein Zeiger auf eine [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) -Struktur, die eine Rich Edit 2.0-Erweiterung ist auf die **CHARFORMAT** Struktur, mit der neuen zeichenformatierung-Attribute für den aktuellen Auswahl.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Nur die Attribute, die gemäß der **DwMask** Mitglied `cf` , die von dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter der [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) und **CHARFORMAT** und **CHARFORMAT2** Strukturen im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#31](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_31.cpp)]  
  
##  <a name="settargetdevice"></a>CRichEditCtrl::SetTargetDevice  
 Legt die Ziel-Gerät und die Standardlinienstärke für WYSIWYG (was Sie sehen, ist das Ergebnis) in dieser Formatierung `CRichEditCtrl` Objekt.  
  
```  
BOOL SetTargetDevice(
    HDC hDC,  
    long lLineWidth);

 
BOOL SetTargetDevice(
    CDC& dc,  
    long lLineWidth);
```  
  
### <a name="parameters"></a>Parameter  
 `hDC`  
 Handle für den Gerätekontext für das neue Zielgerät.  
  
 *lLineWidth*  
 Die Linienstärke für die Formatierung verwenden.  
  
 `dc`  
 [CDC](../../mfc/reference/cdc-class.md) für das neue Zielgerät.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion erfolgreich ist, wird das rich-Edit-Steuerelement besitzt das Gerät Kontext, der als Parameter übergeben. In diesem Fall sollte die aufrufende Funktion den Gerätekontext nicht zerstört.  
  
 Weitere Informationen finden Sie unter [EM_SETTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/bb774282) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#32](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_32.cpp)]  
  
##  <a name="settextmode"></a>CRichEditCtrl::SetTextMode  
 Legt den Text im Modus "oder" Rückgängig "und" Wiederholen für ein rich-Edit-Steuerelement fest.  
  
```  
BOOL SetTextMode(UINT fMode);
```  
  
### <a name="parameters"></a>Parameter  
 *fMode*  
 Gibt die neuen Einstellungen für das Steuerelement Text-Modus und Rückgängigmachen Ebene Parameter an. Eine Liste der möglichen Werte finden Sie in der Mode-Parameter für [EM_SETTEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774286) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL Wenn erfolgreich, andernfalls ungleich NULL.  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Modi für Text, finden Sie unter **EM_SETTEXTMODE** im Windows SDK.  
  
 Diese Memberfunktion schlägt fehl, wenn das Steuerelement den Text enthält. Um sicherzustellen, dass das Steuerelement leer ist, senden Sie eine [WM_SETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632644) Nachricht mit einer leeren Zeichenfolge.  
  
##  <a name="setundolimit"></a>CRichEditCtrl::SetUndoLimit  
 Legt die maximale Anzahl von Aktionen, die in der Rückgängig-Warteschlange gespeichert werden können.  
  
```  
UINT SetUndoLimit(UINT nLimit);
```  
  
### <a name="parameters"></a>Parameter  
 *nLimit*  
 Gibt die maximale Anzahl von Aktionen, die in der Rückgängig-Warteschlange gespeichert werden können. Auf NULL setzen, deaktivieren Sie rückgängig gemacht werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die neue maximale Anzahl von Rückgängig-Aktionen für das Rich edit-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig ist die maximale Anzahl von Aktionen in der Warteschlange zum Rückgängigmachen 100. Wenn Sie diese Zahl erhöhen, muss genügend Speicherplatz für die neue Anzahl aufweist vorhanden sein. Legen Sie den Grenzwert für eine bessere Leistung auf den kleinstmöglichen Wert.  
  
##  <a name="setwordcharformat"></a>CRichEditCtrl::SetWordCharFormat  
 Legt die Formatierung der Attribute für das aktuell ausgewählte Wort in diesem `CRichEditCtrl` Objekt.  
  
```  
BOOL SetWordCharFormat(CHARFORMAT& cf);  
BOOL SetWordCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 In der ersten Version, ein Zeiger auf eine [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Struktur, die die neue Formatierung von Zeichen enthält Attribute, für das aktuell ausgewählte Wort.  
  
 In der zweiten Version, ein Zeiger auf eine [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) -Struktur, die eine Rich Edit 2.0-Erweiterung ist auf die **CHARFORMAT** Struktur, die die neue Formatierung von Zeichen enthält Attribute, für die derzeit markierten Worts.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Nur die Attribute, die gemäß der **DwMask** Mitglied `cf` , die von dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter der [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) Nachricht und die **CHARFORMAT** und **CHARFORMAT2** Strukturen im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#33](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_33.cpp)]  
  
##  <a name="setwordwrapmode"></a>CRichEditCtrl::SetWordWrapMode  
 Legt der Zeilenumbruch und wörtertrennung Optionen für das Rich edit-Steuerelement.  
  
```  
UINT SetWordWrapMode(UINT uFlags) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `uFlags`  
 Die Optionen für den Zeilenumbruch und die wörtertrennung festgelegt. Eine Liste der möglichen Optionen, finden Sie unter [EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Wortumbruch und wörtertrennung Optionen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Meldung ist nur in einer asiatischen Version des Betriebssystems verfügbar.  
  
##  <a name="stopgrouptyping"></a>CRichEditCtrl::StopGroupTyping  
 Beendet das Steuerelement Sammeln von zusätzlichen Aktionen in der aktuellen Rückgängig-Aktion eingeben.  
  
```  
void StopGroupTyping();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement speichert den nächsten Vorgang eingeben, ggf. in eine neue Aktion in der Warteschlange rückgängig.  
  
 Weitere Informationen finden Sie unter [EM_STOPGROUPTYPING](http://msdn.microsoft.com/library/windows/desktop/bb774300) im Windows SDK.  
  
##  <a name="streamin"></a>CRichEditCtrl::StreamIn  
 Ersetzt Text in dieser `CRichEditCtrl` Objekt mit Text aus den angegebenen Eingabedatenstrom.  
  
```  
long StreamIn(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>Parameter  
 `nFormat`  
 Flags, die die Eingabedaten Formate angeben. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 `es`  
 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) Struktur, die den Eingabedatenstrom angibt. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl von Zeichen aus dem Eingabestream zu lesen.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert des `nFormat` muss eines der folgenden sein:  
  
- `SF_TEXT`Gibt nur Lesen von Text an.  
  
- `SF_RTF`Gibt an, Lesen von Text und Formatierung.  
  
 Beide Werte können kombiniert werden, mit `SFF_SELECTION`. Wenn `SFF_SELECTION` angegeben wird, `StreamIn` ersetzt die aktuelle Markierung mit dem Inhalt des Eingabedatenstroms. Wenn sie nicht angegeben ist, `StreamIn` ersetzt den gesamten Inhalt dieses `CRichEditCtrl` Objekt.  
  
 In der **EDITSTREAM** Parameter `es`, geben Sie eine Rückruffunktion, die einen Puffer mit Text aufgefüllt. Diese Rückruffunktion wird wiederholt aufgerufen, bis der Eingabestreams erreicht ist.  
  
 Weitere Informationen finden Sie unter [EM_STREAMIN](http://msdn.microsoft.com/library/windows/desktop/bb774302) Nachricht und [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) Struktur im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#34](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_34.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl#35](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_35.cpp)]  
  
##  <a name="streamout"></a>CRichEditCtrl::StreamOut  
 Schreibt den Inhalt dieses `CRichEditCtrl` Objekt in den angegebenen Ausgabestream.  
  
```  
long StreamOut(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>Parameter  
 `nFormat`  
 Flags, die die Ausgabe-Datenformate angeben. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 `es`  
 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) Struktur, die den Ausgabestream angibt. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl der Zeichen, die in den Ausgabestream geschrieben.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert des `nFormat` muss eines der folgenden sein:  
  
- `SF_TEXT`Gibt nur das Schreiben von Text an.  
  
- `SF_RTF`Gibt an, das Schreiben von Text und Formatierung.  
  
- `SF_RTFNOOBJS`Gibt das Schreiben von Text und Formatierungen, OLE-Elemente werden durch Leerzeichen ersetzt.  
  
- `SF_TEXTIZED`Gibt an, das Schreiben von Text und Formatierung mit Textdarstellungen von OLE-Elementen.  
  
 Diese Werte können kombiniert werden, mit `SFF_SELECTION`. Wenn `SFF_SELECTION` angegeben ist, `StreamOut` die aktuelle Auswahl in den Ausgabedatenstrom schreibt. Wenn sie nicht angegeben ist, `StreamOut` schreibt den gesamten Inhalt dieses `CRichEditCtrl` Objekt.  
  
 In der **EDITSTREAM** Parameter `es`, geben Sie eine Rückruffunktion, die einen Puffer mit Text aufgefüllt. Diese Rückruffunktion wird wiederholt aufgerufen, bis der Ausgabestream erschöpft ist.  
  
 Weitere Informationen finden Sie unter [EM_STREAMOUT](http://msdn.microsoft.com/library/windows/desktop/bb774304) Nachricht und [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) Struktur im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl#36](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_36.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl#37](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_37.cpp)]  
  
##  <a name="undo"></a>CRichEditCtrl::Undo  
 Macht den letzten Vorgang im rich-Edit-Steuerelement.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Rückgängig-Vorgang erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Rückgängig-Vorgang kann auch rückgängig gemacht werden. Sie können z. B. Wiederherstellen gelöschten Text mit dem ersten Aufruf **Rückgängig**. Solange keine Beteiligte Bearbeitungsvorgang vorhanden ist, können, entfernen Sie den Text erneut mit einem zweiten Aufruf von **Rückgängig**.  
  
 Weitere Informationen finden Sie unter [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CanUndo](#canundo).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)
