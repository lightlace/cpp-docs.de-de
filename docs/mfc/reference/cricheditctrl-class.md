---
title: CRichEditCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class, common controls
- CRichEditCtrl class
- formatted text [C++]
ms.assetid: 2be52788-822c-4c27-aafd-2471231e74eb
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 77b8dfb6011831f4e4300096a127f70b26bcc603
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditctrl-class"></a>CRichEditCtrl-Klasse
Stellt die Funktionalität des Rich-Edit-Steuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRichEditCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditCtrl::CRichEditCtrl](#cricheditctrl)|Erstellt ein `CRichEditCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRichEditCtrl::CanPaste](#canpaste)|Bestimmt, ob der Inhalt der Zwischenablage in dieser rich-Edit-Steuerelement eingefügt werden können.|  
|[CRichEditCtrl::CanRedo](#canredo)|Bestimmt, ob die Aktionen in der Wiederholungswarteschlange des Steuerelements.|  
|[CRichEditCtrl::CanUndo](#canundo)|Bestimmt, ob ein Bearbeitungsvorgang rückgängig gemacht werden kann.|  
|[CRichEditCtrl::CharFromPos](#charfrompos)|Ruft Informationen über die Zeichen, die an einem bestimmten Punkt im Clientbereich ein Edit-Steuerelement am nächsten liegt.|  
|[CRichEditCtrl::Clear](#clear)|Löscht die aktuelle Auswahl.|  
|[CRichEditCtrl::Copy](#copy)|Kopiert die aktuelle Auswahl in die Zwischenablage.|  
|[CRichEditCtrl::Create](#create)|Erstellt das rich-Edit-Steuerelement von Windows und ordnet sie dies `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::CreateEx](#createex)|Erstellt das Windows-rich-Edit-Steuerelement mit dem angegebenen erweiterten Fensterstile und ordnet sie dies `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::Cut](#cut)|Schneidet die aktuelle Auswahl in die Zwischenablage.|  
|[CRichEditCtrl::DisplayBand](#displayband)|Zeigt einen Teil des Inhalts des `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::EmptyUndoBuffer](#emptyundobuffer)|Zurücksetzen von Kennwörtern (löscht) das Flag "Rückgängig" dieses `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::FindText](#findtext)|Sucht nach Text in dieser `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::FindWordBreak](#findwordbreak)|Findet die nächste Wort Pause vor oder nach der angegebenen Zeichenposition, oder ruft Informationen über das Zeichen an der Position ab.|  
|[CRichEditCtrl::FormatRange](#formatrange)|Formatiert einen Textbereich für das Zielgerät für die Ausgabe.|  
|[CRichEditCtrl::GetCharPos](#getcharpos)|Bestimmt die Position eines bestimmten Zeichens in dieser `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetDefaultCharFormat](#getdefaultcharformat)|Ruft das aktuelle Standardzeichen Formatierungsattribute in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetEventMask](#geteventmask)|Ruft die Ereignismaske für dieses `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetFirstVisibleLine](#getfirstvisibleline)|Bestimmt die oberste sichtbare Zeile in dieser `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetIRichEditOle](#getiricheditole)|Ruft einen Zeiger auf die `IRichEditOle` -Schnittstelle für diese Rich--Steuerelement Edit.|  
|[CRichEditCtrl::GetLimitText](#getlimittext)|Ruft den Grenzwert für die Größe des Texts in die der Benutzer eingeben kann `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetLine](#getline)|Ruft eine Textzeile aus diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetLineCount](#getlinecount)|Ruft die Anzahl der Zeilen in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetModify](#getmodify)|Bestimmt, ob der Inhalt dieses `CRichEditCtrl` Objekt seit der letzten Speicherung geändert haben.|  
|[CRichEditCtrl::GetOptions](#getoptions)|Ruft die rich-Edit-Steuerelement-Optionen ab.|  
|[CRichEditCtrl::GetParaFormat](#getparaformat)|Ruft die Formatierungsattribute in der aktuellen Auswahl in diesem Absatz `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetPunctuation](#getpunctuation)|Ruft den aktuellen Interpunktionszeichen für das rich-Edit-Steuerelement ab. Diese Meldung ist nur in asiatischen Sprachversionen des Betriebssystems verfügbar.|  
|[CRichEditCtrl::GetRect](#getrect)|Ruft die Formatierung Rechteck für dieses `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetRedoName](#getredoname)|Ruft den Typ der nächsten Aktion ab, wenn alle in der Warteschlange nicht wiederholen.|  
|[CRichEditCtrl::GetSel](#getsel)|Ruft die Anfangs- und Endposition der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetSelectionCharFormat](#getselectioncharformat)|Ruft das Zeichen, das Formatierungsattribute in der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetSelectionType](#getselectiontype)|Ruft den Typ des Inhalts in der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::GetSelText](#getseltext)|Ruft den Text der aktuellen Auswahl in dieser `CRichEditCtrl` Objekt|  
|[CRichEditCtrl::GetTextLength](#gettextlength)|Ruft die Länge des Texts in Anzahl von Zeichen in dieser `CRichEditCtrl` Objekt. Umfasst nicht das abschließende Nullzeichen.|  
|[CRichEditCtrl::GetTextLengthEx](#gettextlengthex)|Ruft die Anzahl der Zeichen oder Bytes in der rich-Edit-Ansicht ab. Akzeptiert eine Liste mit Flags an, dass die Methode zur Bestimmung der Länge des Texts in einem rich-Edit-Steuerelement|  
|[CRichEditCtrl::GetTextMode](#gettextmode)|Ruft den aktuellen Text-Modus und Rückgängigmachen Ebene eines rich-Edit-Steuerelements ab.|  
|[CRichEditCtrl::GetTextRange](#gettextrange)|Ruft den angegebenen Textbereich ab.|  
|[CRichEditCtrl::GetUndoName](#getundoname)|Ruft den Typ der nächsten Rückgängigaktion ab, sofern vorhanden.|  
|[CRichEditCtrl::GetWordWrapMode](#getwordwrapmode)|Ruft die aktuelle Wortumbruch und Word wichtige Optionen für das rich-Edit-Steuerelement ab. Diese Meldung ist nur in asiatischen Sprachversionen des Betriebssystems verfügbar.|  
|[CRichEditCtrl::HideSelection](#hideselection)|Anzeigen oder ausblenden die aktuelle Auswahl.|  
|[CRichEditCtrl::LimitText](#limittext)|Schränkt die Größe des Texts in der Benutzer eingeben kann die `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::LineFromChar](#linefromchar)|Bestimmt, welche Zeile das angegebene Zeichen enthält.|  
|[CRichEditCtrl::LineIndex](#lineindex)|Ruft den Zeichenindex einer bestimmten Zeile in dieser `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::LineLength](#linelength)|Ruft die Länge einer bestimmten Zeile in dieser `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::LineScroll](#linescroll)|Der Text in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::Paste](#paste)|Fügt den Inhalt der Zwischenablage in dieser rich-Edit-Steuerelement.|  
|[CRichEditCtrl::PasteSpecial](#pastespecial)|Fügt den Inhalt der Zwischenablage in dieser rich-Edit-Steuerelement in dem angegebenen Format.|  
|[CRichEditCtrl::PosFromChar](#posfromchar)|Ruft den Bereich Clientkoordinaten eines angegebenen Zeichens in einem Bearbeitungssteuerelement ab.|  
|[CRichEditCtrl::Redo](#redo)|Wiederholen die nächste Aktion in der Wiederholungswarteschlange des Steuerelements.|  
|[CRichEditCtrl::ReplaceSel](#replacesel)|Ersetzt die aktuelle Auswahl in diesem `CRichEditCtrl` -Objekt mit dem angegebenen Text.|  
|[CRichEditCtrl::RequestResize](#requestresize)|Erzwingt, dass diese `CRichEditCtrl` Objekt zum Senden von Benachrichtigungen für Anforderung zum Ändern der Größe.|  
|[CRichEditCtrl::SetAutoURLDetect](#setautourldetect)|Gibt an, ob die automatische URL-Erkennung in einem rich-Edit-Steuerelement aktiv ist.|  
|[CRichEditCtrl::SetBackgroundColor](#setbackgroundcolor)|Legt die Hintergrundfarbe fest, in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetDefaultCharFormat](#setdefaultcharformat)|Legt die aktuelle Standardeinstellung Formatierungsattribute in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetEventMask](#seteventmask)|Legt die Ereignismaske für diesen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetModify](#setmodify)|Aktiviert oder deaktiviert das Flag Änderung für diesen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetOLECallback](#setolecallback)|Legt die `IRichEditOleCallback` COM-Objekt für dieses rich-Edit-Steuerelement.|  
|[CRichEditCtrl::SetOptions](#setoptions)|Legt die Optionen für diesen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetParaFormat](#setparaformat)|Legt die Formatierungsattribute in der aktuellen Auswahl in diesem Absatz `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetPunctuation](#setpunctuation)|Legt die Interpunktion für ein rich-Edit-Steuerelement fest. Diese Meldung ist nur in asiatischen Sprachversionen des Betriebssystems verfügbar.|  
|[CRichEditCtrl::SetReadOnly](#setreadonly)|Legt die Option schreibgeschützt für diesen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetRect](#setrect)|Legt die Formatierung Rechteck für dieses `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetSel](#setsel)|Legt die Auswahl in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetSelectionCharFormat](#setselectioncharformat)|Legt die Formatierung der Attribute in der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetTargetDevice](#settargetdevice)|Legt das Zielgerät für die Ausgabe für diesen `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetTextMode](#settextmode)|Legt den Text-Modus oder Rückgängigmachen eines rich-Edit-Steuerelements fest. Die Nachricht schlägt fehl, wenn das Steuerelement Text enthält.|  
|[CRichEditCtrl::SetUndoLimit](#setundolimit)|Legt die maximale Anzahl von Aktionen, die in der Rückgängig-Warteschlange gespeichert werden können.|  
|[CRichEditCtrl::SetWordCharFormat](#setwordcharformat)|Legt die Formatierung der Attribute im aktuellen Wort in diesem `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::SetWordWrapMode](#setwordwrapmode)|Legt die Zeilen- und Trennen von Wörtern Optionen für das Rich edit-Steuerelement. Diese Meldung ist nur in asiatischen Sprachversionen des Betriebssystems verfügbar.|  
|[CRichEditCtrl::StopGroupTyping](#stopgrouptyping)|Beendet das Steuerelement Sammeln von zusätzlichen Aktionen in die aktuelle Rückgängig-Aktion eingeben. Das Steuerelement speichert die nächste Aktion eingeben, ggf. in eine neue Aktion in der Rückgängig-Warteschlange.|  
|[CRichEditCtrl::StreamIn](#streamin)|Fügt Text aus einem Eingabestream dies `CRichEditCtrl` Objekt.|  
|[CRichEditCtrl::StreamOut](#streamout)|Speichert Text aus diesem `CRichEditCtrl` Objekt in einen Ausgabestream.|  
|[CRichEditCtrl::Undo](#undo)|Kehrt die letzte Bearbeitung des.|  
  
## <a name="remarks"></a>Hinweise  
 Ein "rich-Edit-Steuerelement" ist ein Fenster, in dem der Benutzer kann Text eingeben und bearbeiten. Der Text zugewiesen werden kann, Zeichen- und absatzformatierung und eingebettete OLE-Objekte enthalten kann. Rich-Edit-Steuerelemente bieten eine Programmierschnittstelle zum Formatieren von Text. Allerdings muss eine Anwendung Komponenten der Benutzeroberfläche erforderlich Formatierungsvorgängen der Benutzer zur Verfügung stellen implementieren.  
  
 Diese Windows-Standardsteuerelement (und somit die `CRichEditCtrl` Klasse) ist nur für Programme, die unter Windows 95/98 und Windows NT, Version 3.51 und höher. Die `CRichEditCtrl` Klasse unterstützt die Versionen 2.0 und 3.0 von den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] Rich-edit-Steuerelement.  
  
> [!CAUTION]
>  Bei Verwendung von einem rich Edit-Steuerelement in einem Dialogfeld (unabhängig davon, ob Ihre Anwendung SDI, MDI oder Dialogfeldern basiert), müssen Sie aufrufen, [AfxInitRichEdit](application-information-and-management.md#afxinitrichedit) nach bevor das Dialogfeld angezeigt wird. Eine geeignete Stelle für diesen Funktionsaufruf wird in Ihrem Programms `InitInstance` Member-Funktion. Sie müssen nicht jedes Mal aufrufen Sie das Dialogfeld nur beim ersten anzeigen. Sie müssen keinen Aufrufen `AfxInitRichEdit` , wenn Sie mit arbeiten `CRichEditView`.  
  
 Weitere Informationen zur Verwendung von `CRichEditCtrl`, finden Sie unter:  
  
- [Steuerelemente](../../mfc/controls-mfc.md)  
  
- [Verwenden von CRichEditCtrl](../../mfc/using-cricheditctrl.md)  
  
-   Knowledge Base-Artikel Q259949: INFO: SetCaretPos() ist keine geeignete CEdit oder CRichEditCtrl-Steuerelemente  
  
 Ein Beispiel für ein rich-Edit-Steuerelement in einer MFC-Anwendung verwenden, finden Sie unter der [WORDPAD](../../visual-cpp-samples.md) -Beispiel.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CRichEditCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="canpaste"></a>CRichEditCtrl::CanPaste  
 Bestimmt, ob das rich-Edit-Steuerelement das angegebene Format der Zwischenablage einfügen kann.  
  
```  
BOOL CanPaste(UINT nFormat = 0) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nFormat`  
 Zwischenablage-Datenformats auf Abfrage. Dieser Parameter kann eine der vordefinierten Formate der Zwischenablage oder den Rückgabewert von [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049).  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Format der Zwischenablage eingefügt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nFormat` ist 0, `CanPaste` versucht jedes Format der Zwischenablage.  
  
 Weitere Informationen finden Sie unter [EM_CANPASTE](http://msdn.microsoft.com/library/windows/desktop/bb787993) Nachricht und [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) -Funktion in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#1;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_1.cpp)]  
  
##  <a name="canredo"></a>CRichEditCtrl::CanRedo  
 Bestimmt, ob die Wiederholungswarteschlange Aktionen enthält.  
  
```  
BOOL CanRedo() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, enthält die Wiederholungswarteschlange Aktionen, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Um den Namen des Vorgangs in der Wiederholungswarteschlange zu ermitteln, rufen Sie [CRichEditCtrl::GetRedoName](#getredoname). Rufen Sie zum Wiederherstellen des letzten Rückgängig-Vorgangs [wiederholen](#redo).  
  
 Weitere Informationen finden Sie unter [EM_CANREDO](http://msdn.microsoft.com/library/windows/desktop/bb787995) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="canundo"></a>CRichEditCtrl::CanUndo  
 Bestimmt, ob die letzte Bearbeitung des rückgängig gemacht werden kann.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die letzte Bearbeitung durch einen Aufruf von rückgängig gemacht werden kann die [Rückgängig](#undo) Memberfunktion; 0, wenn es nicht rückgängig gemacht werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#2;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_2.cpp)]  
  
##  <a name="charfrompos"></a>CRichEditCtrl::CharFromPos  
 Ruft Informationen über den Zeichensatz an dem vom Parameter angegebenen `pt`.  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt, das die Koordinaten der angegebenen Punkt enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Zeichenindex des Zeichens am nächsten an der angegebenen Position. Wenn der angegebene Punkt hinter dem letzten Zeichen in das Steuerelement ist, gibt der Rückgabewert des letzten Zeichens in das Steuerelement an.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion funktioniert mit einem rich-Edit-Steuerelement. Rufen Sie zum Abrufen der Informationen für ein Bearbeitungssteuerelement [CEdit::CharFromPos](../../mfc/reference/cedit-class.md#charfrompos).  
  
 Weitere Informationen finden Sie unter [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="clear"></a>CRichEditCtrl::Clear  
 Löscht (deaktiviert) die aktuelle Auswahl (sofern vorhanden) in das Rich-edit-Steuerelement.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Löschen von ausgeführten **löschen** rückgängig gemacht werden können, durch Aufrufen der [rückgängig machen](#undo) Member-Funktion.  
  
 Rufen Sie zum Löschen der aktuellen Auswahl aus, und fügen Sie den gelöschten Inhalt in die Zwischenablage, die [Ausschneiden](#cut) Member-Funktion.  
  
 Weitere Informationen finden Sie unter [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&3;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_3.cpp)]  
  
##  <a name="copy"></a>CRichEditCtrl::Copy  
 Kopiert die aktuelle Auswahl (sofern vorhanden) in das rich-Edit-Steuerelement in die Zwischenablage.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&4;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_4.cpp)]  
  
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
 Gibt das Bearbeitungssteuerelement-Stil. Wenden Sie eine Kombination von Window-Stile, die gemäß der **Hinweise** unten, und [Steuerelementtypen bearbeiten](http://msdn.microsoft.com/library/windows/desktop/bb775464)in beschriebenen der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Gibt des Bearbeitungssteuerelements Größe und Position. Kann ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder [RECT](../../mfc/reference/rect-structure1.md) Struktur.  
  
 `pParentWnd`  
 Gibt an, das Steuerelement zum Bearbeiten des übergeordneten Fensters (häufig eine [CDialog](../../mfc/reference/cdialog-class.md)). Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Edit-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CRichEditCtrl` Objekt in zwei Schritten. Zunächst rufen die [CRichEditCtrl](#cricheditctrl) -Konstruktor rufen Sie dann **erstellen**, die das Windows-Edit-Steuerelement erstellt, und fügt es der `CRichEditCtrl` Objekt.  
  
 Wenn Sie ein rich-Edit-Steuerelement mit dieser Funktion erstellen, müssen zunächst die erforderlichen common Controls-Bibliothek laden. Um die Bibliothek zu laden, rufen Sie die globale Funktion [AfxInitRichEdit](application-information-and-management.md#afxinitrichedit), die wiederum die Bibliothek für Standardsteuerelemente initialisiert. Sie müssen Aufrufen `AfxInitRichEdit` nur einmal innerhalb des Prozesses.  
  
 Wenn **erstellen** ausgeführt wird, sendet Windows die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), und [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Nachrichten an das Steuerelement zum Bearbeiten.  
  
 Diese Nachrichten werden standardmäßig verarbeitet die [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), und [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standardbehandlung für die Nachricht zu erweitern, leiten Sie eine Klasse von `CRichEditCtrl`, Hinzufügen einer Nachricht Zuordnung zu der neuen Klasse und überschreiben Sie die oben genannten Message-Handler-Memberfunktionen. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für die neue Klasse.  
  
 Übernehmen Sie das folgende [Fensterstile](../../mfc/reference/window-styles.md) Kombinationsfeld.  
  
- **WS_CHILD** immer.  
  
- **WS_VISIBLE** in der Regel.  
  
- **WS_DISABLED** selten.  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen.  
  
- **WS_TABSTOP** Edit-Steuerelement in der Tabulatorreihenfolge eingeschlossen.  
  
 Weitere Informationen zu Fensterstile, finden Sie unter [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&5;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_5.cpp)]  
  
##  <a name="createex"></a>CRichEditCtrl::CreateEx  
 Erstellt ein Steuerelement (ein untergeordnetes Fenster), und ordnet sie der `CRichEditCtrl` Objekt.  
  
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
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Übersicht über die erweiterten Fensterstile finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Gibt das Bearbeitungssteuerelement-Stil. Wenden Sie eine Kombination von Window-Stile, die gemäß der **Hinweise** Abschnitt [erstellen](#create) und [Steuerelementtypen bearbeiten](http://msdn.microsoft.com/library/windows/desktop/bb775464)in beschriebenen der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 `nID`  
 Der ID des Steuerelements untergeordnete Fenster  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von **erstellen** erweiterten Fensterstile, angegeben durch den Wert der Windows-erweiterten Stil anwenden **WS_EX_**.  
  
##  <a name="cricheditctrl"></a>CRichEditCtrl::CRichEditCtrl  
 Erstellt ein `CRichEditCtrl`-Objekt.  
  
```  
CRichEditCtrl();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [erstellen](#create) zum Erstellen von Windows Rich-edit-Steuerelement.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&6;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_6.cpp)]  
  
##  <a name="cut"></a>CRichEditCtrl::Cut  
 Löschen (Teilstücke) die aktuelle Auswahl (sofern vorhanden) in das Rich-edit-Steuerelement und den gelöschten Text in die Zwischenablage kopiert.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Löschen von ausgeführten **Ausschneiden** rückgängig gemacht werden können, durch Aufrufen der [rückgängig machen](#undo) Member-Funktion.  
  
 Aufrufen, um die aktuelle Auswahl löschen, ohne den gelöschten Text in die Zwischenablage, die [löschen](#clear) Member-Funktion.  
  
 Weitere Informationen finden Sie unter [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#7;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_7.cpp)]  
  
##  <a name="displayband"></a>CRichEditCtrl::DisplayBand  
 Zeigt einen Teil des Inhalts des rich-Edit-Steuerelements (Text und OLE-Elemente), wie bereits formatiert [FormatRange](#formatrange).  
  
```  
BOOL DisplayBand(LPRECT pDisplayRect);
```  
  
### <a name="parameters"></a>Parameter  
 `pDisplayRect`  
 Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das den Bereich des Geräts zur Anzeige des Textes angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Anzeige von formatierten Text, andernfalls 0 erfolgreich ausgeführt wird.  
  
### <a name="remarks"></a>Hinweise  
 Der Text und die OLE-Elemente werden in den Bereich, der durch den Zeiger angegebenen abgeschnitten `pDisplayRect`.  
  
 Weitere Informationen finden Sie unter [EM_DISPLAYBAND](http://msdn.microsoft.com/library/windows/desktop/bb787997) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditCtrl::FormatRange](#formatrange).  
  
##  <a name="emptyundobuffer"></a>CRichEditCtrl::EmptyUndoBuffer  
 Das Flag "Rückgängig" dieses rich-Edit-Steuerelements (clear) wird zurückgesetzt.  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement werden kann nicht die letzte Bearbeitung des rückgängig gemacht. Die rückgängig-Flag wird festgelegt, wenn ein Vorgang innerhalb des rich-Edit-Steuerelements rückgängig gemacht werden kann.  
  
 Das Flag "Rückgängig" wird automatisch gelöscht, bei jedem Aufruf der [CWnd](../../mfc/reference/cwnd-class.md) Memberfunktion [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
 Weitere Informationen finden Sie unter [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#8;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_8.cpp)]  
  
##  <a name="findtext"></a>CRichEditCtrl::FindText  
 Sucht nach Text innerhalb des rich-Edit-Steuerelements.  
  
```  
long FindText(
    DWORD dwFlags,  
    FINDTEXTEX* pFindText) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Eine Liste der möglichen Werte finden Sie unter `wParam` in [EM_FINDTEXTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788011) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *pFindText*  
 Zeiger auf die [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) Struktur erhalten die Parameter für die Suche und Rückgabe des Bereichs, in dem die Übereinstimmung gefunden wurde.  
  
### <a name="return-value"></a>Rückgabewert  
 Nullbasierte Position des nächsten Übereinstimmung; – 1, wenn keine Übereinstimmungen vorhanden sind.  
  
### <a name="remarks"></a>Hinweise  
 Suche können Sie entweder nach oben oder unten Festlegen der richtigen Bereich-Parameter der [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur innerhalb der **FINDTEXTEX** Struktur.  
  
 Weitere Informationen finden Sie unter [EM_FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb788011) Nachricht und [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#9;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_9.cpp)]  
  
##  <a name="findwordbreak"></a>CRichEditCtrl::FindWordBreak  
 Sucht die nächste Wort Pause vor oder nach der angegebenen Position `nStart`.  
  
```  
DWORD FindWordBreak(
    UINT nCode,  
    DWORD nStart) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nCode`  
 Gibt die auszuführende Aktion an. Eine Liste der möglichen Werte finden Sie unter der Beschreibung für den Parameter `code` in **EM_FINDWORDBREAK** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nStart`  
 Die nullbasierte Zeichenposition, ab.  
  
### <a name="return-value"></a>Rückgabewert  
 Auf Grundlage des Parameters `nCode`. Weitere Informationen finden Sie unter [EM_FINDWORDBREAK](http://msdn.microsoft.com/library/windows/desktop/bb788018) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Sie können diese Memberfunktion verwenden, zum Abrufen von Informationen über ein Zeichen an einer bestimmten Position.  
  
##  <a name="formatrange"></a>CRichEditCtrl::FormatRange  
 Formatiert einen Textbereich in einem rich-Edit-Steuerelement für ein bestimmtes Gerät.  
  
```  
long FormatRange(
    FORMATRANGE* pfr,  
    BOOL bDisplay = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *PFR*  
 Zeiger auf die [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) Struktur enthält Informationen zu diesem Gerät. **NULL** gibt an, dass die zwischengespeicherten Informationen im rich-Edit-Steuerelement freigegeben werden kann.  
  
 *bDisplay*  
 Gibt an, ob der Text gerendert werden soll. Wenn **FALSE**, der Text wird nur gemessen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des letzten Zeichens, die in der Region plus&1; entspricht.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel folgt diesem Aufruf durch einen Aufruf von [DisplayBand](#displayband).  
  
 Weitere Informationen finden Sie unter [EM_FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb788020) Nachricht und [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#10;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_10.cpp)]  
  
##  <a name="getcharpos"></a>CRichEditCtrl::GetCharPos  
 Ruft die Position (obere linke Ecke) eines bestimmten Zeichens in dieser `CRichEditCtrl` Objekt.  
  
```  
CPoint GetCharPos(long lChar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lChar`  
 Nullbasierter Index des Zeichens.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position der oberen linken Ecke des angegebenen Zeichens `lChar`.  
  
### <a name="remarks"></a>Hinweise  
 Das Zeichen wird durch die Vergabe des nullbasierte Indexwerts angegeben. Wenn `lChar` ist größer als der Index des letzten Zeichens in dieser `CRichEditCtrl` -Objekt, gibt der Rückgabewert die Koordinaten der Position des Zeichens direkt nach dem letzten Zeichen in diesem `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getdefaultcharformat"></a>CRichEditCtrl::GetDefaultCharFormat  
 Ruft das Standardzeichen Formatierungsattribute dieses `CRichEditCtrl` Objekt.  
  
```  
DWORD GetDefaultCharFormat(CHARFORMAT& cf) const;  DWORD GetDefaultCharFormat(CHARFORMAT2& cf) const;  ```  
  
### Parameters  
 `cf`  
 In the first version, a pointer to a **CHARFORMAT** structure holding the default character formatting attributes.  
  
 In the second version, a pointer to a **CHARFORMAT2** structure, which is a Rich Edit 2.0 extension to the **CHARFORMAT** structure, holding the default character formatting attributes.  
  
### Return Value  
 The **dwMask** data member of `cf`. It specified the default character formatting attributes.  
  
### Remarks  
 For more information, see the **EM_GETCHARFORMAT** message and the **CHARFORMAT** and **CHARFORMAT2** structures in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [SetDefaultCharFormat](#setdefaultcharformat).  
  
##  <a name="geteventmask"></a>  CRichEditCtrl::GetEventMask  
 Gets the event mask for this `CRichEditCtrl` object.  
  
```  
lange GetEventMask() const;  
```  
  
### Return Value  
 The event mask for this `CRichEditCtrl` object.  
  
### Remarks  
 The event mask specifies which notification messages the `CRichEditCtrl` object sends to its parent window.  
  
 For more information, see [EM_GETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb788032) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [CRichEditCtrl::SetEventMask](#seteventmask).  
  
##  <a name="getfirstvisibleline"></a>  CRichEditCtrl::GetFirstVisibleLine  
 Determines the topmost visible line in this `CRichEditCtrl` object.  
  
```  
GetFirstVisibleLine() const Int.  
```  
  
### Return Value  
 Zero-based index of the uppermost visible line in this `CRichEditCtrl` object.  
  
### Remarks  
 For more information, see [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#11](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_11.cpp)]  
  
##  <a name="getiricheditole"></a>  CRichEditCtrl::GetIRichEditOle  
 Accesses the **IRichEditOle** interface for this `CRichEditCtrl` object.  
  
```  
IRichEditOle * const GetIRichEditOle();  
```  
  
### Return Value  
 Pointer to the [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) interface that can be used to access this `CRichEditCtrl` object's OLE functionality; **NULL** if the interface is not accessible.  
  
### Remarks  
 Use this interface to access this `CRichEditCtrl` object's OLE functionality.  
  
 For more information, see [EM_GETOLEINTERFACE](http://msdn.microsoft.com/library/windows/desktop/bb788041) message and [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) interface in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getlimittext"></a>  CRichEditCtrl::GetLimitText  
 Gets the text limit for this `CRichEditCtrl` object.  
  
```  
lange GetLimitText() const;  
```  
  
### Return Value  
 The current text limit, in bytes, for this `CRichEditCtrl` object.  
  
### Remarks  
 The text limit is the maximum amount of text, in bytes, the rich edit control can accept.  
  
 For more information, see [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#12](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_12.cpp)]  
  
##  <a name="getline"></a>  CRichEditCtrl::GetLine  
 Retrieves a line of text from this `CRichEditCtrl` object.  
  
```  
Int GetLine (Int nIndex,  
    LPTSTR LpszBuffer) const;  
  
Int GetLine (Int nIndex,  
    LPTSTR-lpszBuffer  
    Int nMaxLength) const;  
```  
  
### Parameters  
 `nIndex`  
 Zero-based index of the line to retrieve.  
  
 `lpszBuffer`  
 Points to the buffer to receive the text. The first word of the buffer must specify the maximum number of bytes that can be copied into the buffer.  
  
 `nMaxLength`  
 Maximum number of characters that can be copied into `lpszBuffer`. The second form of `GetLine` places this value into the first word of the buffer specified by `lpszBuffer`.  
  
### Return Value  
 The number of characters copied into `lpszBuffer`.  
  
### Remarks  
 The copied line does not contain a terminating null character.  
  
> [!NOTE]
>  Because the first word of the buffer stores the number of characters to be copied, make sure that your buffer is at least 4 bytes long.  
  
 For more information, see [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>  CRichEditCtrl::GetLineCount  
 Retrieves the number of lines in the `CRichEditCtrl` object.  
  
```  
GetLineCount() const Int.  
```  
  
### Return Value  
 The number of lines in this `CRichEditCtrl` object.  
  
### Remarks  
 For more information, see [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#13](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_13.cpp)]  
  
##  <a name="getmodify"></a>  CRichEditCtrl::GetModify  
 Determines if the contents of this `CRichEditCtrl` object have been modified.  
  
```  
BOOL GetModify() const;  
```  
  
### Return Value  
 Nonzero if the text in this `CRichEditCtrl` object has been modified; otherwise 0.  
  
### Remarks  
 Windows maintains an internal flag indicating whether the contents of the rich edit control have been changed. This flag is cleared when the edit control is first created and can also be cleared by calling the [SetModify](#setmodify) member function.  
  
 For more information, see [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#14](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_14.cpp)]  
  
##  <a name="getoptions"></a>  CRichEditCtrl::GetOptions  
 Retrieves the options currently set for the rich edit control.  
  
```  
UINT GetOptions() const;  
```  
  
### Return Value  
 A combination of the current option flag values. For a list of these values, see the *fOptions* parameter in the [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getparaformat"></a>  CRichEditCtrl::GetParaFormat  
 Gets the paragraph formatting attributes of the current selection.  
  
```  
DWORD GetParaFormat(PARAFORMAT& pf) const;  DWORD GetParaFormat(PARAFORMAT2& pf) const;  ```  
  
### <a name="parameters"></a>Parameter  
 `pf`  
 In der ersten Version, die einen Zeiger auf eine [ABSATZFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) Struktur, um die Attribute der aktuellen Auswahl formatieren von Absätzen zu halten.  
  
 In der zweiten Version, die einen Zeiger auf eine [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) -Struktur, die eine umfassende bearbeiten 2.0-Erweiterung ist, die **ABSATZFORMAT** Struktur, das Standardzeichen Formatierungsattribute.  
  
### <a name="return-value"></a>Rückgabewert  
 Die **DwMask** -Datenmember des `pf`. Es gibt das Absatzformat Attribute, die innerhalb der aktuellen Auswahl konsistent sind.  
  
### <a name="remarks"></a>Hinweise  
 Wenn mehrere Absätze ausgewählt ist, `pf` empfängt die Attribute des ausgewählten Absatz. Der Rückgabewert gibt an, welche Attribute innerhalb der Auswahl konsistent sind.  
  
 Weitere Informationen finden Sie unter der [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) Nachricht und die **ABSATZFORMAT** und **PARAFORMAT2** Strukturen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditCtrl::SetParaFormat](#setparaformat).  
  
##  <a name="getpunctuation"></a>CRichEditCtrl::GetPunctuation  
 Ruft den aktuellen Interpunktionszeichen in einem rich-Edit-Steuerelement ab.  
  
```  
BOOL GetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `fType`  
 Satzzeichen Typ-Flag, wie in beschrieben die `fType` Parameter der [EM_GETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774184) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpPunc`  
 Ein Zeiger auf eine [SATZZEICHEN](http://msdn.microsoft.com/library/windows/desktop/bb787944) Struktur, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
 [CRect](../../atl-mfc-shared/reference/crect-class.md) oder ein Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) Formatierung dieses Rechtecks empfangen `CRichEditCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Formatierung Rechteck ist das umschließende Rechteck für den Text. Dieser Wert ist unabhängig von der Größe der `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [LimitText](#limittext).  
  
##  <a name="getredoname"></a>CRichEditCtrl::GetRedoName  
 Ruft den Typ der nächste verfügbare Aktion in der Wiederholungswarteschlange ab, sofern vorhanden.  
  
```  
UNDONAMEID GetRedoName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall `GetRedoName` gibt die [UNDONAMEID](http://msdn.microsoft.com/library/windows/desktop/bb774365) Enumerationstyp, der die nächste Aktion in der Wiederholungswarteschlange des Steuerelements angibt. Wenn die Wiederholungswarteschlange leer ist oder einen unbekannten Typ, der Wiederholen-Aktion in der Warteschlange ist `GetRedoName` gibt 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Typen von Aktionen, die rückgängig gemacht oder wiederhergestellt werden können gehören eingeben, löschen, Drag & Drop, Ausschneiden und einfügen. Diese Informationen kann für Applikationen hilfreich sein, die eine erweiterte Benutzeroberfläche für rückgängig und wiederholen-Vorgänge, z. B. ein Dropdown-Listenfeld redoable Aktionen bereitstellen.  
  
##  <a name="getsel"></a>CRichEditCtrl::GetSel  
 Ruft die Grenzen der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt.  
  
```  
void GetSel(CHARRANGE& cr) const;  
  
void GetSel(
    long& nStartChar,  
    long& nEndChar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `cr`  
 Ein Verweis auf eine [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur, um die Grenzen der aktuellen Auswahl zu erhalten.  
  
 `nStartChar`  
 Nullbasierte Index des ersten Zeichens in der aktuellen Auswahl.  
  
 `nEndChar`  
 Nullbasierte Index des letzten Zeichens in der aktuellen Auswahl.  
  
### <a name="remarks"></a>Hinweise  
 Die zwei Arten von dieser Funktion bieten eine Möglichkeit, die Grenzen für die Auswahl abzurufen. Führen Sie die kurze Beschreibungen der folgenden Formate:  
  
- **Memberfunktion GetSel (** `cr` **)** dieses Formular verwendet die **CHARRANGE** Struktur mit den **CpMin** und **CpMax** die Grenzen zurückzugebenden Elemente.  
  
- **Memberfunktion GetSel (** `nStartChar` **,** `nEndChar` **)** dieses Formulars gibt die Grenzen in den Parametern `nStartChar` und `nEndChar`.  
  
 Die Auswahl enthält alles, was, wenn am Anfang ( **CpMin** oder `nStartChar`) 0 ist und das Ende ( **CpMax** oder `nEndChar`) – 1 beträgt.  
  
 Weitere Informationen finden Sie unter [EM_EXGETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788001) Nachricht und [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#15;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_15.cpp)]  
  
##  <a name="getselectioncharformat"></a>CRichEditCtrl::GetSelectionCharFormat  
 Ruft die Attribute der aktuellen Auswahl Formatierung.  
  
```  
DWORD GetSelectionCharFormat(CHARFORMAT& cf) const;  DWORD GetSelectionCharFormat(CHARFORMAT2& cf) const;  ```  
  
### Parameters  
 `cf`  
 In the first version, a pointer to a [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) structure to receive the character formatting attributes of the current selection.  
  
 In the second version, a pointer to a [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) structure, which is a Rich Edit 2.0 extension to the **CHARFORMAT** structure to receive the character formatting attributes of the current selection.  
  
### Return Value  
 The **dwMask** data member of `cf`. It specifies the character formatting attributes that are consistent throughout the current selection.  
  
### Remarks  
 The `cf` parameter receives the attributes of the first character in the current selection. The return value specifies which attributes are consistent throughout the selection.  
  
 For more information, see the [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) message and the **CHARFORMAT** and **CHARFORMAT2** structures in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [SetSelectionCharFormat](#setselectioncharformat).  
  
##  <a name="getselectiontype"></a>  CRichEditCtrl::GetSelectionType  
 Determines the selection type in this `CRichEditCtrl` object.  
  
```  
WORD GetSelectionType() const;  
```  
  
### Return Value  
 Flags indicating the contents of the current selection. A combination of the following flags:  
  
- `SEL_EMPTY` Indicates that there is no current selection.  
  
- `SEL_TEXT` Indicates that the current selection contains text.  
  
- `SEL_OBJECT` Indicates that the current selection contains at least one OLE item.  
  
- `SEL_MULTICHAR` Indicates that the current selection contains more than one character of text.  
  
- `SEL_MULTIOBJECT` Indicates that the current selection contains more than one OLE object.  
  
### Remarks  
 For more information, see [EM_SELECTIONTYPE](http://msdn.microsoft.com/library/windows/desktop/bb774223) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#16](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_16.cpp)]  
  
##  <a name="getseltext"></a>  CRichEditCtrl::GetSelText  
 Retrieves the text from the current selection in this `CRichEditCtrl` object.  
  
```  
lange GetSelText(LPSTR lpBuf) const;  CString-GetSelText() const;  ```  
  
### <a name="parameters"></a>Parameter  
 `lpBuf`  
 Zeiger auf den Puffer an den Text in der aktuellen Auswahl zu erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Hängt von der Form:  
  
- **Memberfunktion GetSelText (** `lpBuf` **)** die Anzahl der Zeichen, die in kopiert `lpBuf`, nicht einschließlich der null-Terminierung.  
  
- **Memberfunktion GetSelText ()** die Zeichenfolge, die die aktuelle Auswahl enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das erste Formular verwenden **Memberfunktion GetSelText (** `lpBuf` **)**, müssen Sie sicherstellen, dass der Puffer groß genug für den Text empfängt. Rufen Sie [Memberfunktion GetSel](#getsel) bestimmt die Anzahl der Zeichen in der aktuellen Auswahl.  
  
 Weitere Informationen finden Sie unter [EM_GETSELTEXT](http://msdn.microsoft.com/library/windows/desktop/bb774190) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CRichEditCtrl::GetSelectionType](#getselectiontype).  
  
##  <a name="gettextlength"></a>CRichEditCtrl::GetTextLength  
 Ruft die Länge des Texts in Anzahl von Zeichen in dieser `CRichEditCtrl` Objekts, ohne das abschließende Nullzeichen.  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge des Texts in diesem `CRichEditCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [WM_GETTEXTLENGTH](http://msdn.microsoft.com/library/windows/desktop/ms632628) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&17;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_17.cpp)]  
  
##  <a name="gettextlengthex"></a>CRichEditCtrl::GetTextLengthEx  
 Berechnet die Länge des Texts im rich-Edit-Steuerelement.  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Der Wert gibt die Methode zum Bestimmen der Länge verwendet werden. Dieser Member kann eine oder mehrere der Werte in Flags-Mitglied der [GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) beschrieben, die der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `uCodePage`  
 Die Codepage für die Übersetzung (CP_ACP für ANSI-Codepage, 1200 für Unicode).  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen oder Bytes in das Bearbeitungssteuerelement. Wenn nicht kompatible Flags, im festgelegt wurden `dwFlags`, diese Memberfunktion gibt `E_INVALIDARG`.  
  
### <a name="remarks"></a>Hinweise  
 `GetTextLengthEx`Stellt zusätzliche Methoden zum Bestimmen der Länge des Texts an. Die Funktionalität des Rich bearbeiten 2.0 unterstützt. Finden Sie unter [zu Rich-Edit-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb787873) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]Weitere Informationen.  
  
##  <a name="gettextmode"></a>CRichEditCtrl::GetTextMode  
 Ruft den aktuellen Text-Modus und Rückgängigmachen Ebene eines rich-Edit-Steuerelements ab.  
  
```  
UINT GetTextMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Satz von Bitflags aus der [TEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774364) Enumerationstyp, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Die Flags geben den aktuellen Textmodus und Rückgängig: Abgleichen des Steuerelements.  
  
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
 Die Position des index vor dem ersten Zeichen im Bereich.  
  
 `nLast`  
 Die Position unmittelbar hinter dem letzten Zeichen im Bereich.  
  
 `refString`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den Text angezeigt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeichen kopiert, ohne das abschließende Nullzeichen.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_GETTEXTRANGE](http://msdn.microsoft.com/library/windows/desktop/bb774199) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `GetTextRange`unterstützt die Funktionalität des Rich bearbeiten 2.0. Finden Sie unter [zu Rich-Edit-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb787873) in den [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]Weitere Informationen.  
  
##  <a name="getundoname"></a>CRichEditCtrl::GetUndoName  
 Ruft den Typ der die nächste verfügbare Aktion in der Rückgängig-Warteschlange ab, falls vorhanden.  
  
```  
UNDONAMEID GetUndoName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn eine Rückgängig-Aktion in das Steuerelement Rückgängig-Warteschlange ist `GetUndoName` gibt die [UNDONAMEID](http://msdn.microsoft.com/library/windows/desktop/bb774365) Enumerationstyp, der die nächste Aktion in der Warteschlange angibt. Wenn die Rückgängig-Warteschlange leer ist oder die Rückgängig-Aktion in der Warteschlange eines unbekannten Typs ist `GetUndoName` gibt 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die Typen von Aktionen, die rückgängig gemacht oder wiederhergestellt werden können gehören eingeben, löschen, Drag & Drop, Ausschneiden und einfügen. Diese Informationen können für Anwendungen nützlich sein, die eine erweiterte Benutzeroberfläche für rückgängig und wiederholen-Vorgänge, z. B. ein Dropdown-Listenfeld Aktionen bieten, die rückgängig gemacht werden kann.  
  
##  <a name="getwordwrapmode"></a>CRichEditCtrl::GetWordWrapMode  
 Ruft die aktuelle Wortumbruch und Word wichtige Optionen für das rich-Edit-Steuerelement ab.  
  
```  
UINT GetWordWrapMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Zeilenumbruch und die Optionen für den Wortumbruch. Diese Optionen werden beschrieben [EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
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
 Gibt an, ob die Auswahl angezeigt oder ausgeblendet werden soll **TRUE** die Auswahl ausblenden.  
  
 `bPerm`  
 Gibt an, ob diese Änderung der Sichtbarkeit für die Auswahl dauerhaft sein soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bPerm` ist **TRUE**, ändert die `ECO_NOHIDESEL` für diese Option `CRichEditCtrl` Objekt. Eine kurze Beschreibung dieser Option finden Sie unter [SetOptions](#setoptions). Sie können diese Funktion alle Optionen für das Festlegen `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter [EM_HIDESELECTION](http://msdn.microsoft.com/library/windows/desktop/bb774210) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&18;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_18.cpp)]  
  
##  <a name="limittext"></a>CRichEditCtrl::LimitText  
 Begrenzt die Länge des Texts, die der Benutzer in ein Bearbeitungssteuerelement eingeben können.  
  
```  
void LimitText(long nChars = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nChars`  
 Gibt die Länge (in Byte) des Textes, den der Benutzer eingeben kann. Wenn dieser Parameter 0 (Standardwert) ist, wird die Textlänge auf 64 KB festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Ändern der Grenze Text schränkt nur den Text, den der Benutzer eingeben kann. Wirkt sich nicht auf einen beliebigen Text bereits in der Edit-Steuerelement, und beeinträchtigt die Länge des Texts auf das Steuerelement zum Bearbeiten von kopiert die [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) -Memberfunktion `CWnd`. Wenn eine Anwendung verwendet die `SetWindowText` Funktion zum Platzieren von Text in ein Bearbeitungssteuerelement als im Aufruf angegeben ist `LimitText`, der Benutzer kann den Text im Steuerelement bearbeiten löschen. Der Text-Grenzwert wird verhindert, dass den Benutzer den vorhandenen Text durch neuen Text ersetzen jedoch, wenn die aktuelle Auswahl löschen, wird der Text unterhalb des Text-Limits liegen.  
  
> [!NOTE]
>  Für die Beschränkung der Text zählt jeden OLE-Element als ein einzelnes Zeichen.  
  
 Weitere Informationen finden Sie unter [EM_EXLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788003) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl Nr.&19;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_19.cpp)]  
  
##  <a name="linefromchar"></a>CRichEditCtrl::LineFromChar  
 Ruft die Zeilennummer der Zeile, die den angegebenen Zeichenindex enthält.  
  
```  
long LineFromChar(long nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Indexwert für das gewünschte Zeichen im Text des Edit-Steuerelements, oder -1. Wenn `nIndex` ist-1, gibt die aktuelle Zeile, d. h. die Zeile, die die Einfügemarke enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die nullbasierte Zeilennummer der Zeile mit den angegebenen Zeichenindex `nIndex`. Wenn `nIndex` –&1; ist, wird die Nummer der Zeile, die das erste Zeichen der Markierung enthält, wird zurückgegeben. Wenn keine Auswahl vorhanden ist, wird die aktuelle Zeilennummer zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Ein Zeichenindex ist die Anzahl der Zeichen vom Anfang des rich-Edit-Steuerelements. Ein OLE-Element wird zum Zählen von Zeichen als ein einzelnes Zeichen gezählt.  
  
 Weitere Informationen finden Sie unter [EM_EXLINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb788005) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&20;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_20.cpp)]  
  
##  <a name="lineindex"></a>CRichEditCtrl::LineIndex  
 Ruft den Zeichenindex einer Zeile in dieser `CRichEditCtrl` Objekt.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nLine`  
 Enthält den Indexwert für die gewünschte Position im Text des Bearbeitungssteuerelements, oder –&1;. Wenn `nLine` ist-1, gibt die aktuelle Zeile, d. h. die Zeile, die die Einfügemarke enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeichenindex der Zeile im angegebenen `nLine` oder –&1;, wenn die angegebene Zeilennummer größer ist und die Anzahl der Zeilen im Bearbeitungssteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Der Zeichenindex ist die Anzahl der Zeichen vom Anfang des rich-Edit-Steuerelement in die angegebene Zeile.  
  
 Weitere Informationen finden Sie unter [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&21;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_21.cpp)]  
  
##  <a name="linelength"></a>CRichEditCtrl::LineLength  
 Ruft die Länge einer Zeile in einem rich-Edit-Steuerelement ab.  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nLine`  
 Gibt den Zeichenindex eines Zeichens in der Zeile, deren Länge abgerufen werden sollen. Wenn dieser Parameter auf –&1; ist, wird die Länge der aktuellen Zeile (die Zeile mit dem Caretzeichen) zurückgegeben, ausgenommen die Länge eines beliebigen ausgewählten Text innerhalb der Zeile. Wenn `LineLength` aufgerufen wird für eine einzeilige Edit-Steuerelement, wird dieser Parameter ignoriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `LineLength` wird aufgerufen, für ein mehrzeiliges Bearbeitungssteuerelement, ist der Rückgabewert die Länge (in Bytes) der angegebenen Zeile `nLine`. Wenn `LineLength` aufgerufen wird für eine einzeilige Edit-Steuerelement, ist der Rückgabewert die Länge (in Bytes) des Texts im Bearbeitungssteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [LineIndex](#lineindex) Member-Funktion zum Abrufen eines Zeichenindex für eine bestimmte Zeilennummer innerhalb dieses `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [LineIndex](#lineindex).  
  
##  <a name="linescroll"></a>CRichEditCtrl::LineScroll  
 Führt einen Bildlauf durch den Text eines mehrzeiligen Edit-Steuerelements.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nLines`  
 Gibt die Anzahl der Zeilen, um einen vertikalen Bildlauf ausführen.  
  
 `nChars`  
 Gibt die Anzahl von Zeichenpositionen einen horizontalen Bildlauf durchführen. Dieser Wert wird ignoriert, wenn das rich-Edit-Steuerelement entweder verfügt die **ES_RIGHT** oder **ES_CENTER** Stil. [Bearbeiten von Stilen](../../mfc/reference/edit-styles.md) werden in angegebenen [erstellen](#create).  
  
### <a name="remarks"></a>Hinweise  
 Das Bearbeitungssteuerelement wird hinter der letzten Zeile des Texts im Bearbeitungssteuerelement kein vertikaler Bildlauf ausgeführt. Wenn die aktuelle zuzüglich der Anzahl der Zeilen, die durch angegebene Zeile `nLines` überschreitet die Gesamtanzahl der Zeilen im Bearbeitungssteuerelement, der Wert wird so angepasst, dass die letzte Zeile des Edit-Steuerelements an den Anfang des Fensters bearbeiten-Steuerelement ein Bildlauf durchgeführt wird.  
  
 `LineScroll`kann verwendet werden, um hinter dem letzten Zeichen des jede Zeile ein horizontaler Bildlauf durchgeführt.  
  
 Weitere Informationen finden Sie unter [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetFirstVisibleLine](#getfirstvisibleline).  
  
##  <a name="paste"></a>CRichEditCtrl::Paste  
 Fügt die Daten aus der Zwischenablage in die `CRichEditCtrl` an der Einfügemarke die Position der Einfügemarke.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Hinweise  
 Daten werden eingefügt, nur dann, wenn die Zwischenablage Daten in einem gültigen Format enthält.  
  
 Weitere Informationen finden Sie unter [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#22;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_22.cpp)]  
  
##  <a name="pastespecial"></a>CRichEditCtrl::PasteSpecial  
 Fügt Daten in einem bestimmten Zwischenablageformat in die `CRichEditCtrl` Objekt.  
  
```  
void PasteSpecial(
    UINT nClipFormat,  
    DWORD dvAspect = 0,  
    HMETAFILE hMF = 0);
```  
  
### <a name="parameters"></a>Parameter  
 *nClipFormat*  
 Das Format der Zwischenablage einfügen in die `CRichEditCtrl` Objekt.  
  
 *dvAspect*  
 Gerät Aspekt für die Daten aus der Zwischenablage abgerufen werden sollen.  
  
 *hMF*  
 Handle für die Metadatei, die mit der iconic Ansicht des Objekts eingefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Das neue Material wird an der Einfügemarke die Position der Einfügemarke eingefügt.  
  
 Weitere Informationen finden Sie unter [EM_PASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/bb774214) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&23;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_23.cpp)]  
  
##  <a name="posfromchar"></a>CRichEditCtrl::PosFromChar  
 Ruft den Bereich Clientkoordinaten eines angegebenen Zeichens in einem Bearbeitungssteuerelement ab.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nChar`  
 Der nullbasierte Index des Zeichens.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position des Zeichens, (X, y). Bei einem einzeilige Edit-Steuerelement ist die y-Koordinate immer&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="redo"></a>CRichEditCtrl::Redo  
 Wiederholen die nächste Aktion in der Wiederholungswarteschlange des Steuerelements.  
  
```  
BOOL Redo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_REDO](http://msdn.microsoft.com/library/windows/desktop/bb774218) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="replacesel"></a>CRichEditCtrl::ReplaceSel  
 Ersetzt die aktuelle Auswahl in diesem `CRichEditCtrl` -Objekt mit dem angegebenen Text.  
  
```  
void ReplaceSel(
    LPCTSTR lpszNewText,  
    BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszNewText`  
 Ein Zeiger auf eine Null endende Zeichenfolge, die den Ersetzungstext enthält.  
  
 `bCanUndo`  
 Um anzugeben, dass diese Funktion rückgängig gemacht werden kann, legen Sie den Wert dieses Parameters auf **TRUE**. Der Standardwert ist **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Ersetzen Sie den Text für die in diesem `CRichEditCtrl` -Objekts [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
 Wenn keine aktuelle Auswahl vorhanden ist, wird der Ersetzungstext an der Einfügemarke, d. h. der Position der aktuellen Einfügemarke eingefügt.  
  
 Diese Funktion wird mit dem vorhandenen Formatierung den eingefügten Text formatiert. Ersetzen Sie den gesamten Textbereich (durch Aufrufen von `SetSel`(0, -1) vor dem Aufruf von `ReplaceSel`), besteht ein Ende der Absatz Zeichen, das Beibehalten des vorhergehenden Absatzes formatieren, die in den neu eingefügten Text erben.  
  
 Weitere Informationen finden Sie unter [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [LineIndex](#lineindex).  
  
##  <a name="requestresize"></a>CRichEditCtrl::RequestResize  
 Erzwingt, dass diese `CRichEditCtrl` Objekt senden **EN_REQUESTRESIZE** Benachrichtigung an das übergeordnete Fenster.  
  
```  
void RequestResize();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist nützlich bei [CWnd::OnSize](../../mfc/reference/cwnd-class.md#onsize) Verarbeitung für eine unbeschränkte `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter der [EM_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb774220) Nachricht und die **unbeschränkte Rich-Edit-Steuerelemente** Abschnitt [zu Rich-Edit-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb787873) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setautourldetect"></a>CRichEditCtrl::SetAutoURLDetect  
 Legt das rich-Edit-Steuerelement, eine URL automatisch zu erkennen.  
  
```  
BOOL SetAutoURLDetect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bEnable`  
 Gibt an, ob das Steuerelement festgelegt ist, um eine URL automatisch zu erkennen. Wenn **TRUE**, diese Einstellung aktiviert ist. Wenn **FALSE**, er deaktiviert ist.  
  
### <a name="return-value"></a>Rückgabewert  
 0, wenn erfolgreich, andernfalls ungleich NULL ist. Beispielsweise kann die Nachricht aufgrund von unzureichendem Arbeitsspeicher nicht.  
  
### <a name="remarks"></a>Hinweise  
 Ist diese Einstellung aktiviert ist, scannt das rich-Edit-Steuerelement den Text, um zu bestimmen, ob es sich um ein standard-URL-Format entspricht. Eine Liste dieser URL-Formate finden Sie unter [EM_AUTOURLDETECT](http://msdn.microsoft.com/library/windows/desktop/bb787991) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!NOTE]
>  Stellen Sie keine `SetAutoURLDetect` auf **TRUE** das Bearbeitungssteuerelement verwendet die **CFE_LINK** Effekt für Text als URLs. `SetAutoURLDetect`Dieser Effekt für URLs aktiviert, während es für alle anderen Text deaktiviert. Finden Sie unter [EN_LINK](http://msdn.microsoft.com/library/windows/desktop/bb787970) Weitere Informationen zu den **CFE_LINK** wirksam.  
  
##  <a name="setbackgroundcolor"></a>CRichEditCtrl::SetBackgroundColor  
 Legt die Hintergrundfarbe für diesen `CRichEditCtrl` Objekt.  
  
```  
COLORREF SetBackgroundColor(
    BOOL bSysColor,  
    COLORREF cr);
```  
  
### <a name="parameters"></a>Parameter  
 `bSysColor`  
 Gibt an, ob die Hintergrundfarbe auf den System-Wert festgelegt werden soll. Wenn dieser Wert **TRUE**, `cr` wird ignoriert.  
  
 `cr`  
 Die angeforderte Hintergrundfarbe. Nur verwendet, wenn `bSysColor` ist **FALSE**.  
  
### <a name="return-value"></a>Rückgabewert  
 Die vorherigen Hintergrundfarbe für diesen `CRichEditCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Hintergrundfarbe kann festgelegt werden, die den Systemwert oder mit einem angegebenen [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert.  
  
 Weitere Informationen finden Sie unter [EM_SETBKGNDCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774228) Nachricht und [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#24;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_24.cpp)]  
  
##  <a name="setdefaultcharformat"></a>CRichEditCtrl::SetDefaultCharFormat  
 Legt die Formatierungsattribute für den neuen Text in dieser `CRichEditCtrl` Objekt.  
  
```  
BOOL SetDefaultCharFormat(CHARFORMAT& cf);  
BOOL SetDefaultCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 In der ersten Version, die einen Zeiger auf eine [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Struktur, die das neue Standardzeichen Formatierungsattribute enthält.  
  
 In der zweiten Version, die einen Zeiger auf eine [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) -Struktur, die eine umfassende bearbeiten 2.0-Erweiterung ist auf die **CHARFORMAT** Struktur, die mit dem Standardzeichen, die Formatierungsattribute.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Nur die angegebenen Attribute der **DwMask** Mitglied `cf` dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter der [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) Nachricht und die **CHARFORMAT** und **CHARFORMAT2** Strukturen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#25;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_25.cpp)]  
  
##  <a name="seteventmask"></a>CRichEditCtrl::SetEventMask  
 Legt die Ereignismaske für diesen `CRichEditCtrl` Objekt.  
  
```  
DWORD SetEventMask(DWORD dwEventMask);
```  
  
### <a name="parameters"></a>Parameter  
 *dwEventMask*  
 Das neue Ereignismaske für diesen `CRichEditCtrl` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Das vorherige Ereignismaske.  
  
### <a name="remarks"></a>Hinweise  
 Die Ereignismaske gibt an, welche Benachrichtigung der `CRichEditCtrl` Objekt an das übergeordnete Fenster sendet.  
  
 Weitere Informationen finden Sie unter [EM_SETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb774238) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#26;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_26.cpp)]  
  
##  <a name="setmodify"></a>CRichEditCtrl::SetModify  
 Aktiviert oder deaktiviert das Änderungsflag für ein Bearbeitungssteuerelement.  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bModified`  
 Der Wert **TRUE** gibt an, dass der Text geändert wurde, und den Wert **FALSE** gibt an, dass es nicht geändert. Standardmäßig wird das geänderte Flag festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Das geänderte Flag gibt an, ob der Text im Bearbeitungssteuerelement geändert wurde. Es wird automatisch festgelegt, wenn der Benutzer den Text ändert. Der Wert abgerufen werden kann, mit der [GetModify](#getmodify) Member-Funktion.  
  
 Weitere Informationen finden Sie unter [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetModify](#getmodify).  
  
##  <a name="setolecallback"></a>CRichEditCtrl::SetOLECallback  
 Dadurch `CRichEditCtrl` Objekt ein **IRichEditOleCallback** Objekt, mit dem OLE-bezogene Ressourcen und Informationen zugreifen.  
  
```  
BOOL SetOLECallback(IRichEditOleCallback* pCallback);
```  
  
### <a name="parameters"></a>Parameter  
 `pCallback`  
 Zeiger auf eine [IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308) Objekt, das dieses `CRichEditCtrl` Objekt verwenden, um OLE-bezogene Ressourcen und Informationen zu erstellen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Diese `CRichEditCtrl` Objekt ruft [IUnknown:: AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) zum Erhöhen der Verwendungszähler für das COM-Objekt, das vom angegebenen `pCallback`.  
  
 Weitere Informationen finden Sie unter [EM_SETOLECALLBACK](http://msdn.microsoft.com/library/windows/desktop/bb774252) Nachricht und [IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308) -Schnittstelle in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setoptions"></a>CRichEditCtrl::SetOptions  
 Legt die Optionen für diesen `CRichEditCtrl` Objekt.  
  
```  
void SetOptions(
    WORD wOp,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>Parameter  
 *wOp*  
 Gibt den Typ des Vorgangs an. Einer der folgenden Werte:  
  
- `ECOOP_SET`Legen Sie die Optionen auf solche `dwFlags`.  
  
- `ECOOP_OR`Kombinieren Sie die aktuellen Optionen mit den Koordinaten `dwFlags`.  
  
- `ECOOP_AND`Behalten Sie nur die aktuellen Optionen, die auch vom angegebenen `dwFlags`.  
  
- `ECOOP_XOR`Behalten Sie nur die aktuellen Optionen, die *nicht* angegebene `dwFlags`.  
  
 `dwFlags`  
 Rich-edit-Optionen. Die Flagwerte werden im Abschnitt "Hinweise" aufgeführt.  
  
### <a name="remarks"></a>Hinweise  
 Die Optionen sind eine Kombination der folgenden Werte möglich:  
  
- `ECO_AUTOWORDSELECTION`Automatische Auswahl doppelklicken.  
  
- `ECO_AUTOVSCROLL`Automatisch den Bildlauf nach rechts um 10 Zeichen bei der Benutzer ein Zeichen am Ende der Zeile. Wenn der Benutzer die EINGABETASTE drückt, den Bildlauf des Steuerelements alle an Position&0; (null) zurück.  
  
- `ECO_AUTOHSCROLL`Wenn der Benutzer in der letzten Zeile die EINGABETASTE drückt automatisch den Bildlauf eine Seite nach oben.  
  
- `ECO_NOHIDESEL`Negiert das Standardverhalten für ein Edit-Steuerelement. Das Standardverhalten Blendet die Auswahl, wenn das Steuerelement den Eingabefokus verliert und die Auswahl, zeigt Wenn das Steuerelement den Eingabefokus erhält. Bei Angabe von `ECO_NOHIDESEL`, der markierte Text umkehren, auch wenn das Steuerelement nicht den Fokus besitzt.  
  
- `ECO_READONLY`Verhindert, dass Benutzer eingeben oder Bearbeiten von Text im Bearbeitungssteuerelement.  
  
- `ECO_WANTRETURN`Gibt an, dass ein Wagenrücklauf eingefügt werden, wenn der Benutzer die EINGABETASTE drückt, während der Eingabe von Text in ein mehrzeiliges rich-Edit-Steuerelement in einem Dialogfeld. Wenn Sie dieses Format nicht angeben, sendet das Drücken der EINGABETASTE einen Befehl an das rich-Edit-Steuerelement übergeordneten Fenster, in dem imitiert, auf das übergeordnete Fenster Standardschaltfläche (z. B. die Schaltfläche "OK" in einem Dialogfeld). Dieses Format wirkt sich nicht auf eine einzeilige edit-Steuerelement.  
  
- `ECO_SAVESEL`Behält die Auswahl, wenn das Steuerelement den Fokus verliert. Standardmäßig werden der gesamte Inhalt des Steuerelements ausgewählt, wenn es wieder den Fokus erhält.  
  
- `ECO_VERTICAL`Zeichnet Text und Objekte in vertikaler Richtung. Für nur asiatische Sprachen verfügbar.  
  
 Weitere Informationen finden Sie unter [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#27;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_27.cpp)]  
  
##  <a name="setparaformat"></a>CRichEditCtrl::SetParaFormat  
 Legt die Attribute für die aktuelle Auswahl in das Formatieren von Absätzen `CRichEditCtrl` Objekt.  
  
```  
BOOL SetParaFormat(PARAFORMAT& pf);  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>Parameter  
 `pf`  
 In der ersten Version, die einen Zeiger auf eine [ABSATZFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) -Struktur mit den neuen Standard Absatz Formatierungsattribute.  
  
 In der zweiten Version, die einen Zeiger auf eine [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) -Struktur, die eine umfassende bearbeiten 2.0-Erweiterung ist, die **ABSATZFORMAT** Struktur, das Standardzeichen Formatierungsattribute.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Nur die angegebenen Attribute der **DwMask** Mitglied `pf` dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter der [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) Nachricht und die **ABSATZFORMAT** und **PARAFORMAT2** Strukturen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#28;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_28.cpp)]  
  
##  <a name="setpunctuation"></a>CRichEditCtrl::SetPunctuation  
 Legt die Interpunktion in einem rich-Edit-Steuerelement fest.  
  
```  
BOOL SetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc);
```  
  
### <a name="parameters"></a>Parameter  
 `fType`  
 Das Flag Satzzeichen. Eine Liste der möglichen Werte finden Sie unter der `fType` -Parameter für [EM_SETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774278) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpPunc`  
 Ein Zeiger auf eine [SATZZEICHEN](http://msdn.microsoft.com/library/windows/desktop/bb787944) Struktur, wie beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn erfolgreich, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion ist nur asiatischen Versionen des Betriebssystems verfügbar.  
  
##  <a name="setreadonly"></a>CRichEditCtrl::SetReadOnly  
 Ändert die `ECO_READONLY` für diese Option `CRichEditCtrl` Objekt.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bReadOnly`  
 Gibt an, wenn diese `CRichEditCtrl` Objekt nur gelesen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Eine kurze Beschreibung dieser Option finden Sie unter [SetOptions](#setoptions). Sie können diese Funktion alle Optionen für das Festlegen `CRichEditCtrl` Objekt.  
  
 Weitere Informationen finden Sie unter [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#29;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_29.cpp)]  
  
##  <a name="setrect"></a>CRichEditCtrl::SetRect  
 Legt die Formatierung Rechteck für dieses `CRichEditCtrl` Objekt.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md) oder ein Zeiger auf eine [RECT](../../mfc/reference/rect-structure1.md) , die die neuen Grenzen für die Formatierung Rechteck angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Formatierung Rechteck ist der begrenzende Rechteck für den Text. Die einschränkende Rechteck ist unabhängig von der Größe des Fensters rich-Edit-Steuerelement. Wenn dies `CRichEditCtrl` -Objekt erstellt wird, die Formatierung Rechteck hat die gleiche Größe des Clientbereichs des Fensters. Verwendung `SetRect` die Formatierung Rechteck größer oder kleiner als das rich-Edit-Fenster erstellt.  
  
 Weitere Informationen finden Sie unter [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#30;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_30.cpp)]  
  
##  <a name="setsel"></a>CRichEditCtrl::SetSel  
 Die Auswahl in diesem `CRichEditCtrl` Objekt.  
  
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
 Nullbasierte Index des letzten Zeichens der Auswahl.  
  
 `cr`  
 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) Struktur, die die Grenzen der aktuellen Auswahl enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die zwei Arten von dieser Funktion bieten eine Alternative zum Festlegen der Grenzen für die Auswahl. Führen Sie die kurze Beschreibungen der folgenden Formate:  
  
- **Memberfunktion SetSel (** `cr` **)** dieses Formular verwendet die **CHARRANGE** Struktur mit den **CpMin** und **CpMax** festlegen die Grenzen Member zu.  
  
- **Memberfunktion SetSel (** `nStartChar` **,** `nEndChar` **)** dieses Formulars verwenden Sie die Parameter `nStartChar` und `nEndChar` die Grenzen festlegen.  
  
 Die Einfügemarke wird am Ende der Auswahl durch den größeren der Beginn platziert ( **CpMin** oder `nStartChar`) und Ende ( **CpMax** oder `nEndChar`) Indizes. Diese Funktion führt einen Bildlauf durch den Inhalt der `CRichEditCtrl` , damit die Einfügemarke sichtbar ist.  
  
 Wählen Sie sämtlichen Text in dieser `CRichEditCtrl` -Objekt, rufen Sie `SetSel` mit einem startIndex 0 und Endindex – 1.  
  
 Weitere Informationen finden Sie unter [EM_EXSETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788007) Nachricht und [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Memberfunktion GetSel](#getsel).  
  
##  <a name="setselectioncharformat"></a>CRichEditCtrl::SetSelectionCharFormat  
 Legt die Formatierung für den Text in der aktuellen Auswahl in diesem `CRichEditCtrl` Objekt.  
  
```  
BOOL SetSelectionCharFormat(CHARFORMAT& cf);  
BOOL SetSelectionCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 In der ersten Version, die einen Zeiger auf eine [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Struktur, die die neue Formatierung enthält Attribute, für die aktuelle Auswahl.  
  
 In der zweiten Version, die einen Zeiger auf eine [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) -Struktur, die eine umfassende bearbeiten 2.0-Erweiterung ist, die **CHARFORMAT** Struktur, die mit dem neuen Zeichen, die Attribute für die aktuelle Auswahl formatieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Nur die angegebenen Attribute der **DwMask** Mitglied `cf` dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter der [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) und **CHARFORMAT** und **CHARFORMAT2** Strukturen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#31;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_31.cpp)]  
  
##  <a name="settargetdevice"></a>CRichEditCtrl::SetTargetDevice  
 Legt die Ziel-Gerät und die Standardlinienstärke für die WYSIWYG-(was Sie sehen, ist das Ergebnis) in diesem Formatierung `CRichEditCtrl` Objekt.  
  
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
 Handle für den Gerätekontext für das neue Gerät.  
  
 *lLineWidth*  
 Die Linienstärke für die Formatierung verwendet.  
  
 `dc`  
 [CDC](../../mfc/reference/cdc-class.md) für das neue Gerät.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Funktion erfolgreich ist, das rich-Edit-Steuerelement als Eigentümer des Geräts Kontext als Parameter übergeben. In diesem Fall sollte die aufrufende Funktion den Gerätekontext nicht gelöscht.  
  
 Weitere Informationen finden Sie unter [EM_SETTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/bb774282) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#32;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_32.cpp)]  
  
##  <a name="settextmode"></a>CRichEditCtrl::SetTextMode  
 Legt den Text-Modus oder rückgängig und wiederholen für ein rich-Edit-Steuerelement fest.  
  
```  
BOOL SetTextMode(UINT fMode);
```  
  
### <a name="parameters"></a>Parameter  
 *fMode*  
 Gibt den neuen Einstellungen für das Steuerelement Text-Modus und Rückgängigmachen Parameter an. Eine Liste der möglichen Werte finden Sie unter der Mode-Parameter für [EM_SETTEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774286) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 0, wenn erfolgreich, andernfalls ungleich NULL ist.  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Text, finden Sie unter **EM_SETTEXTMODE** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Diese Memberfunktion schlägt fehl, wenn das Steuerelement Text enthält. Um sicherzustellen, dass das Steuerelement leer ist, senden Sie eine [WM_SETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632644) Nachricht mit einer leeren Zeichenfolge.  
  
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
 Standardmäßig ist die maximale Anzahl von Aktionen in der Rückgängig-Warteschlange 100. Wenn Sie diese Zahl erhöhen, muss genügend Speicherplatz für die neue Anzahl vorhanden sein. Legen Sie für eine bessere Leistung den Grenzwert auf den kleinstmöglichen Wert.  
  
##  <a name="setwordcharformat"></a>CRichEditCtrl::SetWordCharFormat  
 Legt die Formatierung der Attribute für das aktuell ausgewählte Wort in diesem `CRichEditCtrl` Objekt.  
  
```  
BOOL SetWordCharFormat(CHARFORMAT& cf);  
BOOL SetWordCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 In der ersten Version, die einen Zeiger auf eine [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Struktur, die die neue Formatierung enthält Attribute für das aktuell ausgewählte Wort.  
  
 In der zweiten Version, die einen Zeiger auf eine [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) -Struktur, die eine umfassende bearbeiten 2.0-Erweiterung ist, die **CHARFORMAT** Struktur, die mit dem neuen Zeichen Formatierungsattribute für das aktuell ausgewählte Wort.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich 0 (null), wenn erfolgreich, andernfalls 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Nur die angegebenen Attribute der **DwMask** Mitglied `cf` dieser Funktion geändert werden.  
  
 Weitere Informationen finden Sie unter der [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) Nachricht und die **CHARFORMAT** und **CHARFORMAT2** Strukturen in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&33;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_33.cpp)]  
  
##  <a name="setwordwrapmode"></a>CRichEditCtrl::SetWordWrapMode  
 Legt die Zeilen- und Trennen von Wörtern Optionen für das Rich edit-Steuerelement.  
  
```  
UINT SetWordWrapMode(UINT uFlags) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `uFlags`  
 Die Optionen, die für Zeilenumbrüche und Worttrennungen festgelegt. Eine Liste der möglichen Optionen, finden Sie unter [EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Zeilen- und Worttrennung Optionen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Meldung ist nur in asiatischen Sprachversionen des Betriebssystems verfügbar.  
  
##  <a name="stopgrouptyping"></a>CRichEditCtrl::StopGroupTyping  
 Beendet das Steuerelement Sammeln von zusätzlichen Aktionen in die aktuelle Rückgängig-Aktion eingeben.  
  
```  
void StopGroupTyping();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement speichert die nächste Aktion eingeben, ggf. in eine neue Aktion in der Rückgängig-Warteschlange.  
  
 Weitere Informationen finden Sie unter [EM_STOPGROUPTYPING](http://msdn.microsoft.com/library/windows/desktop/bb774300) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="streamin"></a>CRichEditCtrl::StreamIn  
 Ersetzt Text in dieser `CRichEditCtrl` Objekt mit Text aus dem angegebenen Eingabestream.  
  
```  
long StreamIn(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>Parameter  
 `nFormat`  
 Flags, die die Eingabedaten Formate angeben. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 `es`  
 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) -Struktur, die den Eingabedatenstrom angibt. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl von Zeichen aus dem Eingabestream lesen.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert des `nFormat` muss eines der folgenden sein:  
  
- `SF_TEXT`Gibt nur Lesen von Text an.  
  
- `SF_RTF`Gibt an, Lesen von Text und Formatierung.  
  
 Diese Werte können kombiniert werden, mit `SFF_SELECTION`. Wenn `SFF_SELECTION` angegeben ist, `StreamIn` ersetzt die aktuelle Auswahl mit dem Inhalt des Eingabedatenstroms. Wenn sie nicht angegeben ist, `StreamIn` ersetzt den gesamten Inhalt dieses `CRichEditCtrl` Objekt.  
  
 In der **EDITSTREAM** Parameter `es`, Sie geben eine Callback-Funktion, die einen Puffer mit Text ausfüllt. Diese Callback-Funktion wird wiederholt aufgerufen, bis der Eingabestream erschöpft ist.  
  
 Weitere Informationen finden Sie unter [EM_STREAMIN](http://msdn.microsoft.com/library/windows/desktop/bb774302) Nachricht und [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#34;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_34.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#35;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_35.cpp)]  
  
##  <a name="streamout"></a>CRichEditCtrl::StreamOut  
 Schreibt den Inhalt dieses `CRichEditCtrl` Objekt in den angegebenen Ausgabestream.  
  
```  
long StreamOut(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>Parameter  
 `nFormat`  
 Flags, die die Daten Ausgabeformate angeben. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
 `es`  
 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) -Struktur, die den Ausgabestream angibt. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
### <a name="return-value"></a>Rückgabewert  
 Anzahl der Zeichen in den Ausgabestream geschrieben.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert des `nFormat` muss eines der folgenden sein:  
  
- `SF_TEXT`Gibt nur das Schreiben von Text an.  
  
- `SF_RTF`Gibt an, das Schreiben von Text und Formatierung.  
  
- `SF_RTFNOOBJS`Gibt das Schreiben von Text und Formatierung OLE-Elemente durch Leerzeichen ersetzt werden.  
  
- `SF_TEXTIZED`Gibt an, das Schreiben von Text und Formatierung mit Textdarstellungen von OLE-Elementen.  
  
 Diese Werte können kombiniert werden, mit `SFF_SELECTION`. Wenn `SFF_SELECTION` angegeben ist, `StreamOut` die aktuelle Auswahl in den Ausgabestrom schreibt. Wenn sie nicht angegeben ist, `StreamOut` schreibt den gesamten Inhalt dieses `CRichEditCtrl` Objekt.  
  
 In der **EDITSTREAM** Parameter `es`, geben Sie eine Rückruffunktion, die einen Puffer mit Text ausfüllt. Diese Callback-Funktion wird wiederholt aufgerufen, bis der Ausgabestream erschöpft ist.  
  
 Weitere Informationen finden Sie unter [EM_STREAMOUT](http://msdn.microsoft.com/library/windows/desktop/bb774304) Nachricht und [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CRichEditCtrl Nr.&36;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_36.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl&#37;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_37.cpp)]  
  
##  <a name="undo"></a>CRichEditCtrl::Undo  
 Macht den letzten Vorgang in das rich-Edit-Steuerelement.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Rückgängig-Vorgang erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Rückgängig-Vorgang kann auch rückgängig gemacht werden. Sie können z. B. gelöschten Text mit dem ersten Aufruf von wiederherstellen **Rückgängig**. Solange keine Beteiligte Bearbeitungsvorgangs vorhanden ist, können, entfernen Sie den Text erneut mit einem zweiten Aufruf von **Rückgängig**.  
  
 Weitere Informationen finden Sie unter [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CanUndo](#canundo).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CRichEditView-Klasse](../../mfc/reference/cricheditview-class.md)

