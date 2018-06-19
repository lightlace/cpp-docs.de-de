---
title: CEdit-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CEdit
- AFXWIN/CEdit
- AFXWIN/CEdit::CEdit
- AFXWIN/CEdit::CanUndo
- AFXWIN/CEdit::CharFromPos
- AFXWIN/CEdit::Clear
- AFXWIN/CEdit::Copy
- AFXWIN/CEdit::Create
- AFXWIN/CEdit::Cut
- AFXWIN/CEdit::EmptyUndoBuffer
- AFXWIN/CEdit::FmtLines
- AFXWIN/CEdit::GetCueBanner
- AFXWIN/CEdit::GetFirstVisibleLine
- AFXWIN/CEdit::GetHandle
- AFXWIN/CEdit::GetHighlight
- AFXWIN/CEdit::GetLimitText
- AFXWIN/CEdit::GetLine
- AFXWIN/CEdit::GetLineCount
- AFXWIN/CEdit::GetMargins
- AFXWIN/CEdit::GetModify
- AFXWIN/CEdit::GetPasswordChar
- AFXWIN/CEdit::GetRect
- AFXWIN/CEdit::GetSel
- AFXWIN/CEdit::HideBalloonTip
- AFXWIN/CEdit::LimitText
- AFXWIN/CEdit::LineFromChar
- AFXWIN/CEdit::LineIndex
- AFXWIN/CEdit::LineLength
- AFXWIN/CEdit::LineScroll
- AFXWIN/CEdit::Paste
- AFXWIN/CEdit::PosFromChar
- AFXWIN/CEdit::ReplaceSel
- AFXWIN/CEdit::SetCueBanner
- AFXWIN/CEdit::SetHandle
- AFXWIN/CEdit::SetHighlight
- AFXWIN/CEdit::SetLimitText
- AFXWIN/CEdit::SetMargins
- AFXWIN/CEdit::SetModify
- AFXWIN/CEdit::SetPasswordChar
- AFXWIN/CEdit::SetReadOnly
- AFXWIN/CEdit::SetRect
- AFXWIN/CEdit::SetRectNP
- AFXWIN/CEdit::SetSel
- AFXWIN/CEdit::SetTabStops
- AFXWIN/CEdit::ShowBalloonTip
- AFXWIN/CEdit::Undo
dev_langs:
- C++
helpviewer_keywords:
- CEdit [MFC], CEdit
- CEdit [MFC], CanUndo
- CEdit [MFC], CharFromPos
- CEdit [MFC], Clear
- CEdit [MFC], Copy
- CEdit [MFC], Create
- CEdit [MFC], Cut
- CEdit [MFC], EmptyUndoBuffer
- CEdit [MFC], FmtLines
- CEdit [MFC], GetCueBanner
- CEdit [MFC], GetFirstVisibleLine
- CEdit [MFC], GetHandle
- CEdit [MFC], GetHighlight
- CEdit [MFC], GetLimitText
- CEdit [MFC], GetLine
- CEdit [MFC], GetLineCount
- CEdit [MFC], GetMargins
- CEdit [MFC], GetModify
- CEdit [MFC], GetPasswordChar
- CEdit [MFC], GetRect
- CEdit [MFC], GetSel
- CEdit [MFC], HideBalloonTip
- CEdit [MFC], LimitText
- CEdit [MFC], LineFromChar
- CEdit [MFC], LineIndex
- CEdit [MFC], LineLength
- CEdit [MFC], LineScroll
- CEdit [MFC], Paste
- CEdit [MFC], PosFromChar
- CEdit [MFC], ReplaceSel
- CEdit [MFC], SetCueBanner
- CEdit [MFC], SetHandle
- CEdit [MFC], SetHighlight
- CEdit [MFC], SetLimitText
- CEdit [MFC], SetMargins
- CEdit [MFC], SetModify
- CEdit [MFC], SetPasswordChar
- CEdit [MFC], SetReadOnly
- CEdit [MFC], SetRect
- CEdit [MFC], SetRectNP
- CEdit [MFC], SetSel
- CEdit [MFC], SetTabStops
- CEdit [MFC], ShowBalloonTip
- CEdit [MFC], Undo
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fba91f4c16c5b356b1e7a11e35380a15eb98eb1
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
ms.locfileid: "34463078"
---
# <a name="cedit-class"></a>CEdit Class
Stellt die Funktionalität eines Windows-Bearbeitungssteuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CEdit : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEdit::CEdit](#cedit)|Erstellt eine `CEdit` Control-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEdit::CanUndo](#canundo)|Bestimmt, ob ein Bearbeitungssteuerelement Vorgang rückgängig gemacht werden kann.|  
|[CEdit::CharFromPos](#charfrompos)|Ruft die Zeilen- und Indizes für das Zeichen am nächsten an eine angegebene Position ab.|  
|[CEdit::Clear](#clear)|Löscht (deaktiviert) die aktuelle Auswahl in die Bearbeitung (sofern vorhanden) steuern.|  
|[CEdit::Copy](#copy)|Kopiert die aktuelle Auswahl (sofern vorhanden) in das Bearbeitungssteuerelement in der Zwischenablage in **HIERSVR** Format.|  
|[CEdit::Create](#create)|Erstellt die Windows-Bearbeitungssteuerelements und fügt es der `CEdit` Objekt.|  
|[CEdit::Cut](#cut)|Löscht (Teilstücke) die aktuelle Auswahl (sofern vorhanden) in den Bearbeitungsmodus zu steuern und den gelöschten Text in die Zwischenablage kopiert **HIERSVR** Format.|  
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|Setzt (löscht) das Flag zum Rückgängigmachen des bearbeiten-Steuerelement zurück.|  
|[CEdit::FmtLines](#fmtlines)|Legt die Einbindung von soft-Zeilenumbruchzeichen ein- oder ausschalten in einem mehrzeiligen Edit-Steuerelement fest.|  
|[CEdit::GetCueBanner](#getcuebanner)|Ruft den Text, der angezeigt wird, wie der Text Cue bzw. die QuickInfo, in einem Bearbeitungssteuerelement, wenn das Steuerelement leer ist und verfügt nicht über den Fokus.|  
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|Bestimmt die oberste sichtbare Zeile in einem Bearbeitungssteuerelement.|  
|[CEdit::GetHandle](#gethandle)|Ruft ein Handle für den Arbeitsspeicher, der für ein Bearbeitungssteuerelement für mehrzeiligen derzeit zugewiesen ist.|  
|[CEdit::GetHighlight](#gethighlight)|Ruft die Indizes der die Start- und Endzeichen in einem Bereich von Text, der in der aktuellen Edit-Steuerelement hervorgehoben ist.|  
|[CEdit::GetLimitText](#getlimittext)|Ruft der Höchstmenge des Texts dies `CEdit` enthalten können.|  
|[CEdit::GetLine](#getline)|Ruft eine Textzeile aus einem Bearbeitungssteuerelement ab.|  
|[CEdit::GetLineCount](#getlinecount)|Ruft die Anzahl der Zeilen in einem mehrzeiligen Edit-Steuerelement ab.|  
|[CEdit::GetMargins](#getmargins)|Ruft den linken und rechten Rand für `CEdit`.|  
|[CEdit::GetModify](#getmodify)|Bestimmt, ob der Inhalt des Edit-Steuerelements geändert wurden.|  
|[CEdit::GetPasswordChar](#getpasswordchar)|Ruft das Kennwortzeichen in ein Bearbeitungssteuerelement angezeigt, wenn der Benutzer Text eingibt.|  
|[CEdit::GetRect](#getrect)|Ruft die Formatierung Rechteck ein Bearbeitungssteuerelement ab.|  
|[CEdit::GetSel](#getsel)|Ruft die Positionen der erste und letzte Zeichen der aktuellen Auswahl in einem Bearbeitungssteuerelement.|  
|[CEdit::HideBalloonTip](#hideballoontip)|Blendet alle SprechblasenInfo Edit-Steuerelement für die aktuelle zugeordnet.|  
|[CEdit::LimitText](#limittext)|Beschränkt die Länge des Texts, der der Benutzer in einem Bearbeitungssteuerelement eingeben kann.|  
|[CEdit::LineFromChar](#linefromchar)|Ruft die Zeilennummer der Zeile mit der angegebenen Zeichenindex ab.|  
|[CEdit::LineIndex](#lineindex)|Ruft den Zeichenindex einer Zeile in einem mehrzeiligen Edit-Steuerelement ab.|  
|[CEdit::LineLength](#linelength)|Ruft die Länge der Zeile in einem Bearbeitungssteuerelement ab.|  
|[CEdit::LineScroll](#linescroll)|Scrollt den Text eines mehrzeiligen Bearbeitungssteuerelements an.|  
|[CEdit::Paste](#paste)|Die Daten aus der Zwischenablage in das Bearbeitungssteuerelement an der aktuellen Cursorposition eingefügt. Daten werden nur dann, wenn Daten in die Zwischenablage enthält, eingefügt **HIERSVR** Format.|  
|[CEdit::PosFromChar](#posfromchar)|Ruft die Koordinaten der linken oberen Ecke des angegebenen Zeichenindex ab.|  
|[CEdit::ReplaceSel](#replacesel)|Ersetzt die aktuelle Auswahl in einem Bearbeitungssteuerelement mit dem angegebenen Text.|  
|[CEdit::SetCueBanner](#setcuebanner)|Legt den Text, der angezeigt wird, wie der Text Cue bzw. die QuickInfo, in einem Bearbeitungssteuerelement, wenn das Steuerelement leer ist und verfügt nicht über den Fokus.|  
|[CEdit::SetHandle](#sethandle)|Legt das Handle in den lokalen Speicher, der durch ein Bearbeitungssteuerelement für mehrzeiligen verwendet wird.|  
|[CEdit::SetHighlight](#sethighlight)|Bearbeitungssteuerelement für kennzeichnet ein Textbereich, der in der aktuellen angezeigt wird.|  
|[CEdit::SetLimitText](#setlimittext)|Der Höchstmenge des Texts wird hiermit `CEdit` enthalten können.|  
|[CEdit::SetMargins](#setmargins)|Legt den linken und rechten Rand für diesen `CEdit`.|  
|[CEdit::SetModify](#setmodify)|Aktiviert oder deaktiviert das Flag Änderung für ein Bearbeitungssteuerelement.|  
|[CEdit::SetPasswordChar](#setpasswordchar)|Legt fest oder entfernt ein Kennwort ein Zeichen in ein Bearbeitungssteuerelement angezeigt, wenn der Benutzer Text eingibt.|  
|[CEdit::SetReadOnly](#setreadonly)|Legt den schreibgeschützten Zustand eines Bearbeitungssteuerelements.|  
|[CEdit::SetRect](#setrect)|Legt die Formatierung Rechteck eines mehrzeiligen Bearbeitungssteuerelements fest und aktualisiert das Steuerelement.|  
|[CEdit::SetRectNP](#setrectnp)|Legt die Formatierung Rechteck eines mehrzeiligen Bearbeitungssteuerelements ohne Neuzeichnen Fenster des Steuerelements fest.|  
|[CEdit::SetSel](#setsel)|Wählt einen Bereich von Zeichen in einem Bearbeitungssteuerelement.|  
|[CEdit::SetTabStops](#settabstops)|Legt die Tabstopps in einem mehrzeiligen Bearbeitungssteuerelements an.|  
|[CEdit::ShowBalloonTip](#showballoontip)|Zeigt eine SprechblasenInfo, die die aktuelle Edit-Steuerelement zugeordnet ist.|  
|[CEdit::Undo](#undo)|Kehrt den letzten Bearbeitungssteuerelement Vorgang.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Bearbeitungssteuerelement ist ein rechteckiges untergeordnetes Fenster, die in dem der Benutzer Text eingeben kann.  
  
 Sie können ein Bearbeitungssteuerelement aus einer Dialogfeldvorlage oder direkt im Code erstellen. In beiden Fällen rufen Sie zunächst den Konstruktor `CEdit` zum Erstellen der `CEdit` -Objekt, und rufen Sie dann die [erstellen](#create) Memberfunktion zum Erstellen der Windows-Bearbeitungssteuerelements und fügen Sie es auf die `CEdit` Objekt.  
  
 Konstruktion kann ein langwieriger Vorgang in einer abgeleiteten Klasse `CEdit`. Schreiben Sie einen Konstruktor für die abgeleitete Klasse, und rufen **erstellen** von innerhalb des Konstruktors.  
  
 `CEdit` erbt die wichtigsten Features von `CWnd`. Festlegen und Abrufen von Text aus einer `CEdit` -Objekts die `CWnd` Memberfunktionen [SetWindowText](cwnd-class.md#setwindowtext) und [GetWindowText](cwnd-class.md#getwindowtext), welche Set- oder Get den gesamten Inhalt bearbeiten steuern, auch wenn es ist ein mehrzeiliges Steuerelement. Textzeilen in einem mehrzeiligen Steuerelement werden durch '\r\n' Zeichensequenzen getrennt. Auch wenn ein Bearbeitungssteuerelement mehrzeilig ist, abrufen und festlegen Teil der Text des Steuerelements durch Aufrufen der `CEdit` Memberfunktionen [GetLine](#getline), [Memberfunktion SetSel](#setsel), [Memberfunktion GetSel](#getsel), und [ ReplaceSel](#replacesel).  
  
 Wenn Sie ein Bearbeitungssteuerelement zum übergeordneten per Windows-benachrichtigungsmeldungen behandeln möchten (normalerweise eine abgeleitete Klasse `CDialog`), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag und Nachrichtenhandler Memberfunktion hinzufügen.  
  
 Jede Meldungszuordnungseintrags weist folgende Form auf:  
  
  **ON_**_Benachrichtigung_**(** _Id_**,** _MemberFxn_ **)**
  
 wobei `id` gibt die untergeordneten Fenster-ID des Bearbeitungssteuerelements Senden der Benachrichtigung und `memberFxn` ist der Name der übergeordneten-Memberfunktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.  
  
 Das übergeordnete Funktionsprototyp lautet wie folgt:  
  
 **Afx_msg** "void" MemberFxn **();**  
  
 Es folgt eine Liste der möglichen Meldungszuordnungseinträge und eine Beschreibung der Fälle, in denen sie zum übergeordneten Element gesendet werden:  
  
- **ON_EN_CHANGE** der Benutzer eine Aktion, die Text in ein Bearbeitungssteuerelement möglicherweise geändert haben übernommen hat. Im Gegensatz zu den **EN_UPDATE** benachrichtigungsmeldung, diese Benachrichtigung wird gesendet, nachdem Windows die Anzeige aktualisiert.  
  
- **ON_EN_ERRSPACE** das Bearbeitungssteuerelement nicht genügend Speicherplatz, um eine bestimmte Anforderung zu erfüllen zuweisen.  
  
- **ON_EN_HSCROLL** der Benutzer klickt auf ein Bearbeitungssteuerelement horizontale Bildlaufleiste angezeigt. Das übergeordnete Fenster wird benachrichtigt, bevor der Bildschirm aktualisiert wird.  
  
- **ON_EN_KILLFOCUS** Edit-Steuerelement den Eingabefokus verliert.  
  
- **ON_EN_MAXTEXT** das aktuelle einfügen hat die angegebene Anzahl von Zeichen für das Bearbeitungssteuerelement überschritten und wurde abgeschnitten. Auch gesendet, wenn ein Bearbeitungssteuerelement über keinen der **ES_AUTOHSCROLL** Stil und die Anzahl der einzufügenden Zeichen übersteigt die Breite des Bearbeitungssteuerelements. Auch gesendet, wenn ein Bearbeitungssteuerelement über keinen der **ES_AUTOVSCROLL** Stil und die Gesamtzahl der Zeilen, die infolge einer Einfügemarke die Höhe des Bearbeitungssteuerelements überschreiten würde.  
  
- **ON_EN_SETFOCUS** gesendet, wenn ein Bearbeitungssteuerelement über den Eingabefokus erhält.  
  
- **ON_EN_UPDATE** das Bearbeitungssteuerelement geänderten Text angezeigt wird. Gesendet, nachdem das Steuerelement den Text formatiert hat, aber bevor sie den Text Bildschirme, sodass die Größe des Fensters geändert werden kann, bei Bedarf.  
  
- **ON_EN_VSCROLL** der Benutzer klickt auf ein Bearbeitungssteuerelement vertikale Bildlaufleiste angezeigt. Das übergeordnete Fenster wird benachrichtigt, bevor der Bildschirm aktualisiert wird.  
  
 Bei Erstellung einer `CEdit` Objekt in einem Dialogfeld der `CEdit` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Bei Erstellung einer `CEdit` Objekt aus einer Ressource mit dem Dialog-Editor die `CEdit` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie erstellen ein `CEdit` Objekt innerhalb eines Fensters müssen Sie möglicherweise auch sie zerstört werden. Bei Erstellung der `CEdit` Objekt im Stapel befindet, automatisch zerstört wird. Bei Erstellung der `CEdit` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** edit-Steuerelement auf das Objekt, das sie zerstört werden, wenn der Benutzer den Windows beendet. Wenn Sie alle in Speicher der `CEdit` Objekt außer Kraft, indem die `CEdit` Destruktor, der die Zuordnungen zu verwerfen.  
  
 Um bestimmte Formate in ein Bearbeitungssteuerelement zu ändern (z. B. **ES_READONLY**) müssen Sie bestimmte Nachrichten senden, an das Steuerelement statt [ModifyStyle](cwnd-class.md#modifystyle). Finden Sie unter [bearbeiten Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb775464) im Windows SDK.  
  
 Weitere Informationen zu `CEdit` finden Sie unter:  
  
- [Steuerelemente](../../mfc/controls-mfc.md)  
  
-   Knowledge Base-Artikel Q259949: INFO: SetCaretPos() ist nicht geeignet mit CEdit oder CRichEditCtrl-Steuerelementen  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 `CEdit`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="canundo"></a>  CEdit::CanUndo  
 Rufen Sie diese Funktion, um zu bestimmen, ob die letzte Bearbeitung rückgängig gemacht werden kann.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die letzte Bearbeitung durch einen Aufruf von rückgängig gemacht werden, kann die **Rückgängig** Memberfunktion; 0, wenn sie kann nicht rückgängig gemacht werden.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::Undo](#undo).  
  
##  <a name="cedit"></a>  CEdit::CEdit  
 Erstellt ein `CEdit`-Objekt.  
  
```  
CEdit();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [erstellen](#create) zum Erstellen der Windows-Bearbeitungssteuerelements.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]  
  
##  <a name="charfrompos"></a>  CEdit::CharFromPos  
 Mit dieser Funktion wird zum Abrufen der nullbasierten Position und die Zeichen Indizes des Zeichens am nächsten liegt der angegebene Punkt in dieser `CEdit` Steuerelement  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Die Koordinaten eines Punkts in den Clientbereich dieses `CEdit` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeichenindex in das niederwertige **WORD**, und der Zeilenindex in die höherwertigen **WORD**.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Memberfunktion ist verfügbar ab Windows 95 und Windows NT 4.0.  
  
 Weitere Informationen finden Sie unter [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]  
  
##  <a name="clear"></a>  CEdit::Clear  
 Mit dieser Funktion können (clear) die aktuelle Auswahl in das Bearbeitungssteuerelement (sofern vorhanden) löschen.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Löschen von ausgeführten **deaktivieren** können rückgängig gemacht werden, durch Aufrufen der [Rückgängig](#undo) Memberfunktion.  
  
 Rufen Sie zum Löschen der aktuellen Auswahl, und fügen Sie den gelöschten Inhalt in die Zwischenablage, die [Ausschneiden](#cut) Memberfunktion.  
  
 Weitere Informationen finden Sie unter [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]  
  
##  <a name="copy"></a>  CEdit::Copy  
 Rufen Sie diese Funktion zum Kopieren Sie die aktuelle Auswahl (sofern vorhanden) in das Bearbeitungssteuerelement in der Zwischenablage in **HIERSVR** Format.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]  
  
##  <a name="create"></a>  CEdit::Create  
 Erstellt die Windows-Bearbeitungssteuerelements und fügt es der `CEdit` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Bearbeitungssteuerelement-Stil. Wenden Sie eine beliebige Kombination von [Bearbeiten von Stilen](styles-used-by-mfc.md#edit-styles) an das Steuerelement.  
  
 `rect`  
 Gibt des Bearbeitungssteuerelements Größe und Position. Kann eine `CRect` Objekt oder `RECT` Struktur.  
  
 `pParentWnd`  
 Gibt an, das Steuerelement zum Bearbeiten des übergeordneten Fensters (in der Regel eine `CDialog`). Es muss nicht **NULL**.  
  
 `nID`  
 Gibt den Edit-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CEdit` Objekt in zwei Schritten. Rufen Sie zunächst die `CEdit` Konstruktor und rufen Sie dann **erstellen**, die die Windows-Bearbeitungssteuerelements erstellt, und fügt es der `CEdit` Objekt.  
  
 Wenn **erstellen** ausgeführt wird, sendet Windows die [WM_NCCREATE](http://msdn.microsoft.com/library/windows/desktop/ms632635), [WM_NCCALCSIZE](http://msdn.microsoft.com/library/windows/desktop/ms632634), [WM_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619), und [WM_ GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626) Nachrichten an das Steuerelement zum Bearbeiten.  
  
 Diese Nachrichten werden standardmäßig verarbeitet der [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate), und [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standard-Meldungsbehandlung zu erweitern, leiten Sie eine Klasse von `CEdit`, eine meldungszuordnung an die neue Klasse hinzufügen und die oben genannten Meldungshandler Memberfunktionen überschreiben. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für die neue Klasse.  
  
 Übernehmen Sie die folgenden [Fensterstile](styles-used-by-mfc.md#window-styles) auf das Bearbeitungssteuerelement.  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
- **WS_TABSTOP** Edit-Steuerelement in der Tabulatorreihenfolge einschließen  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]  
  
##  <a name="cut"></a>  CEdit::Cut  
 Rufen Sie diese Funktion zum Löschen (Cut) die aktuelle Auswahl (sofern vorhanden) in das Bearbeitungssteuerelement und kopieren Sie den gelöschten Text in die Zwischenablage **HIERSVR** Format.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Löschen von ausgeführten **Ausschneiden** können rückgängig gemacht werden, durch Aufrufen der [rückgängig machen](#undo) Memberfunktion.  
  
 Um die aktuelle Auswahl ohne platzieren den gelöschten Text in die Zwischenablage zu löschen, rufen die [deaktivieren](#clear) Memberfunktion.  
  
 Weitere Informationen finden Sie unter [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]  
  
##  <a name="emptyundobuffer"></a>  CEdit::EmptyUndoBuffer  
 Rufen Sie diese Funktion zum Zurücksetzen (löschen) das Flag zum Rückgängigmachen des ein Bearbeitungssteuerelement.  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Bearbeitungssteuerelement werden kann nicht den letzten Vorgang rückgängig gemacht. Der Rückgängig-Flag wird festgelegt, wenn ein Vorgang in das Bearbeitungssteuerelement rückgängig gemacht werden kann.  
  
 Das Flag zum Rückgängigmachen wird automatisch gelöscht, sobald die [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) oder [SetHandle](#sethandle) `CWnd` Memberfunktionen aufgerufen werden.  
  
 Weitere Informationen finden Sie unter [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]  
  
##  <a name="fmtlines"></a>  CEdit::FmtLines  
 Mit dieser Funktion können die Aufnahme von soft-Zeilenumbruchzeichen in ein Bearbeitungssteuerelement für mehrzeiligen on oder off festgelegt.  
  
```  
BOOL FmtLines(BOOL bAddEOL);
```  
  
### <a name="parameters"></a>Parameter  
 *bAddEOL*  
 Gibt an, ob soft-Zeilenumbruchzeichen eingefügt werden soll. Der Wert **"true"** fügt die Zeichen; ein Wert von **"false"** entfernt sie.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn Formatierung auftritt. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein weichen Zeilenumbruch besteht aus zwei Wagenrückläufe und einen Zeilenvorschub am Ende einer Zeile, die aufgrund von Wortumbruch unterbrochen wird eingefügt. Ein Hard Zeilenumbruch besteht aus einem Wagenrücklauf und ein Zeilenvorschub. Zeilen, die mit einer Festplatte Zeilenumbruch enden sind nicht betroffen von `FmtLines`.  
  
 Windows wird nur dann Antworten, wenn die `CEdit` Objekt ist ein Bearbeitungssteuerelement für mehrzeiligen.  
  
 `FmtLines` wirkt sich nur auf den Puffer zurückgegebenes [GetHandle](#gethandle) und der zurückgegebene Text [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627). Es hat keine Auswirkungen auf die Anzeige von Text in das Bearbeitungssteuerelement.  
  
 Weitere Informationen finden Sie unter [EM_FMTLINES](http://msdn.microsoft.com/library/windows/desktop/bb761570) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]  
  
##  <a name="getcuebanner"></a>  CEdit::GetCueBanner  
 Ruft den Text, der angezeigt wird, wie der Text Cue bzw. die QuickInfo, die in einem Bearbeitungssteuerelement, wenn das Steuerelement leer ist.  
  
```  
BOOL GetCueBanner(
    LPWSTR lpszText,  
    int cchText) const;  
  
CString GetCueBanner() const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `lpszText`  
 Ein Zeiger auf eine Zeichenfolge, die den Hinweistext enthält.  
  
 [in] `cchText`  
 Die Anzahl der Zeichen, die empfangen werden können. Diese Zahl umfasst das abschließende `NULL` Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Für die erste Überladung `true` , wenn die Methode erfolgreich; andernfalls ist `false`.  
  
 Für die zweite Überladung eine [CString](../../atl-mfc-shared/using-cstring.md) , die den Hinweistext enthält, wenn die Methode erfolgreich, andernfalls ist die leere Zeichenfolge ("").  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [EM_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761572) Nachricht, die im Windows SDK beschrieben wird. Weitere Informationen finden Sie unter der [Edit_GetCueBannerText](http://msdn.microsoft.com/library/windows/desktop/bb761695) Makro.  
  
##  <a name="getfirstvisibleline"></a>  CEdit::GetFirstVisibleLine  
 Mit dieser Funktion wird zum Bestimmen der obersten sichtbaren Zeile in einem Bearbeitungssteuerelement.  
  
```  
int GetFirstVisibleLine() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index von der obersten sichtbaren Zeile. Für einzeilige Bearbeitungssteuerelemente ist der Rückgabewert 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]  
  
##  <a name="gethandle"></a>  CEdit::GetHandle  
 Mit dieser Funktion wird zum Abrufen eines Handles für ein Bearbeitungssteuerelement für mehrzeiligen derzeit belegte Speicherplatz.  
  
```  
HLOCAL GetHandle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein lokaler Speicher-Handle, das den Puffer, der den Inhalt des Bearbeitungssteuerelements identifiziert. Wenn ein Fehler auftritt, z. B. das Senden der Nachricht an eine einzeilige Bearbeitungssteuerelement, ist der Rückgabewert 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Handle ist ein Handle für die lokalen Speicher und kann verwendet werden, mithilfe einer der **lokale** Windows-Memory-Funktionen, die einen lokalen Speicher akzeptieren zu behandeln, als Parameter.  
  
 **GetHandle** nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet wird.  
  
 Rufen Sie **GetHandle** für ein Bearbeitungssteuerelement für mehrzeiligen in einem Dialogfeld nur, wenn das Dialogfeld erstellt wurde, mit der **DS_LOCALEDIT** formatieren-Flag festgelegt. Wenn die **DS_LOCALEDIT** Stil nicht festgelegt ist, Sie erhalten weiterhin einen Wert ungleich NULL, aber Sie werden nicht in der Lage, den zurückgegebenen Wert verwenden.  
  
> [!NOTE]
> **GetHandle** funktioniert nicht mit Windows 95-und Windows 98. Beim Aufrufen **GetHandle** in Windows 95-und Windows 98, wird zurückgegeben, **NULL**. **GetHandle** funktioniert wie beschrieben unter Windows NT, Version 3.51 und höher.  
  
 Weitere Informationen finden Sie unter [EM_GETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761576) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]  
  
##  <a name="gethighlight"></a>  CEdit::GetHighlight  
 Ruft die Indizes der das erste und letzten Zeichen in einem Bereich von Text, der in der aktuellen Edit-Steuerelement hervorgehoben ist.  
  
```  
BOOL GetHighlight(
    int* pichStart,   
    int* pichEnd) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `pichStart`|Nullbasierte Index des ersten Zeichens in den Bereich der Text, der hervorgehoben ist.|  
|[out] `pichEnd`|Nullbasierte Index des letzten Zeichens in den Bereich der Text, der hervorgehoben ist.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [EM_GETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761578) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getlimittext"></a>  CEdit::GetLimitText  
 Rufen Sie diese Memberfunktion zum Abrufen des Text-Grenzwert für diesen `CEdit` Objekt.  
  
```  
UINT GetLimitText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Text Grenzwert in Bytes, der für diesen `CEdit` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Text-Grenzwert ist die Höchstmenge des Textes in Bytes, der das Bearbeitungssteuerelement annehmen kann.  
  
> [!NOTE]
>  Diese Memberfunktion ist verfügbar ab Windows 95 und Windows NT 4.0.  
  
 Weitere Informationen finden Sie unter [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]  
  
##  <a name="getline"></a>  CEdit::GetLine  
 Mit dieser Funktion wird zum Abrufen einer Zeile des Texts aus einem Bearbeitungssteuerelement und platziert es in `lpszBuffer`.  
  
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
 Gibt die Zeilennummer, Abrufen aus einer mehrzeiligen Bearbeitungssteuerelements. Zeilennummern sind nullbasiert. der Wert 0 gibt die erste Zeile an. Dieser Parameter wird von einem einzeiligen Edit-Steuerelement ignoriert.  
  
 `lpszBuffer`  
 Verweist auf den Puffer, der eine Kopie der Zeile empfängt. Das erste Wort des Puffers muss die maximale Anzahl von Zeichen angeben, die in den Puffer kopiert werden können.  
  
 `nMaxLength`  
 Gibt die maximale Anzahl von Bytes, die in den Puffer kopiert werden können. `GetLine` Dieser Wert in das erste Wort platziert `lpszBuffer` vor dem Aufruf von Windows.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bytes, die tatsächlich kopiert. Der Rückgabewert ist 0, wenn die Nummer der Zeile, wird angegeben `nIndex` ist größer als die Anzahl der Zeilen im Bearbeitungssteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Der kopierte Zeile enthält einen Null-Abschlusszeichen nicht.  
  
 Weitere Informationen finden Sie unter [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>  CEdit::GetLineCount  
 Mit dieser Funktion wird zum Abrufen der Anzahl der Zeilen in einem mehrzeiligen Edit-Steuerelement.  
  
```  
int GetLineCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die mit der Anzahl von Zeilen in der mehrzeiligen Bearbeitungssteuerelements an. Wenn das Bearbeitungssteuerelement kein Text eingegeben wurde, ist der Rückgabewert 1.  
  
### <a name="remarks"></a>Hinweise  
 `GetLineCount` Mehrzeilige Bearbeitungssteuerelemente wird nur verarbeitet.  
  
 Weitere Informationen finden Sie unter [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]  
  
##  <a name="getmargins"></a>  CEdit::GetMargins  
 Rufen Sie diese Memberfunktion zum Abrufen von der linken und rechten Rand des Bearbeitungssteuerelements.  
  
```  
DWORD GetMargins() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite des linken Rands in das niederwertige **WORD** und die Breite des rechten Rands in die höherwertigen **WORD**.  
  
### <a name="remarks"></a>Hinweise  
 Ränder werden in Pixel gemessen.  
  
> [!NOTE]
>  Diese Memberfunktion ist verfügbar ab Windows 95 und Windows NT 4.0.  
  
 Weitere Informationen finden Sie unter [EM_GETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761590) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="getmodify"></a>  CEdit::GetModify  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Inhalt des Edit-Steuerelements geändert wurden.  
  
```  
BOOL GetModify() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Inhalt des Bearbeitungssteuerelements geändert wurden; 0, wenn sie verblieben sind, wurden nicht geändert.  
  
### <a name="remarks"></a>Hinweise  
 Windows verwaltet ein internes Flag gibt an, ob der Inhalt des Bearbeitungssteuerelements geändert wurde. Dieses Flag wird gelöscht, wenn das Bearbeitungssteuerelement erstellt wird, und möglicherweise auch, durch den Aufruf gelöscht werden der [SetModify](#setmodify) Memberfunktion.  
  
 Weitere Informationen finden Sie unter [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]  
  
##  <a name="getpasswordchar"></a>  CEdit::GetPasswordChar  
 Rufen Sie diese Funktion, um das Kennwortzeichen abgerufen werden, das in ein Bearbeitungssteuerelement angezeigt wird, wenn der Benutzer Text eingibt.  
  
```  
TCHAR GetPasswordChar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Zeichen, statt das Zeichen angezeigt werden, die der Benutzer eingegeben. Der Rückgabewert ist `NULL` Wenn kein Kennwortzeichen vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Erstellung der Edit-Steuerelement mit dem **ES_PASSWORD** Stil, die DLL, die das Steuerelement unterstützt bestimmt das standardmäßige Kennwortzeichen. Das Manifest oder die [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) Methode bestimmt, welche die DLL unterstützt das Steuerelement zum Bearbeiten. Wenn "User32.dll" der Edit-Steuerelement unterstützt, wird das standardmäßige Kennwortzeichen Sternchen ("*", U + 002A). Wenn comctl32.dll, Version 6 der Edit-Steuerelement unterstützt, ist das Standardzeichen SCHWARZER Kreis ('●', U + 25CF). Weitere Informationen zu der DLL und Version unterstützt die Standardsteuerelemente finden Sie unter [Shell und allgemeine Steuerelemente Versionen](http://msdn.microsoft.com/library/windows/desktop/bb776779).  
  
 Diese Methode sendet die [EM_GETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761594) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]  
  
##  <a name="getrect"></a>  CEdit::GetRect  
 Rufen Sie diese Funktion, um die Formatierung Rechteck von einem Bearbeitungssteuerelement abzurufen.  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf die `RECT` -Struktur, die die Formatierung Rechteck empfängt.  
  
### <a name="remarks"></a>Hinweise  
 Die Formatierung Rechteck handelt es sich um die begrenzenden Rechteck des Texts, der unabhängig von der Größe des Fensters bearbeiten-Steuerelement ist.  
  
 Die Formatierung Rechteck eines mehrzeiligen Bearbeitungssteuerelements kann geändert werden, durch die [SetRect](#setrect) und [SetRectNP](#setrectnp) Memberfunktionen.  
  
 Weitere Informationen finden Sie unter [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::LimitText](#limittext).  
  
##  <a name="getsel"></a>  CEdit::GetSel  
 Mit dieser Funktion wird zum Abrufen von Start- und Endzeichen der aktuellen Auswahl (sofern vorhanden) in ein Bearbeitungssteuerelement über den Rückgabewert oder Parameter.  
  
```  
DWORD GetSel() const;  
  
void GetSel(
    int& nStartChar,  
    int& nEndChar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nStartChar`  
 Verweis auf eine ganze Zahl, die die Position des ersten Zeichens in der aktuellen Auswahl erhalten.  
  
 `nEndChar`  
 Verweis auf eine ganze Zahl, die die Position des ersten Zeichens nicht ausgewählten nach dem Ende der aktuellen Auswahl erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Version, die gibt eine `DWORD` gibt einen Wert, der die Anfangsposition in das niederwertige Wort und die Position des ersten Zeichens nicht ausgewählten nach dem Ende der Auswahl in das höherwertige Wort enthält.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_GETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761598) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]  
  
##  <a name="hideballoontip"></a>  CEdit::HideBalloonTip  
 Blendet alle SprechblasenInfo Edit-Steuerelement für die aktuelle zugeordnet.  
  
```  
BOOL HideBalloonTip();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sendet die [EM_HIDEBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761604) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="limittext"></a>  CEdit::LimitText  
 Rufen Sie diese Funktion, um die Länge des Texts zu beschränken, die der Benutzer ein Bearbeitungssteuerelement eingeben kann.  
  
```  
void LimitText(int nChars = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nChars`  
 Gibt die Länge (in Bytes) des Texts, der der Benutzer eingeben kann. Wenn dieser Parameter 0 ist, auf die Textlänge festgelegt **UINT_MAX** Bytes. Dies ist das Standardverhalten.  
  
### <a name="remarks"></a>Hinweise  
 Änderungen am Grenzwert der Text wird nur den Text, den der Benutzer eingeben kann, eingeschränkt. Er wirkt sich nicht auf einen beschreibenden Text ein bereits in das Bearbeitungssteuerelement und beeinträchtigt die Länge des Texts in das Bearbeitungssteuerelement durch kopiert die [SetWindowText](cwnd-class.md#setwindowtext) Memberfunktion in `CWnd`. Wenn eine Anwendung verwendet die `SetWindowText` Funktion zum Platzieren von Text in ein Bearbeitungssteuerelement als im Aufruf angegeben ist `LimitText`, der Benutzer kann den Text im Bearbeitungssteuerelement löschen. Jedoch der Grenzwert Text wird verhindert, dass den Benutzer den vorhandenen Text durch neuen Text ersetzen, führt dazu, dass den Text, der unterhalb des Limits Text fallen, sofern nicht die aktuelle Auswahl zu löschen.  
  
> [!NOTE]
>  In Win32 (Windows NT und Windows 95-und Windows 98) [SetLimitText](#setlimittext) ersetzt diese Funktion.  
  
 Weitere Informationen finden Sie unter [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]  
  
##  <a name="linefromchar"></a>  CEdit::LineFromChar  
 Mit dieser Funktion wird die Zeilennummer der Zeile abgerufen, die den angegebenen Zeichenindex enthält.  
  
```  
int LineFromChar(int nIndex = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Den nullbasierte Indexwert für das gewünschte Zeichen im Text des Bearbeitungssteuerelements enthält, oder-1 enthält. Wenn `nIndex` ist-1, gibt die aktuelle Zeile, d. h. die Zeile, die den Textcursor enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die nullbasierte Zeilennummer der Zeile mit der Zeichenindex gemäß `nIndex`. Wenn `nIndex` ist-1. die Zahl der Zeile, die das erste Zeichen der Auswahl zurückgegeben. Wenn keine Auswahl vorhanden ist, wird die aktuelle Zeilennummer zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Ein Zeichenindex ist die Anzahl der Zeichen vom Anfang des Bearbeitungssteuerelements an.  
  
 Diese Memberfunktion wird nur von mehrzeiligen Edit-Steuerelemente.  
  
 Weitere Informationen finden Sie unter [EM_LINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761609) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]  
  
##  <a name="lineindex"></a>  CEdit::LineIndex  
 Mit dieser Funktion wird zum Abrufen des Zeichenindex einer Zeile in einem mehrzeiligen Edit-Steuerelement.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nLine`  
 Den Indexwert für die gewünschte Position im Text des Bearbeitungssteuerelements enthält, oder-1 enthält. Wenn `nLine` ist-1, gibt die aktuelle Zeile, d. h. die Zeile, die den Textcursor enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeichenindex der Zeile im angegebenen `nLine` oder -1, wenn die angegebene Zeilennummer größer als die Anzahl der Zeilen in das Bearbeitungssteuerelement ist.  
  
### <a name="remarks"></a>Hinweise  
 Der Zeichenindex ist die Anzahl der Zeichen vom Anfang des Bearbeitungssteuerelements in die angegebene Zeile.  
  
 Diese Memberfunktion wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 Weitere Informationen finden Sie unter [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]  
  
##  <a name="linelength"></a>  CEdit::LineLength  
 Ruft die Länge der Zeile in einem Bearbeitungssteuerelement ab.  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nLine`  
 Der nullbasierte Index von einem Zeichen in der Zeile, deren Länge abgerufen werden sollen. Der Standardwert ist -1.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist für einzeilige Bearbeitungssteuerelemente, die Länge `TCHAR`s, der den Text im Bearbeitungssteuerelement.  
  
 Der Rückgabewert ist die Länge für mehrzeilige Bearbeitungssteuerelemente `TCHAR`s, der die angegebene Zeile die `nLine` Parameter. Für [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] Text, beträgt die Anzahl der Bytes in der Zeile; für Unicode-Text, beträgt die Anzahl der Zeichen in der Zeile. Die Länge schließt nicht die Zeichen Wagenrücklauf am Ende der Zeile.  
  
 Wenn die `nLine` Parameter ist größer als die Anzahl der Zeichen im Steuerelement, der Rückgabewert ist 0 (null).  
  
 Wenn die `nLine` Parameter ist-1, der Rückgabewert ist die Anzahl der nicht ausgewählte Zeichen in den Zeilen, die ausgewählten Zeichen enthalten. Wenn die Auswahl aus dem vierten Zeichen des zeilenweise Zeichen vom Ende der nächsten Zeile erweitert wird, ist der Rückgabewert z. B. 10. D. h. Zeichen drei auf der ersten Zeile und sieben am nächsten.  
  
 Weitere Informationen zu den `TCHAR` finden Sie unter der `TCHAR` Zeile in der Tabelle in [Windows Data Types](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode unterstützt die [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::LineIndex](#lineindex).  
  
##  <a name="linescroll"></a>  CEdit::LineScroll  
 Rufen Sie diese Funktion, um den Text eines mehrzeiligen Bearbeitungssteuerelements scrollen.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nLines`  
 Gibt die Anzahl der Zeilen vertikaler Bildlauf durchgeführt wird.  
  
 `nChars`  
 Gibt die Anzahl von Zeichenpositionen einen horizontalen Bildlauf durchführen. Dieser Wert wird ignoriert, wenn das Bearbeitungssteuerelement entweder verfügt die **ES_RIGHT** oder **ES_CENTER** Stil.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 Das Bearbeitungssteuerelement Bildlauf vertikal nicht hinter die letzte Zeile des Texts im Bearbeitungssteuerelement. Wenn plus die Anzahl der Zeilen, die gemäß der aktuellen Zeile `nLines` überschreitet die Gesamtanzahl der Zeilen im Bearbeitungssteuerelement, der Wert wird angepasst, damit die letzte Zeile des Bearbeitungssteuerelements an den Anfang der Edit-Steuerelement Fenster ein Bildlauf durchgeführt wird.  
  
 `LineScroll` kann verwendet werden, einen horizontalen Bildlauf hinter dem letzten Zeichen, der eine beliebige Zeile durchführen.  
  
 Weitere Informationen finden Sie unter [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::GetFirstVisibleLine](#getfirstvisibleline).  
  
##  <a name="paste"></a>  CEdit::Paste  
 Mit dieser Funktion wird zum Einfügen von Daten aus der Zwischenablage in die `CEdit` an der Einfügemarke.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Hinweise  
 Daten werden nur dann, wenn Daten in die Zwischenablage enthält, eingefügt **HIERSVR** Format.  
  
 Weitere Informationen finden Sie unter [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]  
  
##  <a name="posfromchar"></a>  CEdit::PosFromChar  
 Mit dieser Funktion können die Position (linke obere Ecke) eines angegebenen Zeichens in dieser abrufen `CEdit` Objekt.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nChar`  
 Der nullbasierte Index des angegebenen Zeichens.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Koordinaten der linken oberen Ecke des durch angegebene Zeichen `nChar`.  
  
### <a name="remarks"></a>Hinweise  
 Das Zeichen wird durch die Vergabe ihres nullbasierten Indexwerts angegeben. Wenn `nChar` ist größer als der Index des letzten Zeichens in dieser `CEdit` -Objekt, der Rückgabewert gibt die Koordinaten der Position des Zeichens hinter dem letzten Zeichen in dieser `CEdit` Objekt.  
  
> [!NOTE]
>  Diese Memberfunktion ist verfügbar ab Windows 95 und Windows NT 4.0.  
  
 Weitere Informationen finden Sie unter [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::LineFromChar](#linefromchar).  
  
##  <a name="replacesel"></a>  CEdit::ReplaceSel  
 Mit dieser Funktion können Sie die aktuelle Auswahl in einem Bearbeitungssteuerelement durch den angegebenen Text ersetzen `lpszNewText`.  
  
```  
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszNewText`  
 Verweist auf eine Null-terminierte Zeichenfolge, die den Ersetzungstext enthält.  
  
 `bCanUndo`  
 Um anzugeben, dass diese Funktion rückgängig gemacht werden kann, legen Sie den Wert dieses Parameters auf **"true"** . Der Standardwert ist **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Wird nur einen Teil des Texts in einem Bearbeitungssteuerelement ersetzt. Wenn Sie den gesamten Text ersetzen möchten, verwenden Sie die [CWnd::SetWindowText](cwnd-class.md#setwindowtext) Memberfunktion.  
  
 Wenn keine aktuelle Auswahl vorhanden ist, wird der Ersetzungstext an der aktuellen Cursorposition eingefügt.  
  
 Weitere Informationen finden Sie unter [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::LineIndex](#lineindex).  
  
##  <a name="setcuebanner"></a>  CEdit::SetCueBanner  
 Legt den Text, der als den Cue Text angezeigt wird oder Tipp, in eine Bearbeitung steuern, wenn das Steuerelement leer ist.  
  
```  
BOOL SetCueBanner(LPCWSTR lpszText);

 
BOOL SetCueBanner(
    LPCWSTR lpszText,   
    BOOL fDrawWhenFocused = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszText`  
 Ein Zeiger auf eine Zeichenfolge, die enthält den Hinweis im Bearbeitungssteuerelement angezeigt.  
  
 [in] `fDrawWhenFocused`  
 Wenn `false`, das hinweisbanner wird nicht gezeichnet werden, wenn der Benutzer in der Edit-Steuerelement klickt und das Steuerelement den Fokus erhält.  
  
 Wenn `true`, das hinweisbanner gezeichnet wird, selbst wenn das Steuerelement den Fokus besitzt. Das hinweisbanner verschwindet, wenn der Benutzer beginnt, geben Sie in das Steuerelement.  
  
 Der Standardwert ist `false`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn die Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [EM_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761639) Nachricht, die im Windows SDK beschrieben wird. Weitere Informationen finden Sie unter der [Edit_SetCueBannerTextFocused](http://msdn.microsoft.com/library/windows/desktop/bb761703) Makro.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die [CEdit::SetCueBanner](#setcuebanner) Methode.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]  
  
##  <a name="sethandle"></a>  CEdit::SetHandle  
 Rufen Sie diese Funktion, um das Handle in den lokalen Speicher festzulegen, die von einer mehrzeiligen Bearbeitungssteuerelements verwendet wird.  
  
```  
void SetHandle(HLOCAL hBuffer);
```  
  
### <a name="parameters"></a>Parameter  
 *hBuffer*  
 Enthält ein Handle für den lokalen Speicher an. Dieses Handle muss durch einen vorherigen Aufruf erstellt wurden die [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) Windows-Funktion verwendet die **LMEM_MOVEABLE** Flag. Der Arbeitsspeicher wird davon ausgegangen, dass eine Null-terminierte Zeichenfolge enthalten. Wenn dies nicht der Fall ist, sollte das erste Byte des belegten Speichers auf 0 festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Bearbeitungssteuerelement verwendet dann diesen Puffer zum Speichern des aktuell angezeigten Texts anstatt einen eigenen Puffer zuzuordnen.  
  
 Diese Memberfunktion wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 Bevor eine Anwendung ein neues Speicherhandle festlegt, verwenden sie die [GetHandle](#gethandle) Memberfunktion versucht, das Handle zu der aktuellen Arbeitsspeicherpuffer abrufen und Freigeben von Arbeitsspeicher verwenden die **LocalAlloc** Windows-Funktion.  
  
 `SetHandle` Löscht den Rückgängigpuffer (die [CanUndo](#canundo) Member-Funktion gibt dann 0) und das Flag für die interne Änderung (die [GetModify](#getmodify) dann Member-Funktion gibt 0 zurück). Fenster bearbeiten-Steuerelement neu gezeichnet wird.  
  
 Sie können diese Memberfunktion in einer mehrzeiligen Edit-Steuerelement in einem Dialogfeld verwenden, nur, wenn Sie das Dialogfeld mit erstellt haben die **DS_LOCALEDIT** formatieren-Flag festgelegt.  
  
> [!NOTE]
> **GetHandle** funktioniert nicht mit Windows 95-und Windows 98. Beim Aufrufen **GetHandle** in Windows 95-und Windows 98, wird zurückgegeben, **NULL**. **GetHandle** funktioniert wie beschrieben unter Windows NT, Version 3.51 und höher.  
  
 Weitere Informationen finden Sie unter [EM_SETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761641), [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), und [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366730) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]  
  
##  <a name="sethighlight"></a>  CEdit::SetHighlight  
 Bearbeitungssteuerelement für kennzeichnet ein Textbereich, der in der aktuellen angezeigt wird.  
  
```  
void SetHighlight(
    int ichStart,   
    int ichEnd);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `ichStart`|Nullbasierte Index des ersten Zeichens in den Bereich von Text zu markieren.|  
|[in] `ichEnd`|Nullbasierte Index des letzten Zeichens in den Bereich von Text zu markieren.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [EM_SETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761643) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="setlimittext"></a>  CEdit::SetLimitText  
 Rufen Sie diese Memberfunktion zum Festlegen des Text-Grenzwert für diesen `CEdit` Objekt.  
  
```  
void SetLimitText(UINT nMax);
```  
  
### <a name="parameters"></a>Parameter  
 `nMax`  
 Der neue Text Grenzwert in Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Der Text-Grenzwert ist die Höchstmenge des Textes in Zeichen, d. h., die das Bearbeitungssteuerelement akzeptieren kann.  
  
 Änderungen am Grenzwert der Text wird nur den Text, den der Benutzer eingeben kann, eingeschränkt. Er wirkt sich nicht auf einen beschreibenden Text ein bereits in das Bearbeitungssteuerelement und beeinträchtigt die Länge des Texts in das Bearbeitungssteuerelement durch kopiert die [SetWindowText](cwnd-class.md#setwindowtext) Memberfunktion in `CWnd`. Wenn eine Anwendung verwendet die `SetWindowText` Funktion zum Platzieren von Text in ein Bearbeitungssteuerelement als im Aufruf angegeben ist `LimitText`, der Benutzer kann den Text im Bearbeitungssteuerelement löschen. Jedoch der Grenzwert Text wird verhindert, dass den Benutzer den vorhandenen Text durch neuen Text ersetzen, führt dazu, dass den Text, der unterhalb des Limits Text fallen, sofern nicht die aktuelle Auswahl zu löschen.  
  
 Diese Funktion ersetzt [LimitText](#limittext) in Win32.  
  
 Weitere Informationen finden Sie unter [EM_SETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761647) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmargins"></a>  CEdit::SetMargins  
 Rufen Sie diese Methode zum Festlegen der linken und rechten Rand des Bearbeitungssteuerelements.  
  
```  
void SetMargins(
    UINT nLeft,  
    UINT nRight);
```  
  
### <a name="parameters"></a>Parameter  
 *nLeft*  
 Die Breite des neuen linken Rand in Pixel.  
  
 *nRight*  
 Die Breite des der neuen rechten Rand in Pixel.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Memberfunktion ist verfügbar ab Windows 95 und Windows NT 4.0.  
  
 Weitere Informationen finden Sie unter [EM_SETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761649) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmodify"></a>  CEdit::SetModify  
 Mit dieser Funktion wird zum Aktivieren bzw. deaktivieren das Änderungsflag für ein Bearbeitungssteuerelement.  
  
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
  Siehe das Beispiel für [CEdit::GetModify](#getmodify).  
  
##  <a name="setpasswordchar"></a>  CEdit::SetPasswordChar  
 Mit dieser Funktion wird zum Festlegen oder entfernen ein Kennwort ein Zeichen in ein Bearbeitungssteuerelement angezeigt, wenn der Benutzer Text eingibt.  
  
```  
void SetPasswordChar(TCHAR ch);
```  
  
### <a name="parameters"></a>Parameter  
 *ch*  
 Gibt das Zeichen, die anstelle der vom Benutzer eingegebenen Zeichen angezeigt werden. Wenn *ch* gleich 0 ist, die vom Benutzer eingegebenen Zeichen angezeigt werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Kennwortzeichen festgelegt ist, wird dieses Zeichen angezeigt, für jedes vom Benutzer eingegebenen Zeichen.  
  
 Diese Memberfunktion wirkt sich nicht auf einen mehrzeiligen Steuerelement zu bearbeiten.  
  
 Wenn die `SetPasswordChar` Memberfunktion aufgerufen wird, `CEdit` wird neu gezeichnet werden alle sichtbar, mit dem durch angegebene Zeichen *ch*.  
  
 Wenn das Bearbeitungssteuerelement erstellt wird, mit der [ES_PASSWORD](styles-used-by-mfc.md#edit-styles) Format, das standardmäßige Kennwortzeichen auf ein Sternchen festgelegt ist ( **\***). Dieses Format wird entfernt, wenn `SetPasswordChar` aufgerufen wird und *ch* auf 0 festgelegt.  
  
 Weitere Informationen finden Sie unter [EM_SETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761653) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]  
  
##  <a name="setreadonly"></a>  CEdit::SetReadOnly  
 Ruft diese Funktion zum Festlegen des schreibgeschützten Status eines Bearbeitungssteuerelements.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bReadOnly`  
 Gibt an, ob festlegen oder entfernen den schreibgeschützten Status des Edit-Steuerelements. Der Wert **"true"** legt den Zustand auf schreibgeschützt, der Wert **"false"** legt den Zustand auf Lese-/Schreibzugriff.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich ist, oder 0, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Die aktuelle Einstellung verwendbaren durch Testen der [ES_READONLY](styles-used-by-mfc.md#edit-styles) -Flag in der Rückgabewert der [CWnd::GetStyle](cwnd-class.md#getstyle).  
  
 Weitere Informationen finden Sie unter [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]  
  
##  <a name="setrect"></a>  CEdit::SetRect  
 Mit dieser Funktion wird zum Festlegen der Dimensionen eines Rechtecks, das mit den angegebenen Koordinaten.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf die `RECT` Struktur oder `CRect` Objekt, das die Abmessungen des Rechtecks Formatierung angibt.  
  
### <a name="remarks"></a>Hinweise  
 Bei diesem Member wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 Verwendung `SetRect` festzulegende die Formatierung Rechteck einer mehrzeiligen Bearbeitungssteuerelements. Die Formatierung Rechteck handelt es sich um die begrenzenden Rechteck des Texts, der unabhängig von der Größe des Fensters bearbeiten-Steuerelement ist. Wenn das Bearbeitungssteuerelement zuerst erstellt wird, entspricht die Formatierung Rechteck Clientbereichs des Fensters bearbeiten-Steuerelement. Mithilfe der `SetRect` Member-Funktion, eine Anwendung kann legen Sie für die Formatierung Rechteck größer oder kleiner als das Bearbeitungssteuerelement Fenster.  
  
 Wenn das Bearbeitungssteuerelement keine Bildlaufleiste enthält, wird Text abgeschnitten nicht umbrochen, erfolgt die Formatierung Rechteck größer als das Fenster. Wenn das Steuerelement zum Bearbeiten ein Rahmens enthält, wird die Formatierung Rechteck von der Größe des Rahmens reduziert. Wenn Sie das Rechteck zurückgegebenes Anpassen der `GetRect` Memberfunktion ist, müssen Sie die Größe des Rahmens entfernen, bevor Sie das Rechteck übergeben `SetRect`.  
  
 Wenn `SetRect` aufgerufen wird, wird das Steuerelement zum Bearbeiten des Texts auch neu formatiert und erneut angezeigt.  
  
 Weitere Informationen finden Sie unter [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]  
  
##  <a name="setrectnp"></a>  CEdit::SetRectNP  
 Mit dieser Funktion können Sie Formatierung Rechtecks eines mehrzeiligen Bearbeitungssteuerelements festgelegt.  
  
```  
void SetRectNP(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `RECT` Struktur oder `CRect` Objekt, das die Abmessungen des Rechtecks angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Formatierung Rechteck handelt es sich um die begrenzenden Rechteck des Texts, der unabhängig von der Größe des Fensters bearbeiten-Steuerelement ist.  
  
 `SetRectNP` ist identisch mit der `SetRect` Memberfunktion mit dem Unterschied, dass das Bearbeitungssteuerelement Fenster nicht neu gezeichnet wird.  
  
 Wenn das Bearbeitungssteuerelement zuerst erstellt wird, entspricht die Formatierung Rechteck Clientbereichs des Fensters bearbeiten-Steuerelement. Durch Aufrufen der `SetRectNP` Member-Funktion, eine Anwendung kann legen Sie für die Formatierung Rechteck größer oder kleiner als das Bearbeitungssteuerelement Fenster.  
  
 Wenn das Bearbeitungssteuerelement keine Bildlaufleiste enthält, wird Text abgeschnitten nicht umbrochen, erfolgt die Formatierung Rechteck größer als das Fenster.  
  
 Bei diesem Member wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 Weitere Informationen finden Sie unter [EM_SETRECTNP](http://msdn.microsoft.com/library/windows/desktop/bb761659) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::SetRect](#setrect).  
  
##  <a name="setsel"></a>  CEdit::SetSel  
 Rufen Sie diese Funktion, um einen Bereich von Zeichen in ein Bearbeitungssteuerelement auszuwählen.  
  
```  
void SetSel(
    DWORD dwSelection,  
    BOOL bNoScroll = FALSE);

 
void SetSel(
    int nStartChar,  
    int nEndChar,  
    BOOL bNoScroll = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *dwSelection*  
 Gibt die Anfangsposition in das niederwertige Wort und die Endposition in das höherwertige Wort. Wenn das niederwertige Wort 0 ist, und das höherwertige Wort-1 ist, ist gesamten Text im Bearbeitungssteuerelement ausgewählt. Wenn das niederwertige Wort-1 ist, wird keine aktuelle Auswahl entfernt.  
  
 *bNoScroll*  
 Gibt an, ob die Einfügemarke in die Ansicht gescrollt werden soll. Wenn **"false"**, Einfügemarke angezeigt wird. Wenn **"true"**, die Einfügemarke wird nicht angezeigt.  
  
 `nStartChar`  
 Gibt die Startposition. Wenn `nStartChar` ist 0 und `nEndChar` ist-1 und alle in der Text im Bearbeitungssteuerelement ausgewählt ist. Wenn `nStartChar` ist-1 und keine aktuelle Auswahl entfernt wird.  
  
 `nEndChar`  
 Gibt die Endposition.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_SETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761661) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::GetSel](#getsel).  
  
##  <a name="settabstops"></a>  CEdit::SetTabStops  
 Mit dieser Funktion wird zum Festlegen von Tabstopps in einem mehrzeiligen Edit-Steuerelement.  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>Parameter  
 `cxEachStop`  
 Gibt an, dass Tabstopps zu jedem `cxEachStop` Dialogeinheiten.  
  
 `nTabStops`  
 Gibt die Anzahl der in enthaltenen Tabstopps `rgTabStops`. Diese Zahl muss größer als 1 sein.  
  
 `rgTabStops`  
 Verweist auf ein Array von Ganzzahlen ohne Vorzeichen, die die Registerkarte angeben, die in Dialogeinheiten wird beendet. Eine Dialogeinheit ist einen horizontalen oder vertikalen Abstand an. Eine horizontale Dialogeinheit ein Viertel der aktuellen Dialogfeld Basis Breite Einheit entspricht, und 1 vertikale Dialogeinheit entspricht einem Achtel des aktuellen Dialogfeld Basis Höhe Komponententest. Die Basis Dialogeinheiten werden basierend auf die Höhe und Breite der aktuellen Systemschriftart berechnet. Die **GetDialogBaseUnits** Windows-Funktion gibt den aktuellen Dialogfeld Basis Einheiten in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Registerkarten festgelegt wurden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Text in ein Bearbeitungssteuerelement für mehrzeiligen kopiert werden, verursachen alle Tabstoppzeichen im Text Leerzeichen bis zum nächsten Tabstopp generiert werden soll.  
  
 Rufen Sie die parameterlose Version von dieser Memberfunktion, um die Standardgröße des 32 Dialogeinheiten Tabstopps festzulegen. Tabstopps auf einer anderen Größe als 32 festlegen möchten, rufen Sie die Version mit der `cxEachStop` Parameter. Um ein Array von Größen Tabstopps festzulegen, verwenden Sie die Version mit zwei Parametern aus.  
  
 Diese Memberfunktion wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 `SetTabStops` wird nicht automatisch das Bearbeitungsfenster neu gezeichnet werden. Wenn Sie die Tabstopps für den Text im Bearbeitungssteuerelement bereits ändern, rufen Sie [CWnd::InvalidateRect](cwnd-class.md#invalidaterect) Bearbeitungsfenster neu zeichnet.  
  
 Weitere Informationen finden Sie unter [EM_SETTABSTOPS](http://msdn.microsoft.com/library/windows/desktop/bb761663) und [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEditView::SetTabStops](ceditview-class.md#settabstops).  
  
##  <a name="showballoontip"></a>  CEdit::ShowBalloonTip  
 Zeigt eine SprechblasenInfo, die die aktuelle Edit-Steuerelement zugeordnet ist.  
  
```  
BOOL ShowBalloonTip(PEDITBALLOONTIP pEditBalloonTip);

 
BOOL ShowBalloonTip(
    LPCWSTR lpszTitle,   
    LPCWSTR lpszText,   
    INT ttiIcon = TTI_NONE);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pEditBalloonTip`|Zeiger auf eine [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) Struktur, die die SprechblasenInfo beschreibt.|  
|[in] `lpszTitle`|Ein Zeiger auf eine Unicodezeichenfolge, die den Titel der SprechblasenInfo enthält.|  
|[in] `lpszText`|Ein Zeiger auf eine Unicodezeichenfolge, die die Sprechblase Tipptext beinhaltet.|  
|[in] `ttiIcon`|Ein `INT` , der den Typ des Symbols die SprechblasenInfo zuzuordnende angibt. Der Standardwert ist `TTI_NONE`. Weitere Informationen finden Sie unter der `ttiIcon` Mitglied der [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) Struktur.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true` Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sendet die [EM_SHOWBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761668) Nachricht, die im Windows SDK beschrieben wird. Weitere Informationen finden Sie unter der [Edit_ShowBalloonTip](http://msdn.microsoft.com/library/windows/desktop/bb761707) Makro.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert eine Variable `m_cedit`, d. h. verwendet, um die aktuellen Edit-Steuerelement zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt eine SprechblasenInfo für ein Bearbeitungssteuerelement an. Die [CEdit::ShowBalloonTip](#showballoontip) Methode gibt ein QuickInfo-Text für Titel und Sprechblase an.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]  
  
##  <a name="undo"></a>  CEdit::Undo  
 Rufen Sie diese Funktion, um den letzten Bearbeitungssteuerelement Vorgang rückgängig zu machen.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Für eine einzeilige Edit-Steuerelement ist der Rückgabewert immer ungleich NULL. Der Rückgabewert ist ungleich NULL, wenn der Rückgängig-Vorgang erfolgreich ist, ist für ein Bearbeitungssteuerelement für mehrzeiligen oder 0, wenn der Rückgängig-Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Ein Rückgängig-Vorgang kann auch rückgängig gemacht werden. Sie können z. B. Wiederherstellen gelöschten Text mit dem ersten Aufruf **Rückgängig**. Solange keine Beteiligte Bearbeitungsvorgang vorhanden ist, können, entfernen Sie den Text erneut mit einem zweiten Aufruf von **Rückgängig**.  
  
 Weitere Informationen finden Sie unter [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CALCDRIV](../../visual-cpp-samples.md)   
 [MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](cwnd-class.md)   
 [CButton-Klasse](cbutton-class.md)   
 [CComboBox-Klasse](ccombobox-class.md)   
 [CListBox-Klasse](clistbox-class.md)   
 [CScrollBar-Klasse](cscrollbar-class.md)   
 [CStatic-Klasse](cstatic-class.md)   
 [CDialog-Klasse](cdialog-class.md)
