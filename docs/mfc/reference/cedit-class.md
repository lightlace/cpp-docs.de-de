---
title: CEdit Class
ms.date: 09/12/2018
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
ms.openlocfilehash: f18866dca3610db275c629bbb2ac885c21cbdcb8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455808"
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
|[CEdit::CanUndo](#canundo)|Bestimmt, ob ein bearbeiten-Steuerelement-Vorgang rückgängig gemacht werden kann.|
|[CEdit::CharFromPos](#charfrompos)|Ruft die Zeilen- und Indizes für das Zeichen, die am nächsten an eine angegebene Position ab.|
|[CEdit::Clear](#clear)|Löscht (deaktiviert) die aktuelle Auswahl (sofern vorhanden) in das Bearbeitungsfeld steuern.|
|[CEdit::Copy](#copy)|Kopiert die aktuelle Auswahl (sofern vorhanden) in das Bearbeitungssteuerelement im HIERSVR-Format in die Zwischenablage.|
|[CEdit::Create](#create)|Erstellt die Windows-Edit-Steuerelement, und fügt es der `CEdit` Objekt.|
|[CEdit::Cut](#cut)|Löscht (Schnitte) die aktuelle Auswahl (sofern vorhanden) in das Bearbeitungsfeld steuern und kopiert der gelöschte Text in die Zwischenablage in HIERSVR-format.|
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|Setzt (löscht) das Flag zum Rückgängigmachen der Bearbeitung Steuerelement zurück.|
|[CEdit::FmtLines](#fmtlines)|Legt die Einbeziehung von soft-Zeilenumbruchzeichen innerhalb eines mehrzeiligen Bearbeitungssteuerelements fest, aktivieren oder deaktivieren.|
|[CEdit::GetCueBanner](#getcuebanner)|Ruft den Text ab, der angezeigt wird, als der Texthinweis "oder" Tipp, in einem Bearbeitungssteuerelement, wenn das Steuerelement leer ist und keinen Fokus besitzt.|
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|Bestimmt die oberste sichtbare Zeile in einem Bearbeitungssteuerelement.|
|[CEdit::GetHandle](#gethandle)|Ruft ein Handle für den Arbeitsspeicher, der derzeit für ein Bearbeitungssteuerelement für mehrzeiligen zugeordnet ist.|
|[CEdit::GetHighlight](#gethighlight)|Ruft ab, die Indizes von der ersten und letzten Zeichen in einem Bereich von Text, der in das aktuelle Bearbeitungssteuerelement hervorgehoben wird.|
|[CEdit::GetLimitText](#getlimittext)|Ruft der maximale Größe des Texts dieser `CEdit` enthalten können.|
|[CEdit::GetLine](#getline)|Ruft eine Textzeile aus einem Bearbeitungssteuerelement ab.|
|[CEdit::GetLineCount](#getlinecount)|Ruft die Anzahl der Zeilen in einem mehrzeiligen Bearbeitungssteuerelement ab.|
|[CEdit::GetMargins](#getmargins)|Ruft den linken und rechten Rand für diese `CEdit`.|
|[CEdit::GetModify](#getmodify)|Bestimmt, ob der Inhalt von einem Bearbeitungssteuerelement geändert wurden.|
|[CEdit::GetPasswordChar](#getpasswordchar)|Ruft das Kennwort ein Zeichen in einem Bearbeitungssteuerelement angezeigt wird, wenn der Benutzer Text eingibt.|
|[CEdit::GetRect](#getrect)|Ruft die Formatierung Rechteck ein Edit-Steuerelement ab.|
|[CEdit::GetSel](#getsel)|Ruft die Positionen der erste und letzte Zeichen der aktuellen Auswahl in einem Bearbeitungssteuerelement ab.|
|[CEdit::HideBalloonTip](#hideballoontip)|Blendet alle das aktuelle Bearbeitungssteuerelement zugeordneten QuickInfo-Sprechblase an.|
|[CEdit::LimitText](#limittext)|Begrenzt die Länge des Texts, der der Benutzer in ein Bearbeitungssteuerelement eingeben kann.|
|[CEdit::LineFromChar](#linefromchar)|Ruft die Zeilennummer der Zeile, die den angegebenen Zeichenindex enthält.|
|[CEdit::LineIndex](#lineindex)|Ruft den Zeichenindex des einer Zeile eines mehrzeiligen Bearbeitungssteuerelements ab.|
|[CEdit::LineLength](#linelength)|Ruft die Länge einer Zeile in einem Bearbeitungssteuerelement ab.|
|[CEdit::LineScroll](#linescroll)|Scrollt den Text eines mehrzeiligen Bearbeitungssteuerelements an.|
|[CEdit::Paste](#paste)|Die Daten aus der Zwischenablage in das Bearbeitungssteuerelement an der aktuellen Cursorposition eingefügt. Daten werden eingefügt, nur, wenn die Zwischenablage Daten im HIERSVR Format enthält.|
|[CEdit::PosFromChar](#posfromchar)|Ruft die Koordinaten der oberen linken Ecke von einem angegebenen Zeichenindex ab.|
|[CEdit::ReplaceSel](#replacesel)|Ersetzt die aktuelle Auswahl in einem Bearbeitungssteuerelement mit dem angegebenen Text.|
|[CEdit::SetCueBanner](#setcuebanner)|Legt den Text, der angezeigt wird, als der Texthinweis "oder" Tipp, in einem Bearbeitungssteuerelement, wenn das Steuerelement leer ist und keinen Fokus besitzt.|
|[CEdit::SetHandle](#sethandle)|Legt das Handle fest, auf den lokalen Speicher, der von einem mehrzeiligen Bearbeitungssteuerelements verwendet wird.|
|[CEdit::SetHighlight](#sethighlight)|Bearbeitungssteuerelement für Highlights ein Textbereich, der in der aktuellen angezeigt wird.|
|[CEdit::SetLimitText](#setlimittext)|Legt der maximale Größe des Texts dieser `CEdit` enthalten können.|
|[CEdit::SetMargins](#setmargins)|Legt den linken und rechten Rand für diesen `CEdit`.|
|[CEdit::SetModify](#setmodify)|Legt fest oder löscht das Flag "Änderungen" für eine Bearbeitungssteuerelement.|
|[CEdit::SetPasswordChar](#setpasswordchar)|Legt fest oder entfernt ein Kennwort ein Zeichen in einem Bearbeitungssteuerelement angezeigt wird, wenn der Benutzer Text eingibt.|
|[CEdit::SetReadOnly](#setreadonly)|Legt den schreibgeschützten Status ein Bearbeitungssteuerelement fest.|
|[CEdit::SetRect](#setrect)|Legt des Formatierungsrechtecks eines mehrzeiligen Bearbeitungssteuerelements fest, und aktualisiert das Steuerelement aus.|
|[CEdit::SetRectNP](#setrectnp)|Legt des Formatierungsrechtecks eines mehrzeiligen Bearbeitungssteuerelements ohne Neuzeichnen Fenster des Steuerelements fest.|
|[CEdit::SetSel](#setsel)|Wählt einen Bereich von Zeichen in einem Bearbeitungssteuerelement.|
|[CEdit::SetTabStops](#settabstops)|Legt die Tabstopps in einer mehrzeiligen Bearbeitungssteuerelements an.|
|[CEdit::ShowBalloonTip](#showballoontip)|Zeigt eine QuickInfo-Sprechblase, die das aktuelle Bearbeitungssteuerelement zugeordnet ist.|
|[CEdit::Undo](#undo)|Kehrt den letzten Vorgang für den bearbeiten-Steuerelement.|

## <a name="remarks"></a>Hinweise

Ein Bearbeitungssteuerelement ist ein rechteckiges untergeordnete Fenster in der der Benutzer Text eingeben kann.

Sie können ein Edit-Steuerelement aus einer Dialogfeldvorlage oder direkt in Ihrem Code erstellen. In beiden Fällen rufen Sie zunächst den Konstruktor `CEdit` zum Erstellen der `CEdit` Objekt aus, und rufen Sie dann die [erstellen](#create) Member-Funktion zum Erstellen der Windows-edit-Steuerelement, und fügen Sie ihn auf die `CEdit` Objekt.

Erstellung kann ein langwieriger Vorgang in einer Klasse abgeleitet sein `CEdit`. Schreiben Sie einen Konstruktor für die abgeleitete Klasse und rufen `Create` von innerhalb des Konstruktors.

`CEdit` erbt die wichtigsten Features von `CWnd`. Festlegen und Abrufen von Text aus einer `CEdit` -Objekts die `CWnd` Memberfunktionen [SetWindowText](cwnd-class.md#setwindowtext) und [GetWindowText](cwnd-class.md#getwindowtext), welche Set- oder Get den gesamten Inhalt der Bearbeitung steuern, auch wenn es ist ein mehrzeiliges Steuerelement. Textzeilen in ein mehrzeiliges Steuerelement werden durch Zeichenfolgen "\r\n" getrennt. Auch wenn ein Bearbeitungssteuerelement mehrzeilig ist, erhalten, und legen Sie Teil der Text des Steuerelements, durch Aufrufen der `CEdit` Memberfunktionen [GetLine](#getline), [Memberfunktion SetSel](#setsel), [Memberfunktion GetSel](#getsel), und [ ReplaceSel](#replacesel).

Wenn Sie Windows gesendete benachrichtigungsmeldungen von ein Bearbeitungssteuerelement zum übergeordneten behandeln möchten (in der Regel eine abgeleitete Klasse `CDialog`), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag "und"-Nachrichtenhandler-Memberfunktion hinzugefügt.

Jede Nachricht-Zuordnungseintrag weist folgende Form:

  **ON_**_Benachrichtigung_**(** _Id_**,** _MemberFxn_ **)**

wo `id` gibt die untergeordneten Fenster-ID des Edit-Steuerelements, das Senden der Benachrichtigung, und `memberFxn` ist der Name der übergeordneten Member-Funktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.

Funktionsprototyp des übergeordneten Elements lautet wie folgt aus:

**Afx_msg** "void" MemberFxn **();**

Es folgt eine Liste der möglichen Meldungszuordnungseinträge und eine Beschreibung der Fälle in denen sie das dem übergeordneten gesendet werden sollen:

- ON_EN_CHANGE der Benutzer hat eine Aktion ausgeführt, die Text in einem Bearbeitungssteuerelement geändert haben kann. Im Gegensatz zu der Benachrichtigung EN_UPDATE wird diese Benachrichtigung gesendet, nachdem Windows die Anzeige aktualisiert.

- ON_EN_ERRSPACE das Bearbeitungssteuerelement Speicherplatz nicht genügend um eine bestimmte Anforderung zu erfüllen.

- ON_EN_HSCROLL der Benutzer klickt auf die horizontale Schiebeleiste des Bearbeitungssteuerelements ein. Das übergeordnete Fenster wird benachrichtigt, bevor der Bildschirm aktualisiert wird.

- ON_EN_KILLFOCUS der Edit-Steuerelement verliert den Eingabefokus.

- ON_EN_MAXTEXT der aktuellen Einfügemarke hat die angegebene Anzahl von Zeichen für das Steuerelement zum Bearbeiten überschritten und wurde abgeschnitten. Auch gesendet, wenn ein Bearbeitungssteuerelement verfügt nicht über den ES_AUTOHSCROLL-Stil und die Anzahl der einzufügenden Zeichen die Breite des Bearbeitungssteuerelements übersteigt. Auch gesendet, wenn ein Bearbeitungssteuerelement verfügt nicht über den ES_AUTOVSCROLL-Stil und die Gesamtzahl der Zeilen, die durch eine texteinfügung zu einer der Höhe des Bearbeitungssteuerelements Überschreitung würde.

- ON_EN_SETFOCUS wird gesendet, wenn ein Edit-Steuerelement den Eingabefokus erhält.

- ON_EN_UPDATE geändert Anzeigetext der Edit-Steuerelements zu werden. Gesendet, nachdem das Steuerelement den Text formatiert hat, aber bevor sie den Text Bildschirmauflösung, sodass die Größe des Fensters geändert werden kann, bei Bedarf.

- ON_EN_VSCROLL der Benutzer klickt auf die vertikale Schiebeleiste ein Edit-Steuerelements. Das übergeordnete Fenster wird benachrichtigt, bevor der Bildschirm aktualisiert wird.

Bei der Erstellung einer `CEdit` Objekt in einem Dialogfeld der `CEdit` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.

Bei der Erstellung einer `CEdit` Objekt aus einer Ressource mithilfe des Dialog-Editors die `CEdit` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.

Bei der Erstellung einer `CEdit` Objekt innerhalb eines Zeitfensters, Sie müssen möglicherweise auch zerstören. Bei der Erstellung der `CEdit` Objekt im Stapel automatisch zerstört wird. Bei der Erstellung der `CEdit` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** edit-Steuerelement auf das Objekt, das es zerstört, wenn der Benutzer die Windows beendet. Wenn Sie im Arbeitsspeicher zuordnen der `CEdit` Objekt außer Kraft, indem die `CEdit` Destruktor, der Zuordnungen zu verwerfen.

So ändern Sie bestimmte Formate in einem Bearbeitungssteuerelement (z. B. ES_READONLY) müssen Sie bestimmte Nachrichten senden, auf das Steuerelement anstelle von [ModifyStyle](cwnd-class.md#modifystyle). Finden Sie unter [Bearbeiten der Stile von Listensteuerelementen](/windows/desktop/Controls/edit-control-styles) in das Windows SDK.

Weitere Informationen zu `CEdit`, finden Sie unter [Steuerelemente](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

`CEdit`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="canundo"></a>  CEdit::CanUndo

Rufen Sie diese Funktion, um zu bestimmen, ob die letzte Bearbeitung rückgängig rückgängig gemacht werden kann.

```
BOOL CanUndo() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der letzte Bearbeitungsvorgang durch einen Aufruf von rückgängig gemacht werden kann die `Undo` Memberfunktion; 0, wenn sie kann nicht rückgängig gemacht werden.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [EM_CANUNDO](/windows/desktop/Controls/em-canundo) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEdit::Undo](#undo).

##  <a name="cedit"></a>  CEdit::CEdit

Erstellt ein `CEdit`-Objekt.

```
CEdit();
```

### <a name="remarks"></a>Hinweise

Verwendung [erstellen](#create) zum Erstellen der Windows-edit-Steuerelement.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]

##  <a name="charfrompos"></a>  CEdit::CharFromPos

Mit dieser Funktion können Sie die nullbasierte Zeilennummer und die Zeichen Indizes des Zeichens am nächsten liegt der angegebene Punkt in diesem abrufen `CEdit` Steuerelement

```
int CharFromPos(CPoint pt) const;
```

### <a name="parameters"></a>Parameter

*pt*<br/>
Die Koordinaten eines Punkts in den Clientbereich dieses `CEdit` Objekt.

### <a name="return-value"></a>Rückgabewert

Der Zeichenindex in das niederwertige Wort, und der Zeilenindex in das höherwertige Wort.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Diese Memberfunktion wird ab, die mit Windows 95 und Windows NT 4.0 verfügbar.

Weitere Informationen finden Sie unter [EM_CHARFROMPOS](/windows/desktop/Controls/em-charfrompos) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]

##  <a name="clear"></a>  CEdit::Clear

Mit dieser Funktion können Sie (clear) die aktuelle Auswahl in das Bearbeitungssteuerelement (sofern vorhanden) löschen.

```
void Clear();
```

### <a name="remarks"></a>Hinweise

Das Löschen von ausgeführten `Clear` rückgängig gemacht werden kann, durch den Aufruf der [rückgängig machen](#undo) Member-Funktion.

Rufen Sie zum Löschen der aktuellen Auswahl, und fügen Sie den gelöschten Inhalt in die Zwischenablage kopieren, die [Ausschneiden](#cut) Member-Funktion.

Weitere Informationen finden Sie unter [WM_CLEAR](/windows/desktop/dataxchg/wm-clear) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]

##  <a name="copy"></a>  CEdit::Copy

Rufen Sie diese Funktion zum Kopieren der aktuellen Auswahl (sofern vorhanden) in das Bearbeitungssteuerelement im HIERSVR-Format in die Zwischenablage.

```
void Copy();
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [WM_COPY](/windows/desktop/dataxchg/wm-copy) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]

##  <a name="create"></a>  CEdit::Create

Erstellt die Windows-Edit-Steuerelement, und fügt es der `CEdit` Objekt.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parameter

*dwStyle*<br/>
Gibt das Steuerelement zum Bearbeiten des Stils an. Wenden Sie eine beliebige Kombination von [Bearbeiten von Stilen](styles-used-by-mfc.md#edit-styles) an das Steuerelement.

*Rect*<br/>
Gibt an, des Steuerelements zum Bearbeiten der Größe und Position. Kann eine `CRect` Objekt oder `RECT` Struktur.

*pParentWnd*<br/>
Gibt an, das Steuerelement zum Bearbeiten des übergeordneten Fensters (in der Regel eine `CDialog`). Es darf nicht NULL sein.

*nID*<br/>
Gibt die Edit-Steuerelement-ID an.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn die Initialisierung erfolgreich ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie erstellen eine `CEdit` Objekt in zwei Schritten. Rufen Sie zunächst die `CEdit` Konstruktor und rufen Sie dann `Create`, die das Steuerelement zum Bearbeiten von Windows erstellt, und fügt es der `CEdit` Objekt.

Wenn `Create` ausgeführt wird, handelt es sich bei Windows sendet die [WM_NCCREATE](/windows/desktop/winmsg/wm-nccreate), [WM_NCCALCSIZE](/windows/desktop/winmsg/wm-nccalcsize), [WM_CREATE](/windows/desktop/winmsg/wm-create), und [WM_GETMINMAXINFO](/windows/desktop/winmsg/wm-getminmaxinfo) die Nachrichten an das Steuerelement zum Bearbeiten.

Diese Nachrichten werden standardmäßig behandelt der [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate), und [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standardbehandlung für die Nachricht zu erweitern, leiten Sie eine Klasse von `CEdit`, hinzufügen eine meldungszuordnung an die neue Klasse und überschreiben Sie die oben genannten Meldungshandler-Memberfunktionen. Außer Kraft setzen `OnCreate`, z. B. für die erforderliche Initialisierung für die neue Klasse.

Übernehmen Sie das folgende [Window-Stile](styles-used-by-mfc.md#window-styles) an ein Bearbeitungssteuerelement.

- WS_CHILD immer

- WS_VISIBLE in der Regel

- WS_DISABLED selten

- WS_GROUP zum Gruppieren von Steuerelementen

- WS_TABSTOP-Edit-Steuerelement in der Tabulatorreihenfolge eingeschlossen

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]

##  <a name="cut"></a>  CEdit::Cut

Rufen Sie diese Funktion zum Löschen (Ausschneiden) die aktuelle Auswahl (sofern vorhanden), in das Bearbeitungssteuerelement, und kopieren Sie den gelöschten Text im HIERSVR-Format in die Zwischenablage.

```
void Cut();
```

### <a name="remarks"></a>Hinweise

Das Löschen von ausgeführten `Cut` rückgängig gemacht werden kann, durch den Aufruf der [rückgängig machen](#undo) Member-Funktion.

Um die aktuelle Auswahl ohne den gelöschten Text in die Zwischenablage zu löschen, rufen die [löschen](#clear) Member-Funktion.

Weitere Informationen finden Sie unter [WM_CUT](/windows/desktop/dataxchg/wm-cut) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]

##  <a name="emptyundobuffer"></a>  CEdit::EmptyUndoBuffer

Rufen Sie diese Funktion zum Zurücksetzen (löschen) das Flag zum Rückgängigmachen des ein Edit-Steuerelement.

```
void EmptyUndoBuffer();
```

### <a name="remarks"></a>Hinweise

Das Steuerelement zum Bearbeiten werden können nicht den letzten Vorgang rückgängig gemacht. Die rückgängig-Flag wird festgelegt, wenn ein Vorgang innerhalb der Edit-Steuerelement rückgängig gemacht werden kann.

Die rückgängig-Flag wird automatisch gelöscht, wenn die [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) oder [SetHandle auf](#sethandle) `CWnd` Memberfunktionen aufgerufen werden.

Weitere Informationen finden Sie unter [EM_EMPTYUNDOBUFFER](/windows/desktop/Controls/em-emptyundobuffer) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]

##  <a name="fmtlines"></a>  CEdit::FmtLines

Mit dieser Funktion können Sie die Einbeziehung von soft-Zeilenumbruchzeichen innerhalb eines mehrzeiligen Bearbeitungssteuerelements on oder off festgelegt.

```
BOOL FmtLines(BOOL bAddEOL);
```

### <a name="parameters"></a>Parameter

*bAddEOL*<br/>
Gibt an, ob vorläufig-Zeilenumbruchzeichen eingefügt werden soll. Der Wert "true" fügt die Zeichen; der Wert "false" werden diese entfernt.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn Formatierung auftritt. andernfalls 0.

### <a name="remarks"></a>Hinweise

Ein soft Zeilenumbruch besteht aus zwei Wagenrückläufe und einen Zeilenvorschub am Ende einer Zeile, die aufgrund der Wortumbruch unterbrochen wird eingefügt. Festplatte Zeilenumbruch besteht aus einem Carriage return, Wagenrücklauf und ein Zeilenvorschub. Zeilen, die mit einem Hard Zeilenumbruch enden sind nicht betroffen von `FmtLines`.

Windows wird nur reagiert, wenn die `CEdit` Objekt ist eines mehrzeiligen Bearbeitungssteuerelements.

`FmtLines` wirkt sich nur auf den Puffer, der vom [GetHandle](#gethandle) und der zurückgegebene Text [WM_GETTEXT](/windows/desktop/winmsg/wm-gettext). Es hat keine Auswirkungen auf die Anzeige des Texts in der Edit-Steuerelements.

Weitere Informationen finden Sie unter [EM_FMTLINES](/windows/desktop/Controls/em-fmtlines) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]

##  <a name="getcuebanner"></a>  CEdit::GetCueBanner

Ruft den Text ab, der angezeigt wird, als der Texthinweis "oder" Tipp, in einem Bearbeitungssteuerelement, wenn das Steuerelement leer ist.

```
BOOL GetCueBanner(
    LPWSTR lpszText,
    int cchText) const;

CString GetCueBanner() const;
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
[out] Ein Zeiger auf eine Zeichenfolge, die den Hinweistext enthält.

*cchText*<br/>
[in] Die Anzahl der Zeichen, die empfangen werden können. Diese Zahl beinhaltet das abschließende Nullzeichen.

### <a name="return-value"></a>Rückgabewert

"True" für die erste Überladung Wenn die Methode erfolgreich ist; andernfalls "false".

Für die der zweiten Überladung ist eine [CString](../../atl-mfc-shared/using-cstring.md) , die den Hinweistext enthält, wenn die Methode erfolgreich; andernfalls ist, die leere Zeichenfolge ("").

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [EM_GETCUEBANNER](/windows/desktop/Controls/em-getcuebanner) -Nachricht, die im Windows SDK beschrieben wird. Weitere Informationen finden Sie unter den [Edit_GetCueBannerText](/windows/desktop/api/commctrl/nf-commctrl-edit_getcuebannertext) Makro.

##  <a name="getfirstvisibleline"></a>  CEdit::GetFirstVisibleLine

Rufen Sie diese Funktion, um die oberste sichtbare Zeile in einem Bearbeitungssteuerelement zu bestimmen.

```
int GetFirstVisibleLine() const;
```

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index der obersten Linie angezeigt. Für einzeilige Bearbeitungssteuerelemente ist der Rückgabewert 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [EM_GETFIRSTVISIBLELINE](/windows/desktop/Controls/em-getfirstvisibleline) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]

##  <a name="gethandle"></a>  CEdit::GetHandle

Rufen Sie diese Funktion, um ein Handle für die derzeit zugeordnete eines mehrzeiligen Bearbeitungssteuerelements abzurufen.

```
HLOCAL GetHandle() const;
```

### <a name="return-value"></a>Rückgabewert

Ein lokaler Speicher-Handle, das den Puffer, der den Inhalt des Bearbeitungssteuerelements identifiziert. Wenn ein Fehler auftritt, z. B. das Senden der Nachricht an ein Bearbeitungssteuerelement einzeilige, ist der Rückgabewert 0.

### <a name="remarks"></a>Hinweise

Das Handle ist ein Handle für die lokalen Speicher und kann verwendet werden, von jedem der **lokalen** Windows-Memory-Funktionen, die einen lokalen Speicher verwenden als Parameter zu behandeln.

`GetHandle` wird nur von mehrzeiligen Bearbeitungssteuerelemente verarbeitet.

Rufen Sie `GetHandle` für ein Bearbeitungssteuerelement für mehrzeiligen in einem Dialogfeld nur, wenn das Dialogfeld mit festgelegtem Flag DS_LOCALEDIT Stil erstellt wurde. Wenn der DS_LOCALEDIT-Stil nicht festgelegt ist, erhalten Sie immer noch einen Rückgabewert ungleich NULL, aber Sie werden nicht in der Lage, den zurückgegebenen Wert verwenden.

> [!NOTE]
> `GetHandle` funktioniert nicht mit Windows 95/98. Wenn Sie aufrufen `GetHandle` in Windows 95/98, wird NULL zurückgegeben. `GetHandle` funktioniert wie beschrieben unter Windows NT, Version 3.51 und höher.

Weitere Informationen finden Sie unter [EM_GETHANDLE](/windows/desktop/Controls/em-gethandle) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]

##  <a name="gethighlight"></a>  CEdit::GetHighlight

Ruft die Indizes der das ersten und letzte Zeichen in einem Bereich von Text, der in das aktuelle Bearbeitungssteuerelement hervorgehoben wird.

```
BOOL GetHighlight(
    int* pichStart,
    int* pichEnd) const;
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*pichStart*|[out] Nullbasierte Index des ersten Zeichens im Bereich von Text, der hervorgehoben ist.|
|*pichEnd*|[out] Nullbasierte Index des letzten Zeichens in den Bereich des Texts, die hervorgehoben ist.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [EM_GETHILITE](/windows/desktop/Controls/em-gethilite) -Nachricht, die im Windows SDK beschrieben wird. Beide `SetHighlight` und `GetHighlight` derzeit für nur UNICODE-builds aktiviert sind.

##  <a name="getlimittext"></a>  CEdit::GetLimitText

Rufen Sie diese Memberfunktion rufen Sie den Text-Grenzwert für diesen `CEdit` Objekt.

```
UINT GetLimitText() const;
```

### <a name="return-value"></a>Rückgabewert

Der aktuelle Text Grenzwert in Bytes, der für diesen `CEdit` Objekt.

### <a name="remarks"></a>Hinweise

Der Text-Grenzwert ist die Höchstmenge des Textes in Bytes, die das Bearbeitungssteuerelement annehmen kann.

> [!NOTE]
>  Diese Memberfunktion wird ab, die mit Windows 95 und Windows NT 4.0 verfügbar.

Weitere Informationen finden Sie unter [EM_GETLIMITTEXT](/windows/desktop/Controls/em-getlimittext) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]

##  <a name="getline"></a>  CEdit::GetLine

Mit dieser Funktion können Sie eine Textzeile aus einem Bearbeitungssteuerelement abzurufen und platziert es in *LpszBuffer*.

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

*nIndex*<br/>
Gibt an, die Nummer der Zeile aus einer mehrzeiligen Abrufen edit-Steuerelement. Zeilennummern sind nullbasiert. der Wert 0 gibt an, die erste Zeile. Dieser Parameter wird von einem Steuerelement für die einzelnen Zeile ignoriert.

*lpszBuffer*<br/>
Verweist auf den Puffer, der eine Kopie der Zeile empfängt. Das erste Wort des Puffers muss die maximale Anzahl von Zeichen angeben, die in den Puffer kopiert werden können.

*nMaxLength*<br/>
Gibt die maximale Anzahl von Bytes, die in den Puffer kopiert werden können. `GetLine` stellt diesen Wert in das erste Wort *LpszBuffer* vor dem Aufruf von Windows.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der tatsächlich kopierter Bytes. Der Rückgabewert ist 0, wenn die Nummer der Zeile angegeben *nIndex* ist größer als die Anzahl der Zeilen im Bearbeitungssteuerelement.

### <a name="remarks"></a>Hinweise

Die kopierte Zeile enthält einen Null-Terminierungszeichen nicht.

Weitere Informationen finden Sie unter [EM_GETLINE](/windows/desktop/Controls/em-getline) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEdit::GetLineCount](#getlinecount).

##  <a name="getlinecount"></a>  CEdit::GetLineCount

Rufen Sie diese Funktion, um die Anzahl der Zeilen in einer mehrzeiligen Bearbeitungssteuerelements abzurufen.

```
int GetLineCount() const;
```

### <a name="return-value"></a>Rückgabewert

Eine ganze Zahl, die Anzahl der Zeilen in der mehrzeiligen Bearbeitungssteuerelements an. Wenn kein Text in das Bearbeitungssteuerelement eingegeben wurde, ist der zurückgegebene Wert 1.

### <a name="remarks"></a>Hinweise

`GetLineCount` Mehrzeilige Bearbeitungssteuerelemente wird nur verarbeitet.

Weitere Informationen finden Sie unter [EM_GETLINECOUNT](/windows/desktop/Controls/em-getlinecount) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]

##  <a name="getmargins"></a>  CEdit::GetMargins

Rufen Sie diese Memberfunktion zum Abrufen von der linken und rechten Rand des Bearbeitungssteuerelements.

```
DWORD GetMargins() const;
```

### <a name="return-value"></a>Rückgabewert

Die Breite des linken Rands in das niederwertige Wort und die Breite des rechten Rands in das höherwertige Wort.

### <a name="remarks"></a>Hinweise

Ränder werden in Pixel gemessen.

> [!NOTE]
>  Diese Memberfunktion wird ab, die mit Windows 95 und Windows NT 4.0 verfügbar.

Weitere Informationen finden Sie unter [EM_GETMARGINS](/windows/desktop/Controls/em-getmargins) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).

##  <a name="getmodify"></a>  CEdit::GetModify

Rufen Sie diese Funktion, um zu bestimmen, ob der Inhalt von einem Bearbeitungssteuerelement geändert wurden.

```
BOOL GetModify() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn der Inhalt des Bearbeitungssteuerelements geändert wurden; 0, wenn sie geblieben unverändert.

### <a name="remarks"></a>Hinweise

Windows verwaltet ein internes Flag gibt an, ob der Inhalt des Bearbeitungssteuerelements geändert wurde. Dieses Flag wird gelöscht, wenn das Bearbeitungssteuerelement zuerst erstellt und auch werden, durch den Aufruf gelöscht kann der [SetModify](#setmodify) Member-Funktion.

Weitere Informationen finden Sie unter [EM_GETMODIFY](/windows/desktop/Controls/em-getmodify) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]

##  <a name="getpasswordchar"></a>  CEdit::GetPasswordChar

Mit dieser Funktion können Kennwortzeichen abzurufen, das in einem Bearbeitungssteuerelement angezeigt wird, wenn der Benutzer Text eingibt.

```
TCHAR GetPasswordChar() const;
```

### <a name="return-value"></a>Rückgabewert

Gibt das Zeichen, die das Zeichen angezeigt werden, die der Benutzer eingegeben. Der Rückgabewert ist NULL, wenn kein Kennwortzeichen vorhanden ist.

### <a name="remarks"></a>Hinweise

Wenn Sie das Steuerelement zum Bearbeiten mit dem ES_PASSWORD-Stil erstellen, bestimmt die DLL, die das Steuerelement unterstützt das Standardkennwortzeichen an. Das Manifest oder [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) Methode bestimmt die DLL unterstützt das Steuerelement zum Bearbeiten. Wenn das Steuerelement zum Bearbeiten von "User32.dll" unterstützt wird, ist das das Standardkennwortzeichen Sternchen ("*", U + 002A). Wenn comctl32.dll Version 6 der Edit-Steuerelement unterstützt, ist das Standardzeichen SCHWARZER Kreis ("●", U + 25CF). Weitere Informationen zu der DLL und die Version unterstützt das häufig verwendeter Steuerelemente finden Sie unter [Shell und allgemeine Steuerelemente Versionen](https://msdn.microsoft.com/library/windows/desktop/bb776779).

Diese Methode sendet die [EM_GETPASSWORDCHAR](/windows/desktop/Controls/em-getpasswordchar) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]

##  <a name="getrect"></a>  CEdit::GetRect

Rufen Sie diese Funktion zum Abrufen des Formatierungsrechtecks des ein Edit-Steuerelements.

```
void GetRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf die `RECT` -Struktur, des Formatierungsrechtecks empfängt.

### <a name="remarks"></a>Hinweise

Des Formatierungsrechtecks handelt es sich um das begrenzende Rechteck des Texts, die unabhängig von der Größe des Fensters bearbeiten-Steuerelement ist.

Des Formatierungsrechtecks eines mehrzeiligen Bearbeitungssteuerelements kann geändert werden, indem die [SetRect](#setrect) und [SetRectNP](#setrectnp) Memberfunktionen.

Weitere Informationen finden Sie unter [EM_GETRECT](/windows/desktop/Controls/em-getrect) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEdit::LimitText](#limittext).

##  <a name="getsel"></a>  CEdit::GetSel

Rufen Sie diese Funktion rufen Sie die Start- und Endzeichen des die aktuelle Auswahl (sofern vorhanden) in ein Bearbeitungssteuerelement, das mit den Rückgabewert oder Parameter.

```
DWORD GetSel() const;

void GetSel(
    int& nStartChar,
    int& nEndChar) const;
```

### <a name="parameters"></a>Parameter

*nStartChar*<br/>
Verweis auf eine ganze Zahl, die die Position des ersten Zeichens in der aktuellen Auswahl erhält.

*nEndChar*<br/>
Verweis auf eine ganze Zahl, die die Position des ersten Zeichens nach dem Ende der aktuellen Auswahl nicht ausgewählten erhält.

### <a name="return-value"></a>Rückgabewert

Die Version, die einen DWORD-Wert zurückgibt, gibt einen Wert, der die Anfangsposition in das niederwertige Wort und die Position des ersten Zeichens nicht ausgewählten nach dem Ende der Auswahl in das höherwertige Wort enthält.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [EM_GETSEL](/windows/desktop/Controls/em-getsel) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]

##  <a name="hideballoontip"></a>  CEdit::HideBalloonTip

Blendet alle das aktuelle Bearbeitungssteuerelement zugeordneten QuickInfo-Sprechblase an.

```
BOOL HideBalloonTip();
```

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Funktion sendet die [EM_HIDEBALLOONTIP](/windows/desktop/Controls/em-hideballoontip) -Nachricht, die im Windows SDK beschrieben wird.

##  <a name="limittext"></a>  CEdit::LimitText

Rufen Sie diese Funktion, um die Länge des Texts zu beschränken, die der Benutzer in ein Bearbeitungssteuerelement eingeben kann.

```
void LimitText(int nChars = 0);
```

### <a name="parameters"></a>Parameter

*nChars*<br/>
Gibt die Länge (in Byte) des Texts, der der Benutzer eingeben kann. Wenn dieser Parameter 0 ist, wird die Textlänge UINT_MAX Bytes festgelegt. Dies ist das Standardverhalten.

### <a name="remarks"></a>Hinweise

Änderungen am Text Grenzwert schränkt nur den Text an, die, den der Benutzer eingeben kann. Wirkt sich nicht auf einen beliebigen Text ein bereits in das Bearbeitungssteuerelement, noch wirkt sie sich die Länge des Texts in das Steuerelement zum Bearbeiten von kopiert die [SetWindowText](cwnd-class.md#setwindowtext) -Memberfunktion im `CWnd`. Wenn eine Anwendung verwendet die `SetWindowText` Funktion zum Platzieren von mehr Text in ein Bearbeitungssteuerelement, als im Aufruf angegeben ist `LimitText`, der Benutzer kann den Text in das Bearbeitungssteuerelement löschen. Allerdings die textlimit wird verhindert, dass den Benutzer den vorhandenen Text durch neuen Text zu ersetzen, führt dazu, dass den Text, der unterhalb des Limits Text gehören, sofern nicht die aktuelle Auswahl zu löschen.

> [!NOTE]
>  In Win32 (Windows NT und Windows 95/98), [SetLimitText](#setlimittext) diese Funktion ersetzt.

Weitere Informationen finden Sie unter [EM_LIMITTEXT](/windows/desktop/Controls/em-limittext) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]

##  <a name="linefromchar"></a>  CEdit::LineFromChar

Rufen Sie diese Funktion, um die Zeilennummer der Zeile abzurufen, die den angegebenen Zeichenindex enthält.

```
int LineFromChar(int nIndex = -1) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Enthält den nullbasierten Indexwert für das gewünschte Zeichen im Text des Edit-Steuerelements, oder -1. Wenn *nIndex* -1 ist, wird die aktuelle Zeile, d. h. die Zeile, die den Textcursor enthält.

### <a name="return-value"></a>Rückgabewert

Die nullbasierte Zeilennummer der Zeile mit den vom angegebenen Zeichenindex *nIndex*. Wenn *nIndex* ist-1. die Zahl der Zeile, die das erste Zeichen der Auswahl enthält zurückgegeben. Wenn keine Auswahl vorhanden ist, wird die Nummer der aktuellen Zeile zurückgegeben.

### <a name="remarks"></a>Hinweise

Ein Zeichenindex ist die Anzahl der Zeichen vom Anfang des Edit-Steuerelements.

Diese Memberfunktion wird nur von mehrzeiligen Edit-Steuerelemente verwendet werden.

Weitere Informationen finden Sie unter [EM_LINEFROMCHAR](/windows/desktop/Controls/em-linefromchar) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]

##  <a name="lineindex"></a>  CEdit::LineIndex

Mit dieser Funktion können Sie den Zeichenindex des einer Zeile eines mehrzeiligen Bearbeitungssteuerelements abzurufen.

```
int LineIndex(int nLine = -1) const;
```

### <a name="parameters"></a>Parameter

*nLine*<br/>
Enthält den Indexwert für die gewünschte Position im Text des Edit-Steuerelements, oder -1. Wenn *nLine* -1 ist, wird die aktuelle Zeile, d. h. die Zeile, die den Textcursor enthält.

### <a name="return-value"></a>Rückgabewert

Der Index des Anfangszeichens der Zeile im angegebenen *nLine* oder -1, wenn die angegebenen Zeilennummer größer als die Anzahl der Zeilen in das Bearbeitungssteuerelement ist.

### <a name="remarks"></a>Hinweise

Der Zeichenindex ist die Anzahl der Zeichen vom Anfang des Edit-Steuerelements in die angegebene Zeile.

Diese Memberfunktion wird nur von mehrzeiligen Bearbeitungssteuerelemente verarbeitet.

Weitere Informationen finden Sie unter [EM_LINEINDEX](https://msdn.microsoft.com/library/windows/desktop/bb761611) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]

##  <a name="linelength"></a>  CEdit::LineLength

Ruft die Länge einer Zeile in einem Bearbeitungssteuerelement ab.

```
int LineLength(int nLine = -1) const;
```

### <a name="parameters"></a>Parameter

*nLine*<br/>
Der nullbasierte Index eines Zeichens in der Zeile, deren Länge abgerufen werden sollen. Der Standardwert ist -1.

### <a name="return-value"></a>Rückgabewert

Für einzeilige Bearbeitungssteuerelemente ist der Rückgabewert der Länge des Texts in das Bearbeitungssteuerelement in TCHARs.

Für mehrzeilige Bearbeitungssteuerelemente, der Rückgabewert ist die Länge der Zeile anhand des in TCHARs, die *nLine* Parameter. Für ANSI-Text ist die Länge der Anzahl der Bytes in der Zeile. für Unicode-Text ist die Länge der Anzahl der Zeichen in der Zeile. Die Länge schließt nicht die Zeichen Wagenrücklauf am Ende der Zeile.

Wenn die *nLine* -Parameter ist größer als die Anzahl der Zeichen in das Steuerelement, der Rückgabewert ist 0 (null).

Wenn die *nLine* Parameter ist 1, der Rückgabewert ist die Anzahl von nicht markierten Zeichen in den Zeilen, die markierte Zeichen enthalten. Wenn die Auswahl aus dem vierten Zeichen einer Zeile, die über das achte Zeichen vom Ende der nächsten Zeile erweitert wird, ist der Rückgabewert z. B. 10. D. h., drei Zeichen auf der ersten Zeile und sieben bei der nächsten.

Weitere Informationen zu den TCHAR-Typ, finden Sie unter der TCHAR-Zeile in der Tabelle im [Windows-Datentypen](/windows/desktop/WinProg/windows-data-types).

### <a name="remarks"></a>Hinweise

Diese Methode wird von unterstützt die [EM_LINELENGTH](/windows/desktop/Controls/em-linelength) -Nachricht, die im Windows SDK beschrieben wird.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEdit::LineIndex](#lineindex).

##  <a name="linescroll"></a>  CEdit::LineScroll

Rufen Sie diese Funktion den Text eines mehrzeiligen Bearbeitungssteuerelements einen Bildlauf durchführen.

```
void LineScroll(
    int nLines,
    int nChars = 0);
```

### <a name="parameters"></a>Parameter

*nLines*<br/>
Gibt die Anzahl der Zeilen, die einen vertikalen Bildlauf durchführen.

*nChars*<br/>
Gibt die Anzahl von Zeichenpositionen einen horizontalen Bildlauf durchführen. Dieser Wert wird ignoriert, wenn das Steuerelement zum Bearbeiten oder die ES_RIGHT-ES_CENTER verfügt.

### <a name="remarks"></a>Hinweise

Diese Memberfunktion wird nur von mehrzeiligen Bearbeitungssteuerelemente verarbeitet.

Das Bearbeitungssteuerelement scrollt vertikal nicht hinter der letzten Zeile des Texts im Bearbeitungssteuerelement. Wenn die aktuelle zuzüglich der Anzahl der Zeilen, die durch angegebene Zeile *nLines* überschreitet die Gesamtzahl der Zeilen im Bearbeitungssteuerelement, der Wert wird so angepasst, dass die letzte Zeile des Edit-Steuerelements an den Anfang des Fensters bearbeiten-Steuerelement ein Bildlauf durchgeführt wird.

`LineScroll` kann für einen horizontalen Bildlauf hinter dem letzten Zeichen in jeder Zeile verwendet werden.

Weitere Informationen finden Sie unter [EM_LINESCROLL](/windows/desktop/Controls/em-linescroll) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEdit::GetFirstVisibleLine](#getfirstvisibleline).

##  <a name="paste"></a>  CEdit::Paste

Mit dieser Funktion wird zum Einfügen von Daten aus der Zwischenablage in die `CEdit` an der Einfügemarke.

```
void Paste();
```

### <a name="remarks"></a>Hinweise

Daten werden eingefügt, nur, wenn die Zwischenablage Daten im HIERSVR Format enthält.

Weitere Informationen finden Sie unter [WM_PASTE](/windows/desktop/dataxchg/wm-paste) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]

##  <a name="posfromchar"></a>  CEdit::PosFromChar

Mit dieser Funktion können Sie die Position (linke obere Ecke) eines angegebenen Zeichens innerhalb dieses erste `CEdit` Objekt.

```
CPoint PosFromChar(UINT nChar) const;
```

### <a name="parameters"></a>Parameter

*NChar*<br/>
Der nullbasierte Index des angegebenen Zeichens.

### <a name="return-value"></a>Rückgabewert

Die Koordinaten der oberen linken Ecke des durch angegebene Zeichen *nChar*.

### <a name="remarks"></a>Hinweise

Das Zeichen wird durch Angabe ihres nullbasierten Indexwerts angegeben. Wenn *nChar* ist größer als der Index des letzten Zeichens in dieser `CEdit` Objekt ist, wird der Rückgabewert gibt die Koordinaten der die Position direkt hinter dem letzten Zeichen in dieser `CEdit` Objekt.

> [!NOTE]
>  Diese Memberfunktion wird ab, die mit Windows 95 und Windows NT 4.0 verfügbar.

Weitere Informationen finden Sie unter [EM_POSFROMCHAR](/windows/desktop/Controls/em-posfromchar) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEdit::LineFromChar](#linefromchar).

##  <a name="replacesel"></a>  CEdit::ReplaceSel

Mit dieser Funktion können Sie die aktuelle Auswahl in einem Bearbeitungssteuerelement mit den angegebenen Text ersetzen *LpszNewText*.

```
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```

### <a name="parameters"></a>Parameter

*lpszNewText*<br/>
Verweist auf eine Null-terminierte Zeichenfolge, die den Ersetzungstext enthält.

*bCanUndo*<br/>
Um anzugeben, dass diese Funktion rückgängig gemacht werden kann, wird den Wert dieses Parameters auf "true" fest. Der Standardwert ist "false".

### <a name="remarks"></a>Hinweise

Wird nur einen Teil des Texts in einem Bearbeitungssteuerelement ersetzt. Wenn Sie den gesamten Text ersetzen möchten, verwenden Sie die [CWnd::SetWindowText](cwnd-class.md#setwindowtext) Member-Funktion.

Wenn keine aktuelle Auswahl vorhanden ist, wird der Ersetzungstext an der aktuellen Cursorposition eingefügt.

Weitere Informationen finden Sie unter [EM_REPLACESEL](/windows/desktop/Controls/em-replacesel) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEdit::LineIndex](#lineindex).

##  <a name="setcuebanner"></a>  CEdit::SetCueBanner

Legt fest, den Text, der als der Texthinweis angezeigt wird oder Tipp, in Bearbeitung steuern, wenn das Steuerelement leer ist.

```
BOOL SetCueBanner(LPCWSTR lpszText);

BOOL SetCueBanner(
    LPCWSTR lpszText,
    BOOL fDrawWhenFocused = FALSE);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
[in] Zeiger auf eine Zeichenfolge, die das Stichwort dafür enthält, in das Bearbeitungssteuerelement angezeigt.

*fDrawWhenFocused*<br/>
[in] False gibt an, wird das hinweisbanner nicht gezeichnet, wenn der Benutzer in der Edit-Steuerelement klickt und dem Steuerelement den Fokus gibt.

Bei "true", wird das hinweisbanner gezeichnet, selbst wenn das Steuerelement den Fokus besitzt. Das hinweisbanner wird ausgeblendet, wenn der Benutzer beginnt, geben Sie in das Steuerelement.

Der Standardwert ist "false".

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [EM_SETCUEBANNER](/windows/desktop/Controls/em-setcuebanner) -Nachricht, die im Windows SDK beschrieben wird. Weitere Informationen finden Sie unter den [Edit_SetCueBannerTextFocused](/windows/desktop/api/commctrl/nf-commctrl-edit_setcuebannertextfocused) Makro.

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die [CEdit::SetCueBanner](#setcuebanner) Methode.

[!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]

##  <a name="sethandle"></a>  CEdit::SetHandle

Rufen Sie diese Funktion, um das Handle auf den lokalen Speicher festzulegen, die von einem mehrzeiligen Bearbeitungssteuerelements verwendet wird.

```
void SetHandle(HLOCAL hBuffer);
```

### <a name="parameters"></a>Parameter

*hBuffer*<br/>
Enthält ein Handle für den lokalen Speicher an. Dieses Handle muss durch einen vorherigen Aufruf erstellt wurden die [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc) Windows-Funktion, die mit dem Flag LMEM_MOVEABLE. Der Arbeitsspeicher wird angenommen, eine Null-terminierte Zeichenfolge enthalten. Wenn dies nicht der Fall ist, sollte das erste Byte des zugeordneten Speichers auf 0 festgelegt werden.

### <a name="remarks"></a>Hinweise

Das Steuerelement zum Bearbeiten verwendet dann diesen Puffer zum Speichern des aktuell angezeigten Texts, anstatt einen eigenen Puffer zuzuweisen.

Diese Memberfunktion wird nur von mehrzeiligen Bearbeitungssteuerelemente verarbeitet.

Bevor eine Anwendung ein neues Speicherhandle festlegt, muss bei Verwendung der [GetHandle](#gethandle) Memberfunktion, um das Handle in der aktuellen Arbeitsspeicherpuffer abrufen und Freigeben von Arbeitsspeicher verwenden die `LocalFree` Windows-Funktion.

`SetHandle` Löscht den Rückgängigpuffer (der [CanUndo](#canundo) Memberfunktion gibt dann zurück, 0) und das Kennzeichen für die interne Änderungen (die [GetModify](#getmodify) dann Member-Funktion gibt 0 zurück). Das Fenster des bearbeiten-Steuerelement neu gezeichnet wird.

Sie können diese Memberfunktion in einer mehrzeiligen Bearbeitungssteuerelements in einem Dialogfeld verwenden, nur dann, wenn Sie das Dialogfeld mit festgelegtem Flag DS_LOCALEDIT Stil erstellt haben.

> [!NOTE]
> `GetHandle` funktioniert nicht mit Windows 95/98. Wenn Sie aufrufen `GetHandle` in Windows 95/98, wird NULL zurückgegeben. `GetHandle` funktioniert wie beschrieben unter Windows NT, Version 3.51 und höher.

Weitere Informationen finden Sie unter [EM_SETHANDLE](/windows/desktop/Controls/em-sethandle), [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc), und [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]

##  <a name="sethighlight"></a>  CEdit::SetHighlight

Bearbeitungssteuerelement für Highlights ein Textbereich, der in der aktuellen angezeigt wird.

```
void SetHighlight(
    int ichStart,
    int ichEnd);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*ichStart*|[in] Nullbasierte Index des ersten Zeichens in den Textbereich hervorheben.|
|*ichEnd*|[in] Nullbasierte Index des letzten Zeichens in den Textbereich hervorheben.|

### <a name="remarks"></a>Hinweise

Diese Methode sendet die [EM_SETHILITE](/windows/desktop/Controls/em-sethilite) -Nachricht, die im Windows SDK beschrieben wird.  Diese Methode sendet die [EM_SETHILITE](/windows/desktop/Controls/em-sethilite) -Nachricht, die im Windows SDK beschrieben wird. Beide `SetHighlight` und `GetHighlight` für nur UNICODE-builds aktiviert sind.

##  <a name="setlimittext"></a>  CEdit::SetLimitText

Rufen Sie diese Memberfunktion zum Festlegen der textlimit für diesen `CEdit` Objekt.

```
void SetLimitText(UINT nMax);
```

### <a name="parameters"></a>Parameter

*nmax.*<br/>
Der neue Text-Grenzwert, in Zeichen.

### <a name="remarks"></a>Hinweise

Der Text-Grenzwert ist die Höchstmenge des Textes in Zeichen ein, die das Bearbeitungssteuerelement annehmen kann.

Änderungen am Text Grenzwert schränkt nur den Text an, die, den der Benutzer eingeben kann. Wirkt sich nicht auf einen beliebigen Text ein bereits in das Bearbeitungssteuerelement, noch wirkt sie sich die Länge des Texts in das Steuerelement zum Bearbeiten von kopiert die [SetWindowText](cwnd-class.md#setwindowtext) -Memberfunktion im `CWnd`. Wenn eine Anwendung verwendet die `SetWindowText` Funktion zum Platzieren von mehr Text in ein Bearbeitungssteuerelement, als im Aufruf angegeben ist `LimitText`, der Benutzer kann den Text in das Bearbeitungssteuerelement löschen. Allerdings die textlimit wird verhindert, dass den Benutzer den vorhandenen Text durch neuen Text zu ersetzen, führt dazu, dass den Text, der unterhalb des Limits Text gehören, sofern nicht die aktuelle Auswahl zu löschen.

Diese Funktion ersetzt [LimitText](#limittext) in Win32.

Weitere Informationen finden Sie unter [EM_SETLIMITTEXT](/windows/desktop/Controls/em-setlimittext) im Windows SDK.

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

*nLeft*<br/>
Die Breite des neuen linken Rand in Pixel.

*nRight*<br/>
Die Breite des der neuen rechten Rand in Pixel.

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Diese Memberfunktion wird ab, die mit Windows 95 und Windows NT 4.0 verfügbar.

Weitere Informationen finden Sie unter [EM_SETMARGINS](/windows/desktop/Controls/em-setmargins) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).

##  <a name="setmodify"></a>  CEdit::SetModify

Mit dieser Funktion können aktivieren oder deaktivieren Sie das Änderungsflag für eine Bearbeitungssteuerelement.

```
void SetModify(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Parameter

*bModified*<br/>
Der Wert "true" gibt an, dass der Text wurde geändert, und der Wert "false" gibt an, dass es unverändert ist. Standardmäßig wird das Änderungsflag festgelegt.

### <a name="remarks"></a>Hinweise

Das geänderte Flag gibt an, und zwar unabhängig davon, ob der Text im Bearbeitungssteuerelement geändert wurde. Es wird automatisch festgelegt, wenn der Benutzer den Text ändert. Der Wert abgerufen werden kann, mit der [GetModify](#getmodify) Member-Funktion.

Weitere Informationen finden Sie unter [EM_SETMODIFY](/windows/desktop/Controls/em-setmodify) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEdit::GetModify](#getmodify).

##  <a name="setpasswordchar"></a>  CEdit::SetPasswordChar

Mit dieser Funktion können Sie festlegen oder entfernen ein Kennwort ein Zeichen in einem Bearbeitungssteuerelement angezeigt wird, wenn der Benutzer Text eingibt.

```
void SetPasswordChar(TCHAR ch);
```

### <a name="parameters"></a>Parameter

*ch*<br/>
Gibt das Zeichen, die anstelle der vom Benutzer eingegebenen Zeichen angezeigt werden. Wenn *ch* gleich 0 ist, werden die tatsächlichen Zeichen, die vom Benutzer eingegeben wird angezeigt.

### <a name="remarks"></a>Hinweise

Wenn ein Kennwort ein Zeichen festgelegt ist, wird das Zeichen für jedes Zeichen, dass der Benutzer eingibt.

Diese Memberfunktion wirkt sich nicht auf ein mehrzeiliges Steuerelement zu bearbeiten.

Wenn die `SetPasswordChar` Memberfunktion aufgerufen wird, `CEdit` wird neu gezeichnet werden alle sichtbar, mit dem durch angegebenen Zeichen *ch*.

Wenn das Steuerelement zum Bearbeiten mit erstellt haben, wird die [ES_PASSWORD](styles-used-by-mfc.md#edit-styles) Stil, das das Standardkennwortzeichen auf ein Sternchen festgelegt ist ( <strong>\*</strong>). Dieses Format wird entfernt, wenn `SetPasswordChar` aufgerufen wird und *ch* auf 0 festgelegt.

Weitere Informationen finden Sie unter [EM_SETPASSWORDCHAR](/windows/desktop/Controls/em-setpasswordchar) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]

##  <a name="setreadonly"></a>  CEdit::SetReadOnly

Ruft diese Funktion zum Festlegen des schreibgeschützten Status des ein Edit-Steuerelements.

```
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```

### <a name="parameters"></a>Parameter

*bReadOnly*<br/>
Gibt an, ob festlegen oder entfernen den schreibgeschützten Status des Edit-Steuerelements. Der Wert TRUE legt den Zustand in den schreibgeschützten Modus fest; den Wert "false" wird den Zustand, der Lese-/Schreibzugriff.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Vorgang erfolgreich war, oder 0, wenn ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Die aktuelle Einstellung finden Sie, indem Sie die Tests die [ES_READONLY](styles-used-by-mfc.md#edit-styles) -Kennzeichen in den Rückgabewert der [CWnd::GetStyle](cwnd-class.md#getstyle).

Weitere Informationen finden Sie unter [EM_SETREADONLY](/windows/desktop/Controls/em-setreadonly) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]

##  <a name="setrect"></a>  CEdit::SetRect

Rufen Sie diese Funktion, um die Abmessungen des Rechtecks mit den angegebenen Koordinaten festgelegt.

```
void SetRect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf die `RECT` Struktur oder `CRect` Objekt, das die Abmessungen des des Formatierungsrechtecks angibt.

### <a name="remarks"></a>Hinweise

Dieses Element wird nur von mehrzeiligen Bearbeitungssteuerelemente verarbeitet.

Verwendung `SetRect` , legen Sie die Formatierung Rechteck ein mehrzeiliges Steuerelement bearbeiten. Des Formatierungsrechtecks handelt es sich um das begrenzende Rechteck des Texts, die unabhängig von der Größe des Fensters bearbeiten-Steuerelement ist. Wenn das Bearbeitungssteuerelement erstellt wird, ist des Formatierungsrechtecks identisch mit den Clientbereich des Fensters bearbeiten-Steuerelement. Mithilfe der `SetRect` Member-Funktion, eine Anwendung kann Erstellen des Formatierungsrechtecks größer oder kleiner als das Bearbeiten-Steuerelement-Fenster.

Wenn das Steuerelement zum Bearbeiten kein Bildlauf durchgeführt wird, wird Text abgeschnitten nicht umbrochen, wenn größer als das Fenster des Formatierungsrechtecks erfolgt. Wenn das Steuerelement zum Bearbeiten ein Rahmens enthält, wird die Größe des Rahmens des Formatierungsrechtecks verringert. Wenn Sie das von zurückgegebene Rechteck Anpassen der `GetRect` Member-Funktion müssen Sie die Größe des Rahmens entfernen, bevor Sie das Rechteck übergeben `SetRect`.

Wenn `SetRect` aufgerufen wird, wird das Steuerelement zum Bearbeiten der Text auch neu formatiert und erneut angezeigt.

Weitere Informationen finden Sie unter [EM_SETRECT](/windows/desktop/Controls/em-setrect) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]

##  <a name="setrectnp"></a>  CEdit::SetRectNP

Rufen Sie diese Funktion zum Festlegen des Formatierungsrechtecks eines mehrzeiligen Bearbeitungssteuerelements an.

```
void SetRectNP(LPCRECT lpRect);
```

### <a name="parameters"></a>Parameter

*lpRect*<br/>
Verweist auf eine `RECT` Struktur oder `CRect` Objekt, das die Abmessungen des Rechtecks angibt.

### <a name="remarks"></a>Hinweise

Des Formatierungsrechtecks handelt es sich um das begrenzende Rechteck des Texts, die unabhängig von der Größe des Fensters bearbeiten-Steuerelement ist.

`SetRectNP` ist identisch mit der `SetRect` Memberfunktion mit dem Unterschied, dass das Bearbeiten-Steuerelement-Fenster nicht neu gezeichnet wird.

Wenn das Bearbeitungssteuerelement erstellt wird, ist des Formatierungsrechtecks identisch mit den Clientbereich des Fensters bearbeiten-Steuerelement. Durch Aufrufen der `SetRectNP` Member-Funktion, eine Anwendung kann Erstellen des Formatierungsrechtecks größer oder kleiner als das Bearbeiten-Steuerelement-Fenster.

Wenn das Steuerelement zum Bearbeiten kein Bildlauf durchgeführt wird, wird Text abgeschnitten nicht umbrochen, wenn größer als das Fenster des Formatierungsrechtecks erfolgt.

Dieses Element wird nur von mehrzeiligen Bearbeitungssteuerelemente verarbeitet.

Weitere Informationen finden Sie unter [EM_SETRECTNP](/windows/desktop/Controls/em-setrectnp) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEdit::SetRect](#setrect).

##  <a name="setsel"></a>  CEdit::SetSel

Mit dieser Funktion können Sie wählen Sie einen Bereich von Zeichen in einem Bearbeitungssteuerelement.

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

*dwSelection*<br/>
Gibt die Anfangsposition in das niederwertige Wort und die Endposition in das höherwertige Wort. Wenn das niederwertige Wort 0 ist, und das höherwertige Wort-1 ist, ist gesamten Text im Bearbeitungssteuerelement ausgewählt. Wenn das niederwertige Wort-1 ist, wird eine aktuelle Auswahl entfernt.

*bNoScroll*<br/>
Gibt an, ob die Einfügemarke in die Ansicht gescrollt werden soll. False gibt an, die Einfügemarke in die Ansicht ein Bildlauf durchgeführt wird. True gibt an, die Einfügemarke nicht in der Ansicht ein Bildlauf durchgeführt wird.

*nStartChar*<br/>
Gibt die Anfangsposition an. Wenn *nStartChar* ist 0 und *nEndChar* ist-1, alle in der Text im Bearbeitungssteuerelement ausgewählt ist. Wenn *nStartChar* -1 ist, wird eine aktuelle Auswahl entfernt.

*nEndChar*<br/>
Gibt die Endposition.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [EM_SETSEL](/windows/desktop/Controls/em-setsel) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEdit::GetSel](#getsel).

##  <a name="settabstops"></a>  CEdit::SetTabStops

Rufen Sie diese Funktion zum Festlegen von Tabstopps in ein Bearbeitungssteuerelement für mehrzeiligen.

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Parameter

*cxEachStop*<br/>
Gibt an, dass Tabstopps zur festgelegt werden alle *CxEachStop* Dialogeinheiten.

*nTabStops*<br/>
Gibt die Anzahl von Tabstopps in enthaltenen *RgTabStops*. Diese Zahl muss größer als 1 sein.

*rgTabStops*<br/>
Zeigt auf ein Array von Ganzzahlen ohne Vorzeichen, die Angabe der Registerkarte "wird beendet, in Dialogeinheiten. Eine Dialogeinheit ist einem horizontalen oder vertikalen Abstand. Eine horizontale Dialogeinheit ein Viertel der aktuellen Dialogfeld Basis Breite Einheit entspricht, und 1 Einheit der vertikalen Dialogfeld ein Achtel der aktuellen Dialogfeld Basis Höhe Einheit entspricht. Die Dialogfeld Basiseinheiten werden basierend auf die Höhe und Breite der aktuellen Systemschriftart berechnet. Die `GetDialogBaseUnits` Windows-Funktion gibt den aktuellen Dialogfeld Basiseinheiten in Pixel.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Registerkarten festgelegt wurden; andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn auf ein Bearbeitungssteuerelement für mehrzeiligen Text kopiert wird, bewirkt jede Registerkarte Zeichen im Text Leerzeichen bis zum nächsten Tabstopp generiert werden soll.

Um die Standardgröße 32 Dialogeinheiten Tabstopps festzulegen, rufen Sie die parameterlose Version von dieser Memberfunktion. Um eine andere Größe als 32 Tabstopps festzulegen, rufen Sie die Version mit der *CxEachStop* Parameter. Um ein Array von Größen Tabstopps festzulegen, verwenden Sie die Version mit zwei Parametern.

Diese Memberfunktion wird nur von mehrzeiligen Bearbeitungssteuerelemente verarbeitet.

`SetTabStops` wird nicht automatisch die Editor-Fenster neu zeichnen. Wenn Sie die Tabstopps für den Text im Bearbeitungssteuerelement bereits ändern, rufen Sie [CWnd::InvalidateRect](cwnd-class.md#invalidaterect) Editor-Fenster neu zeichnen.

Weitere Informationen finden Sie unter [EM_SETTABSTOPS](/windows/desktop/Controls/em-settabstops) und [GetDialogBaseUnits](/windows/desktop/api/winuser/nf-winuser-getdialogbaseunits) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CEditView::SetTabStops](ceditview-class.md#settabstops).

##  <a name="showballoontip"></a>  CEdit::ShowBalloonTip

Zeigt eine QuickInfo-Sprechblase, die das aktuelle Bearbeitungssteuerelement zugeordnet ist.

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
|*pEditBalloonTip*|[in] Zeiger auf ein [EDITBALLOONTIP](/windows/desktop/api/commctrl/ns-commctrl-_tageditballoontip) -Struktur, der die SprechblasenInfo beschreibt.|
|*lpszTitle*|[in] Zeiger auf eine Unicodezeichenfolge, die den Titel der SprechblasenInfo enthält.|
|*lpszText*|[in] Zeiger auf eine Unicode-Zeichenfolge, die die Sprechblase QuickInfo-Text enthält.|
|*ttiIcon*|[in] Ein **INT** , die angibt, dass der Typ des Symbols, der die SprechblasenInfo zugeordnet werden soll. Der Standardwert ist TTI_NONE. Weitere Informationen finden Sie unter den `ttiIcon` Mitglied der [EDITBALLOONTIP](/windows/desktop/api/commctrl/ns-commctrl-_tageditballoontip) Struktur.|

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Funktion sendet die [EM_SHOWBALLOONTIP](/windows/desktop/Controls/em-showballoontip) -Nachricht, die im Windows SDK beschrieben wird. Weitere Informationen finden Sie unter den [Edit_ShowBalloonTip](/windows/desktop/api/commctrl/nf-commctrl-edit_showballoontip) Makro.

### <a name="example"></a>Beispiel

Das folgende Codebeispiel definiert eine Variable, `m_cedit`, d. h. für den Zugriff auf das aktuelle Steuerelement zum Bearbeiten. Diese Variable wird im nächsten Beispiel verwendet.

[!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]

### <a name="example"></a>Beispiel

Das folgende Codebeispiel zeigt eine SprechblasenInfo für ein Edit-Steuerelement an. Die [CEdit::ShowBalloonTip](#showballoontip) Methode gibt ein QuickInfo-Text für Titel und eine Sprechblase an.

[!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]

##  <a name="undo"></a>  CEdit::Undo

Rufen Sie diese Funktion den letzten Vorgang für die bearbeiten-Steuerelement rückgängig machen.

```
BOOL Undo();
```

### <a name="return-value"></a>Rückgabewert

Bei einem einzeiligen Bearbeitungssteuerelement ist der Rückgabewert immer ungleich NULL. Für eines mehrzeiligen Bearbeitungssteuerelements, ist der Rückgabewert ungleich NULL, wenn der Rückgängig-Vorgang erfolgreich ist oder 0, wenn der Rückgängig-Vorgang ein Fehler auftritt.

### <a name="remarks"></a>Hinweise

Ein Rückgängig-Vorgang kann auch rückgängig gemacht werden. Sie können z. B. gelöschten Text mit dem ersten Aufruf von wiederherstellen `Undo`. Solange Sie keine beteiligten Bearbeitungsvorgang wird können, entfernen Sie den Text erneut mit einem zweiten Aufruf von `Undo`.

Weitere Informationen finden Sie unter [EM_UNDO](/windows/desktop/Controls/em-undo) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel CALCDRIV](../../visual-cpp-samples.md)<br/>
[MFC-Beispiel CMNCTRL2](../../visual-cpp-samples.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](cwnd-class.md)<br/>
[CButton-Klasse](cbutton-class.md)<br/>
[CComboBox-Klasse](ccombobox-class.md)<br/>
[CListBox-Klasse](clistbox-class.md)<br/>
[CScrollBar-Klasse](cscrollbar-class.md)<br/>
[CStatic-Klasse](cstatic-class.md)<br/>
[CDialog-Klasse](cdialog-class.md)
