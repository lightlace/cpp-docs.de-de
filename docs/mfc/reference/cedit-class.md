---
title: CEdit Class | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- separators, in multiline edit controls
- text editors
- controls [MFC], edit
- text editors, CEdit class
- edit controls, classes
- multiline edit control
- CEdit class
- line separators in multiline edit controls
- edit controls
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
caps.latest.revision: 22
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
ms.openlocfilehash: 9c782e77b1fdb9026ee030238413955ba4d537e9
ms.lasthandoff: 02/24/2017

---
# <a name="cedit-class"></a>CEdit Class
Stellt die Funktionalität eines Windows-Bearbeitungssteuerelements bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CEdit : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEdit::CEdit](#cedit)|Erstellt eine `CEdit` Steuerelementobjekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CEdit::CanUndo](#canundo)|Bestimmt, ob ein Bearbeitungssteuerelement Vorgang rückgängig gemacht werden kann.|  
|[CEdit::CharFromPos](#charfrompos)|Ruft die Zeilen- und Indizes für das Zeichen am nächsten an eine angegebene Position ab.|  
|[CEdit::Clear](#clear)|Löscht (deaktiviert) steuern, die aktuelle Auswahl (sofern vorhanden) bearbeiten.|  
|[CEdit::Copy](#copy)|Kopiert die aktuelle Auswahl (sofern vorhanden) in der Edit-Steuerelement in die Zwischenablage **CF_TEXT** Format.|  
|[CEdit::Create](#create)|Erstellt die Windows-Edit-Steuerelement und fügt es der `CEdit` Objekt.|  
|[CEdit::Cut](#cut)|Löscht (Teilstücke) steuern, die aktuelle Auswahl (sofern vorhanden) bearbeiten und den gelöschten Text in die Zwischenablage kopiert **CF_TEXT** Format.|  
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|Setzt (löscht) das Flag zum Rückgängigmachen einer Bearbeitung-Steuerelement zurück.|  
|[CEdit::FmtLines](#fmtlines)|Legt die Aufnahme der vorläufigen Zeilenumbruchzeichen ein- oder ausschalten in einem mehrzeiligen Edit-Steuerelement fest.|  
|[CEdit::GetCueBanner](#getcuebanner)|Ruft den Text ab, der angezeigt wird, als Text Cue oder Tipp, in einem Bearbeitungssteuerelement, wenn das Steuerelement leer ist und nicht den Fokus besitzt.|  
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|Bestimmt die oberste sichtbare Zeile in einem Bearbeitungssteuerelement.|  
|[CEdit::GetHandle](#gethandle)|Ruft ein Handle für den Speicher, der derzeit für eine mehrzeilige Edit-Steuerelement zugeordnet ist.|  
|[CEdit::GetHighlight](#gethighlight)|Ruft die Indizes der Start- und Endzeichen in einem Bereich von Text, der in der aktuellen Edit-Steuerelement hervorgehoben ist.|  
|[CEdit::GetLimitText](#getlimittext)|Ruft der maximale Größe des Texts dies `CEdit` enthalten können.|  
|[CEdit::GetLine](#getline)|Ruft eine Textzeile aus einem Edit-Steuerelement ab.|  
|[CEdit::GetLineCount](#getlinecount)|Ruft die Anzahl der Zeilen in einem mehrzeiligen Bearbeitungssteuerelement ab.|  
|[CEdit::GetMargins](#getmargins)|Ruft den linken und rechten Rand für `CEdit`.|  
|[CEdit::GetModify](#getmodify)|Bestimmt, ob der Inhalt des Edit-Steuerelements geändert wurde.|  
|[CEdit::GetPasswordChar](#getpasswordchar)|Ruft das Kennwortzeichen in einem Bearbeitungssteuerelement angezeigt wird, wenn der Benutzer Text eingibt.|  
|[CEdit::GetRect](#getrect)|Ruft die Formatierung Rechteck ein Edit-Steuerelement ab.|  
|[CEdit::GetSel](#getsel)|Ruft die Positionen der erste und letzte Zeichen der aktuellen Auswahl in einem Bearbeitungssteuerelement ab.|  
|[CEdit::HideBalloonTip](#hideballoontip)|Blendet alle SprechblasenInfo aktuelle Bearbeitungssteuerelement zugeordnet.|  
|[CEdit::LimitText](#limittext)|Begrenzt die Länge des Texts, die der Benutzer in ein Bearbeitungssteuerelement eingeben können.|  
|[CEdit::LineFromChar](#linefromchar)|Ruft die Zeilennummer der Zeile, die den angegebenen Zeichenindex enthält.|  
|[CEdit::LineIndex](#lineindex)|Ruft den Zeichenindex einer Zeile in einem mehrzeiligen Bearbeitungssteuerelement ab.|  
|[CEdit::LineLength](#linelength)|Ruft die Länge einer Zeile in einem Bearbeitungssteuerelement ab.|  
|[CEdit::LineScroll](#linescroll)|Führt einen Bildlauf durch den Text eines mehrzeiligen Edit-Steuerelements.|  
|[CEdit::Paste](#paste)|Die Daten aus der Zwischenablage in das Bearbeitungssteuerelement an der Cursorposition eingefügt. Daten werden eingefügt, nur dann, wenn Daten in die Zwischenablage enthält, **CF_TEXT** Format.|  
|[CEdit::PosFromChar](#posfromchar)|Ruft die Koordinaten der oberen linken Ecke des angegebenen Zeichenindex ab.|  
|[CEdit::ReplaceSel](#replacesel)|Ersetzt die aktuelle Auswahl in einem Edit-Steuerelement mit dem angegebenen Text.|  
|[CEdit::SetCueBanner](#setcuebanner)|Legt den Text, der angezeigt wird, als Text Cue oder Tipp, in einem Bearbeitungssteuerelement, wenn das Steuerelement leer ist und nicht den Fokus besitzt.|  
|[CEdit::SetHandle](#sethandle)|Legt das Handle in der lokalen Speicher, der von einem mehrzeilige Edit-Steuerelement verwendet wird.|  
|[CEdit::SetHighlight](#sethighlight)|Bearbeitungssteuerelement für Highlights ein Textbereich, der in der aktuellen angezeigt wird.|  
|[CEdit::SetLimitText](#setlimittext)|Legt der maximale Größe des Texts dies `CEdit` enthalten können.|  
|[CEdit::SetMargins](#setmargins)|Legt den linken und rechten Rand für dieses `CEdit`.|  
|[CEdit::SetModify](#setmodify)|Aktiviert oder deaktiviert das Flag Änderung für ein Bearbeitungssteuerelement.|  
|[CEdit::SetPasswordChar](#setpasswordchar)|Legt fest oder entfernt ein Kennwortzeichen in einem Bearbeitungssteuerelement angezeigt wird, wenn der Benutzer Text eingibt.|  
|[CEdit::SetReadOnly](#setreadonly)|Legt den schreibgeschützten Zustand eines Steuerelements bearbeiten.|  
|[CEdit::SetRect](#setrect)|Legt die Formatierung Rechteck mehrzeilige Bearbeitungssteuerelemente und aktualisiert das Steuerelement.|  
|[CEdit::SetRectNP](#setrectnp)|Legt die Formatierung Rechteck mehrzeilige Bearbeitungssteuerelemente ohne Neuzeichnen das Steuerelementfenster fest.|  
|[CEdit::SetSel](#setsel)|Wählt einen Bereich von Zeichen in einem Bearbeitungssteuerelement.|  
|[CEdit::SetTabStops](#settabstops)|Legt in einer mehrzeiligen Tabstopps Bearbeitungssteuerelement.|  
|[CEdit::ShowBalloonTip](#showballoontip)|Zeigt eine SprechblasenInfo, die das aktuelle Edit-Steuerelement zugeordnet ist.|  
|[CEdit::Undo](#undo)|Kehrt die letzten Bearbeitungssteuerelement Vorgang.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Edit-Steuerelement ist ein rechteckiges untergeordnete Fenster in dem der Benutzer Text eingeben kann.  
  
 Sie können ein Edit-Steuerelement aus einer Dialogfeldvorlage oder direkt im Code erstellen. In beiden Fällen rufen Sie zuerst den Konstruktor `CEdit` zum Erstellen der `CEdit` -Objekt, und rufen Sie dann die [erstellen](#create) Member-Funktion zum Erstellen der Windows-edit-Steuerelement und fügen Sie es auf die `CEdit` Objekt.  
  
 Konstruktion kann ein langwieriger Vorgang in einer abgeleiteten Klasse `CEdit`. Schreiben Sie einen Konstruktor für die abgeleitete Klasse und rufen **erstellen** von innerhalb des Konstruktors.  
  
 `CEdit`wichtige Funktionen von erbt `CWnd`. Festlegen und Abrufen von Text aus einer `CEdit` Objekt, verwenden Sie die `CWnd` Memberfunktionen [SetWindowText](cwnd-class.md#setwindowtext) und [GetWindowText](cwnd-class.md#getwindowtext), das Festlegen oder Abrufen von den gesamten Inhalt der ein Bearbeitungssteuerelement, auch wenn es sich um ein mehrzeiliges Steuerelement handelt. Textzeilen in einem mehrzeiligen Steuerelement werden durch '\r\n' Zeichenfolgen getrennt. Außerdem ist ein Bearbeitungssteuerelement mehrzeiliger, abrufen und festlegen Teil der Text des Steuerelements durch Aufrufen der `CEdit` Memberfunktionen [GetLine](#getline), [Memberfunktion SetSel](#setsel), [Memberfunktion GetSel](#getsel), und [ReplaceSel](#replacesel).  
  
 Wenn Sie ein Edit-Steuerelement an sein übergeordnetes Element per Windows-Benachrichtigung behandeln möchten (in der Regel eine abgeleitete Klasse `CDialog`), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag und Meldungshandler Memberfunktion hinzugefügt.  
  
 Jede Meldungszuordnungseintrags hat das folgende Format:  
  
 **ON_**Benachrichtigung **(** *-Id, MemberFxn***)**  
  
 wobei `id` gibt die untergeordneten Fenster-ID des Bearbeitungssteuerelements Senden der Benachrichtigung und `memberFxn` ist der Name der übergeordneten Member-Funktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.  
  
 Das übergeordnete Funktionsprototyp lautet wie folgt:  
  
 **Afx_msg** void MemberFxn **();**  
  
 Es folgt eine Liste der möglichen Meldungszuordnungseinträge und eine Beschreibung der Fälle, in denen sie an das übergeordnete Element gesendet werden:  
  
- **ON_EN_CHANGE** der Benutzer eine Aktion, die möglicherweise, Text in einem Bearbeitungssteuerelement geändert übernommen hat. Im Gegensatz zu den **EN_UPDATE** -Nachricht, diese Benachrichtigung wird gesendet, nachdem Windows die Anzeige aktualisiert.  
  
- **ON_EN_ERRSPACE** das Edit-Steuerelement kann nicht genügend Speicher um eine bestimmte Anforderung zu erfüllen.  
  
- **ON_EN_HSCROLL** der Benutzer klickt ein Bearbeitungssteuerelement horizontale Bildlaufleiste angezeigt. Das übergeordnete Fenster wird benachrichtigt, bevor der Bildschirm aktualisiert wird.  
  
- **ON_EN_KILLFOCUS** das Edit-Steuerelement den Eingabefokus verliert.  
  
- **ON_EN_MAXTEXT** der aktuelle Einfügemarke hat die angegebene Anzahl von Zeichen für das Bearbeitungssteuerelement überschritten und wurde abgeschnitten. Auch gesendet, wenn ein Bearbeitungssteuerelement keinen der **ES_AUTOHSCROLL** Stil und die Anzahl der einzufügenden Zeichen übersteigt die Breite des Bearbeitungssteuerelements. Auch gesendet, wenn ein Bearbeitungssteuerelement keinen der **ES_AUTOVSCROLL** Stil und die Gesamtzahl der Zeilen, die durch eine Einfügemarke übersteigt die Höhe des Bearbeitungssteuerelements.  
  
- **ON_EN_SETFOCUS** gesendet, wenn ein Edit-Steuerelement den Eingabefokus erhält.  
  
- **ON_EN_UPDATE** das Bearbeitungssteuerelement geänderten Text angezeigt wird. Gesendet, nachdem das Steuerelement den Text formatiert hat, aber bevor sie den Text Bildschirme, sodass die Fenstergröße geändert werden kann, falls erforderlich.  
  
- **ON_EN_VSCROLL** der Benutzer klickt ein Bearbeitungssteuerelement vertikale Bildlaufleiste angezeigt. Das übergeordnete Fenster wird benachrichtigt, bevor der Bildschirm aktualisiert wird.  
  
 Bei der Erstellung einer `CEdit` Objekt in einem Dialogfeld der `CEdit` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Bei der Erstellung einer `CEdit` Objekt aus einer Ressource mit dem Dialog-Editor das `CEdit` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie erstellen ein `CEdit` -Objekt innerhalb eines Fensters müssen Sie möglicherweise auch zerstört. Bei der Erstellung der `CEdit` Objekt auf dem Stapel automatisch zerstört wird. Bei der Erstellung der `CEdit` Objekt auf dem Heap mithilfe der **neue** -Funktion, die Sie aufrufen müssen **löschen** edit-Steuerelement auf das Objekt, das es zerstört, wenn der Benutzer Windows beendet wird. Wenn Sie alle in Speicher der `CEdit` Objekt, das Überschreiben der `CEdit` Destruktor, um die Zuordnung zu entfernen.  
  
 So ändern Sie bestimmte Formatvorlagen in einem Bearbeitungssteuerelement (z. B. **ES_READONLY**) müssen Sie bestimmte Nachrichten senden, auf das Steuerelement anstelle von [ModifyStyle](cwnd-class.md#modifystyle). Finden Sie unter [bearbeiten Steuerelementtypen](http://msdn.microsoft.com/library/windows/desktop/bb775464) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zu `CEdit` finden Sie unter:  
  
- [Steuerelemente](../../mfc/controls-mfc.md)  
  
-   Knowledge Base-Artikel Q259949: INFO: SetCaretPos() ist keine geeignete CEdit oder CRichEditCtrl-Steuerelemente  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 `CEdit`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="canundo"></a>CEdit::CanUndo  
 Rufen Sie diese Funktion, um zu bestimmen, ob die letzte Bearbeitung rückgängig gemacht werden kann.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn die letzte Bearbeitung durch einen Aufruf von rückgängig gemacht werden kann die **Rückgängig** Memberfunktion; 0, wenn es nicht rückgängig gemacht werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::Undo](#undo).  
  
##  <a name="cedit"></a>CEdit::CEdit  
 Erstellt ein `CEdit`-Objekt.  
  
```  
CEdit();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwendung [erstellen](#create) zum Erstellen der Windows-edit-Steuerelement.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#1;](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]  
  
##  <a name="charfrompos"></a>CEdit::CharFromPos  
 Rufen Sie diese Funktion zum Abrufen von nullbasierte Position und Zeichen Indizes des Zeichens am angegebenen Punkt in dieser nächsten `CEdit` Steuerelement  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pt`  
 Die Koordinaten eines Punkts in den Clientbereich dieses `CEdit` Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeichenindex in die untere **WORD**, und der Zeilenindex in die höherwertigen **WORD**.  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Memberfunktion ist ab Windows 95 und Windows NT 4.0 verfügbar.  
  
 Weitere Informationen finden Sie unter [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&3;](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]  
  
##  <a name="clear"></a>CEdit::Clear  
 Mit dieser Funktion können (clear) die aktuelle Auswahl im Bearbeitungssteuerelement (sofern vorhanden) löschen.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Löschen von ausgeführten **löschen** rückgängig gemacht werden können, durch Aufrufen der [rückgängig machen](#undo) Member-Funktion.  
  
 Um die aktuelle Auswahl löschen, und fügen Sie den gelöschten Inhalt in die Zwischenablage, rufen Sie die [Ausschneiden](#cut) Member-Funktion.  
  
 Weitere Informationen finden Sie unter [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&4;](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]  
  
##  <a name="copy"></a>CEdit::Copy  
 Rufen Sie diese Funktion zum Kopieren der aktuellen Auswahl (sofern vorhanden) in der Edit-Steuerelement in die Zwischenablage **CF_TEXT** Format.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&5;](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]  
  
##  <a name="create"></a>CEdit::Create  
 Erstellt die Windows-Edit-Steuerelement und fügt es der `CEdit` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Bearbeitungssteuerelement-Stil. Wenden Sie eine beliebige Kombination von [Bearbeiten von Stilen](edit-styles.md) an das Steuerelement.  
  
 `rect`  
 Gibt des Bearbeitungssteuerelements Größe und Position. Kann ein `CRect` Objekt oder `RECT` Struktur.  
  
 `pParentWnd`  
 Gibt an, das Steuerelement zum Bearbeiten des übergeordneten Fensters (in der Regel eine `CDialog`). Er darf nicht sein **NULL**.  
  
 `nID`  
 Gibt das Edit-Steuerelement-ID an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CEdit` Objekt in zwei Schritten. Zunächst rufen die `CEdit` Konstruktor und rufen Sie dann **erstellen**, die das Windows-Edit-Steuerelement erstellt, und fügt es der `CEdit` Objekt.  
  
 Wenn **erstellen** ausgeführt wird, sendet Windows die [WM_NCCREATE](http://msdn.microsoft.com/library/windows/desktop/ms632635), [WM_NCCALCSIZE](http://msdn.microsoft.com/library/windows/desktop/ms632634), [WM_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619), und [WM_GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626) Nachrichten an das Steuerelement zum Bearbeiten.  
  
 Diese Nachrichten werden standardmäßig verarbeitet die [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate), und [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standardbehandlung für die Nachricht zu erweitern, leiten Sie eine Klasse von `CEdit`, Hinzufügen einer Nachricht Zuordnung zu der neuen Klasse und überschreiben Sie die oben genannten Message-Handler-Memberfunktionen. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für die neue Klasse.  
  
 Übernehmen Sie das folgende [Fensterstile](window-styles.md) Kombinationsfeld.  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
- **WS_TABSTOP** Edit-Steuerelement in der Tabulatorreihenfolge einschließen  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#2;](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]  
  
##  <a name="cut"></a>CEdit::Cut  
 Rufen Sie diese Funktion zum Löschen (Ausschneiden) die aktuelle Auswahl (sofern vorhanden) in das Steuerelement zum Bearbeiten und den gelöschten Text in die Zwischenablage kopieren **CF_TEXT** Format.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Löschen von ausgeführten **Ausschneiden** rückgängig gemacht werden können, durch Aufrufen der [rückgängig machen](#undo) Member-Funktion.  
  
 Aufrufen, um die aktuelle Auswahl löschen, ohne den gelöschten Text in die Zwischenablage, die [löschen](#clear) Member-Funktion.  
  
 Weitere Informationen finden Sie unter [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&6;](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]  
  
##  <a name="emptyundobuffer"></a>CEdit::EmptyUndoBuffer  
 Rufen Sie diese Funktion zum Zurücksetzen (löschen) das Flag zum Rückgängigmachen des ein Edit-Steuerelement.  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>Hinweise  
 Das Edit-Steuerelement werden kann nicht den letzten Vorgang rückgängig machen. Die rückgängig-Flag wird festgelegt, wenn ein Vorgang innerhalb der Edit-Steuerelement rückgängig gemacht werden kann.  
  
 Das Flag "Rückgängig" wird automatisch gelöscht, wenn die [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) oder [SetHandle](#sethandle) `CWnd` Memberfunktionen aufgerufen werden.  
  
 Weitere Informationen finden Sie unter [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#7;](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]  
  
##  <a name="fmtlines"></a>CEdit::FmtLines  
 Rufen Sie diese Funktion, um die Aufnahme der vorläufigen Zeilenumbruchzeichen in einem mehrzeiligen Bearbeitungssteuerelement on oder off festgelegt.  
  
```  
BOOL FmtLines(BOOL bAddEOL);
```  
  
### <a name="parameters"></a>Parameter  
 *bAddEOL*  
 Gibt an, ob soft Zeilenumbruchzeichen eingefügt werden. Der Wert **TRUE** fügt die Zeichen; der Wert **FALSE** entfernt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn Formatierung auftritt. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein weichen Zeilenumbruch besteht aus zwei Wagenrückläufe und einen Zeilenvorschub am Ende einer Zeile, die fehlerhafte Zeilenumbruch eingefügt. Ein Zeilenumbruch Festplatte besteht aus einem Wagenrücklauf und ein Zeilenvorschub. Zeilen, die mit einer Absatzmarke einzufügen sind nicht betroffen `FmtLines`.  
  
 Windows wird nur reagiert, wenn die `CEdit` -Objekt ist ein mehrzeiliger Edit-Steuerelement.  
  
 `FmtLines`wirkt sich nur auf die zurückgegebene Puffer [GetHandle](#gethandle) und der zurückgegebene Text [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627). Es hat keine Auswirkung auf die Anzeige des Texts im Steuerelement bearbeiten.  
  
 Weitere Informationen finden Sie unter [EM_FMTLINES](http://msdn.microsoft.com/library/windows/desktop/bb761570) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#8;](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]  
  
##  <a name="getcuebanner"></a>CEdit::GetCueBanner  
 Ruft den Text ab, der angezeigt wird, als Text Cue oder Tipp, in einem Bearbeitungssteuerelement, wenn das Steuerelement leer ist.  
  
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
 Die Anzahl der Zeichen, die empfangen werden kann. Hierzu zählen auch das Beenden des `NULL` Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Für die erste Überladung `true` , wenn die Methode erfolgreich; andernfalls ist `false`.  
  
 Für die zweite Überladung eine [CString](../../atl-mfc-shared/using-cstring.md) , die den Hinweistext enthält, wenn die Methode erfolgreich; andernfalls ist, die leere Zeichenfolge ("").  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [EM_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761572) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen finden Sie unter der [Edit_GetCueBannerText](http://msdn.microsoft.com/library/windows/desktop/bb761695) Makro.  
  
##  <a name="getfirstvisibleline"></a>CEdit::GetFirstVisibleLine  
 Rufen Sie diese Funktion, um zu bestimmen, die oberste sichtbare Zeile in einem Bearbeitungssteuerelement.  
  
```  
int GetFirstVisibleLine() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der obersten sichtbaren Zeile. Für einzeilige Edit-Steuerelemente ist der Rückgabewert 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#9;](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]  
  
##  <a name="gethandle"></a>CEdit::GetHandle  
 Rufen Sie diese Funktion, um ein Handle für ein mehrzeiliges Bearbeitungssteuerelement derzeit belegte Speicherplatz.  
  
```  
HLOCAL GetHandle() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein lokaler Speicher-Handle, das den Puffer, der den Inhalt des Bearbeitungssteuerelements identifiziert. Wenn ein Fehler auftritt, z. B. das Senden von Nachrichten an eine einzeilige Bearbeitungssteuerelement, ist der Rückgabewert 0.  
  
### <a name="remarks"></a>Hinweise  
 Das Handle ist ein lokaler Speicher-Handle und kann verwendet werden, von jedem der **lokale** Windows-Speicher-Funktionen, die einen lokalen Speicher verwenden zu behandeln, als Parameter.  
  
 **GetHandle** nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet wird.  
  
 Rufen Sie **GetHandle** für eine mehrzeilige Edit-Steuerelement in einem Dialogfeld nur, wenn das Dialogfeld mit erstellt wurde der **DS_LOCALEDIT** style-Flag festgelegt. Wenn die **DS_LOCALEDIT** Style nicht festgelegt ist, erhalten Sie weiterhin einen Wert ungleich NULL, aber Sie sind nicht in der Lage, den zurückgegebenen Wert verwenden.  
  
> [!NOTE]
> **GetHandle** funktioniert nicht mit Windows 95/98. Wenn Sie aufrufen **GetHandle** in Windows 95/98 wird zurückgegeben, **NULL**. **GetHandle** funktioniert wie beschrieben unter Windows NT, Version 3.51 und höher.  
  
 Weitere Informationen finden Sie unter [EM_GETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761576) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#10;](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]  
  
##  <a name="gethighlight"></a>CEdit::GetHighlight  
 Ruft die Indizes der ersten und letzten Zeichen in einem Bereich von Text, der in der aktuellen Edit-Steuerelement hervorgehoben ist.  
  
```  
BOOL GetHighlight(
    int* pichStart,   
    int* pichEnd) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `pichStart`|Nullbasierte Index des ersten Zeichens in den Textbereich, der hervorgehoben ist.|  
|[out] `pichEnd`|Nullbasierte Index des letzten Zeichens in den Textbereich, der hervorgehoben ist.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [EM_GETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761578) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getlimittext"></a>CEdit::GetLimitText  
 Rufen Sie diese Memberfunktion zum Abrufen des Text-Grenzwert für diesen `CEdit` Objekt.  
  
```  
UINT GetLimitText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Text Grenze in Bytes, der für diese `CEdit` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Der Text-Grenzwert wird die maximale Größe des Textes in Bytes, der das Bearbeitungssteuerelement annehmen kann.  
  
> [!NOTE]
>  Diese Memberfunktion ist ab Windows 95 und Windows NT 4.0 verfügbar.  
  
 Weitere Informationen finden Sie unter [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#11;](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]  
  
##  <a name="getline"></a>CEdit::GetLine  
 Mit dieser Funktion können Sie eine Textzeile aus einem Edit-Steuerelement abzurufen, und platziert es in `lpszBuffer`.  
  
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
 Gibt die Nummer der Zeile aus einer mehrzeiligen Abrufen edit-Steuerelement. Zeilennummern sind nullbasiert. der Wert 0 gibt die erste Zeile. Dieser Parameter wird von einem einzeiligen Edit-Steuerelement ignoriert.  
  
 `lpszBuffer`  
 Verweist auf den Puffer, der eine Kopie der Zeile empfängt. Das erste Wort des Puffers muss die maximale Anzahl von Zeichen angeben, die in den Puffer kopiert werden können.  
  
 `nMaxLength`  
 Gibt die maximale Anzahl von Bytes, die in den Puffer kopiert werden können. `GetLine`Schreibt diesen Wert in das erste Wort `lpszBuffer` vor dem Aufruf von Windows.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der tatsächlich kopierten Bytes. Der Rückgabewert ist 0, wenn die Nummer der Zeile angegeben `nIndex` ist größer als die Anzahl der Zeilen im Bearbeitungssteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Die kopierte Zeile enthält einen Null-Terminierungszeichen nicht.  
  
 Weitere Informationen finden Sie unter [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>CEdit::GetLineCount  
 Rufen Sie diese Funktion, um die Anzahl der Zeilen in einem mehrzeiligen Bearbeitungssteuerelement ab.  
  
```  
int GetLineCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die Anzahl der Zeilen in der mehrzeilige edit-Steuerelement. Wenn kein Text in das Bearbeitungssteuerelement eingegeben wurde, ist der Rückgabewert 1.  
  
### <a name="remarks"></a>Hinweise  
 `GetLineCount`wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet werden.  
  
 Weitere Informationen finden Sie unter [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#12;](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]  
  
##  <a name="getmargins"></a>CEdit::GetMargins  
 Rufen Sie diese Memberfunktion zum Abrufen der linken und rechten Rand des Bearbeitungssteuerelements.  
  
```  
DWORD GetMargins() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite des linken Rands in die untere **WORD** und die Breite des rechten Rands in die höherwertigen **WORD**.  
  
### <a name="remarks"></a>Hinweise  
 Ränder werden in Pixel gemessen.  
  
> [!NOTE]
>  Diese Memberfunktion ist ab Windows 95 und Windows NT 4.0 verfügbar.  
  
 Weitere Informationen finden Sie unter [EM_GETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761590) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="getmodify"></a>CEdit::GetModify  
 Rufen Sie diese Funktion, um zu bestimmen, ob der Inhalt des Edit-Steuerelements geändert wurde.  
  
```  
BOOL GetModify() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Inhalt des Bearbeitungssteuerelements geändert wurden; 0, wenn sie geblieben unverändert.  
  
### <a name="remarks"></a>Hinweise  
 Windows behält ein internes Flag gibt an, ob der Inhalt des Edit-Steuerelements geändert wurde. Dieses Flag wird gelöscht, wenn das Edit-Steuerelement erstellt wird, und möglicherweise auch, durch Aufrufen deaktiviert werden der [SetModify](#setmodify) Member-Funktion.  
  
 Weitere Informationen finden Sie unter [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#13;](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]  
  
##  <a name="getpasswordchar"></a>CEdit::GetPasswordChar  
 Rufen Sie diese Funktion, um das Kennwortzeichen abzurufen, das in einem Bearbeitungssteuerelement angezeigt wird, wenn der Benutzer Text eingibt.  
  
```  
TCHAR GetPasswordChar() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Zeichen und nicht die Zeichen angezeigt werden, die der Benutzer eingegeben. Der Rückgabewert ist `NULL` Falls kein Kennwortzeichen vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das Steuerelement zum Bearbeiten mit Erstellen der **ES_PASSWORD** Stil, die DLL, die das Steuerelement unterstützt die Standard-Kennwortzeichen bestimmt. Das Manifest oder [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) Methode bestimmt, welche die DLL unterstützt das Steuerelement zum Bearbeiten. Wenn "User32.dll" Edit-Steuerelement unterstützt, ist die Standard-Kennwortzeichen Sternchen ("*", U +&002;A). Wenn comctl32.dll, Version 6 der Edit-Steuerelement unterstützt, ist das Standardzeichen SCHWARZER Kreis ('●', U + 25CF). Weitere Informationen zu der DLL und die Version unterstützt die allgemeine Steuerelemente finden Sie unter [Shell und allgemeine Steuerelemente Versionen](http://msdn.microsoft.com/library/windows/desktop/bb776779).  
  
 Diese Methode sendet die [EM_GETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761594) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&14;](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]  
  
##  <a name="getrect"></a>CEdit::GetRect  
 Rufen Sie diese Funktion, um die Formatierung Rechteck der Edit-Steuerelement abzurufen.  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf die `RECT` -Struktur, die die Formatierung Rechteck empfängt.  
  
### <a name="remarks"></a>Hinweise  
 Die Formatierung Rechteck ist der begrenzende Rechteck des Texts, die unabhängig von der Größe des Fensters bearbeiten-Steuerelement ist.  
  
 Die Formatierung Rechteck eines mehrzeiligen Edit-Steuerelements kann geändert werden, von der [SetRect](#setrect) und [SetRectNP](#setrectnp) Memberfunktionen.  
  
 Weitere Informationen finden Sie unter [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::LimitText](#limittext).  
  
##  <a name="getsel"></a>CEdit::GetSel  
 Rufen Sie diese Funktion, um die Start- und Endzeichen der aktuellen Auswahl (sofern vorhanden) in ein Bearbeitungssteuerelement, das über den Rückgabewert oder Parameter zu erhalten.  
  
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
 Verweis auf eine ganze Zahl, die die Position des ersten Zeichens nach dem Ende der aktuellen Auswahl nicht ausgewählten erhalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Version, die gibt eine `DWORD` gibt einen Wert, der die Anfangsposition in das niederwertige Wort und die Position des ersten Zeichens nicht ausgewählten nach dem Ende der Auswahl in das höherwertige Wort enthält.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_GETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761598) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#15;](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]  
  
##  <a name="hideballoontip"></a>CEdit::HideBalloonTip  
 Blendet alle SprechblasenInfo aktuelle Bearbeitungssteuerelement zugeordnet.  
  
```  
BOOL HideBalloonTip();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sendet die [EM_HIDEBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761604) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="limittext"></a>CEdit::LimitText  
 Rufen Sie diese Funktion, um die Länge des Texts zu beschränken, die der Benutzer in ein Bearbeitungssteuerelement eingeben kann.  
  
```  
void LimitText(int nChars = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nChars`  
 Gibt die Länge (in Byte) des Textes, den der Benutzer eingeben kann. Wenn dieser Parameter 0 ist, wird an die Textlänge festgelegt **UINT_MAX** Bytes. Dies ist das Standardverhalten.  
  
### <a name="remarks"></a>Hinweise  
 Ändern der Grenze Text schränkt nur den Text, den der Benutzer eingeben kann. Wirkt sich nicht auf einen beliebigen Text bereits in der Edit-Steuerelement, und beeinträchtigt die Länge des Texts auf das Steuerelement zum Bearbeiten von kopiert die [SetWindowText](cwnd-class.md#setwindowtext) -Memberfunktion `CWnd`. Wenn eine Anwendung verwendet die `SetWindowText` Funktion zum Platzieren von Text in ein Bearbeitungssteuerelement als im Aufruf angegeben ist `LimitText`, der Benutzer kann den Text im Steuerelement bearbeiten löschen. Der Text-Grenzwert wird verhindert, dass den Benutzer den vorhandenen Text durch neuen Text ersetzen jedoch, wenn die aktuelle Auswahl löschen, wird der Text unterhalb des Text-Limits liegen.  
  
> [!NOTE]
>  In Win32 (Windows NT und Windows 95/98), [SetLimitText](#setlimittext) wird diese Funktion ersetzt.  
  
 Weitere Informationen finden Sie unter [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&17;](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]  
  
##  <a name="linefromchar"></a>CEdit::LineFromChar  
 Rufen Sie diese Funktion, um die Zeilennummer der Zeile abzurufen, die den angegebenen Zeichenindex enthält.  
  
```  
int LineFromChar(int nIndex = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Indexwert für das gewünschte Zeichen im Text des Edit-Steuerelements, oder -1. Wenn `nIndex` ist-1, gibt die aktuelle Zeile, d. h. die Zeile, die die Einfügemarke enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Die nullbasierte Zeilennummer der Zeile mit den angegebenen Zeichenindex `nIndex`. Wenn `nIndex` –&1; ist, wird die Nummer der Zeile, die das erste Zeichen der Markierung enthält, wird zurückgegeben. Wenn keine Auswahl vorhanden ist, wird die aktuelle Zeilennummer zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Ein Zeichenindex ist die Anzahl der Zeichen vom Anfang des Bearbeitungssteuerelements.  
  
 Diese Member-Funktion wird nur von mehrzeiligen Bearbeitungssteuerelementen verwendet.  
  
 Weitere Informationen finden Sie unter [EM_LINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761609) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&18;](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]  
  
##  <a name="lineindex"></a>CEdit::LineIndex  
 Rufen Sie diese Funktion zum Abrufen des Zeichenindex einer Zeile in einem mehrzeiligen Edit-Steuerelement.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nLine`  
 Enthält den Indexwert für die gewünschte Position im Text des Edit-Steuerelements, oder -1. Wenn `nLine` ist-1, gibt die aktuelle Zeile, d. h. die Zeile, die die Einfügemarke enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Zeichenindex der Zeile im angegebenen `nLine` oder –&1;, wenn die angegebene Zeilennummer größer als die Anzahl der Zeilen in der Edit-Steuerelement ist.  
  
### <a name="remarks"></a>Hinweise  
 Der Zeichenindex ist die Anzahl der Zeichen vom Anfang des Bearbeitungssteuerelements in die angegebene Zeile.  
  
 Diese Member-Funktion wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 Weitere Informationen finden Sie unter [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit Nr.&19;](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]  
  
##  <a name="linelength"></a>CEdit::LineLength  
 Ruft die Länge einer Zeile in einem Bearbeitungssteuerelement ab.  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nLine`  
 Der nullbasierte Index eines Zeichens in der Zeile, deren Länge abgerufen werden sollen. Der Standardwert ist -1.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Rückgabewert ist die Länge für einzeilige Edit-Steuerelemente `TCHAR`s, der den Text im Bearbeitungssteuerelement.  
  
 Der Rückgabewert ist die Länge für mehrzeilige Bearbeitungssteuerelemente `TCHAR`s, der die angegebene Zeile der `nLine` Parameter. Für [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] Text, beträgt die Anzahl der Bytes in der Zeile, für Unicode-Text, wird die Länge der Anzahl der Zeichen in der Zeile. Die Länge schließt nicht die Zeichen Wagenrücklauf am Ende der Zeile.  
  
 Wenn der `nLine` Parameter ist größer als die Anzahl der Zeichen im Steuerelement, der Rückgabewert ist&0; (null).  
  
 Wenn der `nLine` Parameter ist&1;, der Rückgabewert ist die Anzahl der nicht ausgewählten Zeichen in den Zeilen, die ausgewählten Zeichen enthalten. Wenn die Markierung mit dem vierten Zeichen einer Zeile Zeichen am Ende der nächsten Zeile erstreckt, ist der Rückgabewert z. B. 10. D. h., drei Zeichen in der ersten Zeile und sieben auf der nächsten.  
  
 Weitere Informationen zu den `TCHAR` finden Sie unter der `TCHAR` Zeile in der Tabelle im [Windows Data Types](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird von unterstützt die [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::LineIndex](#lineindex).  
  
##  <a name="linescroll"></a>CEdit::LineScroll  
 Mit dieser Funktion wird den Text eines mehrzeiligen Bearbeitungssteuerelements einen Bildlauf durchführen.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nLines`  
 Gibt die Anzahl der Zeilen, um einen vertikalen Bildlauf ausführen.  
  
 `nChars`  
 Gibt die Anzahl von Zeichenpositionen einen horizontalen Bildlauf durchführen. Dieser Wert wird ignoriert, wenn das Bearbeitungssteuerelement entweder wurde der **ES_RIGHT** oder **ES_CENTER** Stil.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 Das Bearbeitungssteuerelement wird hinter der letzten Zeile des Texts im Bearbeitungssteuerelement kein vertikaler Bildlauf ausgeführt. Wenn die aktuelle zuzüglich der Anzahl der Zeilen, die durch angegebene Zeile `nLines` überschreitet die Gesamtanzahl der Zeilen im Bearbeitungssteuerelement, der Wert wird so angepasst, dass die letzte Zeile des Edit-Steuerelements an den Anfang des Fensters bearbeiten-Steuerelement ein Bildlauf durchgeführt wird.  
  
 `LineScroll`kann verwendet werden, um hinter dem letzten Zeichen des jede Zeile ein horizontaler Bildlauf durchgeführt.  
  
 Weitere Informationen finden Sie unter [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::GetFirstVisibleLine](#getfirstvisibleline).  
  
##  <a name="paste"></a>CEdit::Paste  
 Rufen Sie diese Funktion zum Einfügen von Daten aus der Zwischenablage in die `CEdit` an der Einfügemarke.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Hinweise  
 Daten werden eingefügt, nur dann, wenn Daten in die Zwischenablage enthält, **CF_TEXT** Format.  
  
 Weitere Informationen finden Sie unter [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&20;](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]  
  
##  <a name="posfromchar"></a>CEdit::PosFromChar  
 Rufen Sie diese Funktion zum Abrufen der Position (obere linke Ecke) eines bestimmten Zeichens in dieser `CEdit` Objekt.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nChar`  
 Der nullbasierte Index des angegebenen Zeichens.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Koordinaten der oberen linken Ecke des angegebenen Zeichens `nChar`.  
  
### <a name="remarks"></a>Hinweise  
 Das Zeichen wird durch die Vergabe des nullbasierte Indexwerts angegeben. Wenn `nChar` ist größer als der Index des letzten Zeichens in dieser `CEdit` -Objekt, gibt der Rückgabewert die Koordinaten der Position des Zeichens direkt nach dem letzten Zeichen in diesem `CEdit` Objekt.  
  
> [!NOTE]
>  Diese Memberfunktion ist ab Windows 95 und Windows NT 4.0 verfügbar.  
  
 Weitere Informationen finden Sie unter [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::LineFromChar](#linefromchar).  
  
##  <a name="replacesel"></a>CEdit::ReplaceSel  
 Mit dieser Funktion können Sie die aktuelle Auswahl in einem Bearbeitungssteuerelement mit den angegebenen Text ersetzt `lpszNewText`.  
  
```  
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszNewText`  
 Zeigt auf eine Null endende Zeichenfolge, die den Ersetzungstext enthält.  
  
 `bCanUndo`  
 Um anzugeben, dass diese Funktion rückgängig gemacht werden kann, legen Sie den Wert dieses Parameters auf **TRUE** . Der Standardwert ist **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Wird nur einen Teil des Texts in einem Bearbeitungssteuerelement ersetzt. Wenn Sie den gesamten Text ersetzen möchten, verwenden Sie die [CWnd::SetWindowText](cwnd-class.md#setwindowtext) Member-Funktion.  
  
 Wenn keine aktuelle Auswahl vorhanden ist, wird der Ersetzungstext an der aktuellen Cursorposition eingefügt.  
  
 Weitere Informationen finden Sie unter [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::LineIndex](#lineindex).  
  
##  <a name="setcuebanner"></a>CEdit::SetCueBanner  
 Legt den Text fest, der als das Stichwort Text angezeigt wird oder Tipp, in Bearbeitung steuern, wenn das Steuerelement leer ist.  
  
```  
BOOL SetCueBanner(LPCWSTR lpszText);

 
BOOL SetCueBanner(
    LPCWSTR lpszText,   
    BOOL fDrawWhenFocused = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszText`  
 Ein Zeiger auf eine Zeichenfolge, die das Stichwort in das Bearbeitungssteuerelement angezeigt.  
  
 [in] `fDrawWhenFocused`  
 Wenn `false`, das hinweisbanner wird nicht gezeichnet, wenn der Benutzer in der Edit-Steuerelement klickt und dem Steuerelement den Fokus gibt.  
  
 Wenn `true`, das hinweisbanner gezeichnet wird, auch wenn das Steuerelement den Fokus besitzt. Das hinweisbanner verschwindet, wenn der Benutzer beginnt, geben Sie in das Steuerelement.  
  
 Der Standardwert ist `false`.  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [EM_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761639) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen finden Sie unter der [Edit_SetCueBannerTextFocused](http://msdn.microsoft.com/library/windows/desktop/bb761703) Makro.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die [CEdit::SetCueBanner](#setcuebanner) Methode.  
  
 [!code-cpp[NVC_MFC_CEdit_s&#1;2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]  
  
##  <a name="sethandle"></a>CEdit::SetHandle  
 Rufen Sie diese Funktion, um das Handle zu dem lokalen Speicher festzulegen, die von einem mehrzeilige Edit-Steuerelement verwendet wird.  
  
```  
void SetHandle(HLOCAL hBuffer);
```  
  
### <a name="parameters"></a>Parameter  
 *hBuffer*  
 Enthält ein Handle für den lokalen Speicher. Dieses Handle muss durch einen vorherigen Aufruf von erstellt wurden die [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) Windows-Funktion verwendet die **LMEM_MOVEABLE** Flag. Der Arbeitsspeicher wird angenommen, dass eine Null-terminierte Zeichenfolge enthalten. Wenn dies nicht der Fall ist, sollte das erste Byte des reservierten Speichers auf 0 festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Steuerelement zum Bearbeiten klicken Sie dann verwendet diesen Puffer, um den aktuell angezeigten Text anstelle der Zuordnung eines eigenen Puffers speichern.  
  
 Diese Member-Funktion wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 Bevor eine Anwendung eine neue Speicherhandle festlegt, verwenden sie die [GetHandle](#gethandle) Memberfunktion, die das Handle an dem aktuellen Speicherpuffer abrufen und Freigeben von Arbeitsspeicher verwenden die **LocalFree** Windows-Funktion.  
  
 `SetHandle`Löscht den Rückgängigpuffer (der [CanUndo](#canundo) dann Member-Funktion gibt 0 zurück) und das interne Änderung-Flag (der [GetModify](#getmodify) dann Member-Funktion gibt 0 zurück). Das Fenster Edit-Steuerelement neu gezeichnet wird.  
  
 Können diese Memberfunktion in einer mehrzeiligen Edit-Steuerelement in einem Dialogfeld nur, wenn Sie das Dialogfeld erstellt haben die **DS_LOCALEDIT** style-Flag festgelegt.  
  
> [!NOTE]
> **GetHandle** funktioniert nicht mit Windows 95/98. Wenn Sie aufrufen **GetHandle** in Windows 95/98 wird zurückgegeben, **NULL**. **GetHandle** funktioniert wie beschrieben unter Windows NT, Version 3.51 und höher.  
  
 Weitere Informationen finden Sie unter [EM_SETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761641), [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), und [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#22;](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]  
  
##  <a name="sethighlight"></a>CEdit::SetHighlight  
 Bearbeitungssteuerelement für Highlights ein Textbereich, der in der aktuellen angezeigt wird.  
  
```  
void SetHighlight(
    int ichStart,   
    int ichEnd);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `ichStart`|Nullbasierte Index des ersten Zeichens in den Textbereich markieren.|  
|[in] `ichEnd`|Nullbasierte Index des letzten Zeichens in den Textbereich markieren.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [EM_SETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761643) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setlimittext"></a>CEdit::SetLimitText  
 Rufen Sie diese Memberfunktion zum Festlegen des Text-Grenzwert für diesen `CEdit` Objekt.  
  
```  
void SetLimitText(UINT nMax);
```  
  
### <a name="parameters"></a>Parameter  
 `nMax`  
 Der neue Text-Grenze, in Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Der Text-Grenzwert wird die maximale Größe des Textes in Zeichen ein, die Edit-Steuerelements annehmen kann.  
  
 Ändern der Grenze Text schränkt nur den Text, den der Benutzer eingeben kann. Wirkt sich nicht auf einen beliebigen Text bereits in der Edit-Steuerelement, und beeinträchtigt die Länge des Texts auf das Steuerelement zum Bearbeiten von kopiert die [SetWindowText](cwnd-class.md#setwindowtext) -Memberfunktion `CWnd`. Wenn eine Anwendung verwendet die `SetWindowText` Funktion zum Platzieren von Text in ein Bearbeitungssteuerelement als im Aufruf angegeben ist `LimitText`, der Benutzer kann den Text im Steuerelement bearbeiten löschen. Der Text-Grenzwert wird verhindert, dass den Benutzer den vorhandenen Text durch neuen Text ersetzen jedoch, wenn die aktuelle Auswahl löschen, wird der Text unterhalb des Text-Limits liegen.  
  
 Diese Funktion ersetzt [LimitText](#limittext) in Win32.  
  
 Weitere Informationen finden Sie unter [EM_SETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761647) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmargins"></a>CEdit::SetMargins  
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
>  Diese Memberfunktion ist ab Windows 95 und Windows NT 4.0 verfügbar.  
  
 Weitere Informationen finden Sie unter [EM_SETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761649) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmodify"></a>CEdit::SetModify  
 Rufen Sie diese Funktion zum Aktivieren bzw. deaktivieren Sie das geänderte Flag für ein Bearbeitungssteuerelement.  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bModified`  
 Der Wert **TRUE** gibt an, dass der Text geändert wurde, und den Wert **FALSE** gibt an, dass es nicht geändert. Standardmäßig wird das geänderte Flag festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Das geänderte Flag gibt an, ob der Text im Bearbeitungssteuerelement geändert wurde. Es wird automatisch festgelegt, wenn der Benutzer den Text ändert. Der Wert kann abgerufen werden, mit der [GetModify](#getmodify) Member-Funktion.  
  
 Weitere Informationen finden Sie unter [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::GetModify](#getmodify).  
  
##  <a name="setpasswordchar"></a>CEdit::SetPasswordChar  
 Rufen Sie diese Funktion zum Festlegen oder entfernen ein Kennwortzeichen in einem Bearbeitungssteuerelement angezeigt wird, wenn der Benutzer Text eingibt.  
  
```  
void SetPasswordChar(TCHAR ch);
```  
  
### <a name="parameters"></a>Parameter  
 *CH*  
 Gibt das Zeichen anstelle der vom Benutzer eingegebenen Zeichen angezeigt werden. Wenn *ch* ist 0, die vom Benutzer eingegebenen Zeichen angezeigt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Kennwortzeichen ein festgelegt ist, wird dieses Zeichen angezeigt, für jedes Zeichen der Benutzer eingibt.  
  
 Diese Memberfunktion wirkt sich nicht auf einer mehrzeiligen Steuerelement zu bearbeiten.  
  
 Wenn die `SetPasswordChar` -Memberfunktion aufgerufen wird, `CEdit` wird neu gezeichnet, alle sichtbar, mit dem angegebenen Zeichen *ch*.  
  
 Wenn das Edit-Steuerelement erstellt wird, mit der [ES_PASSWORD](edit-styles.md) Format, das Standard-Kennwortzeichen auf ein Sternchen festgelegt ( ** \* **). Dieses Format wird entfernt, wenn `SetPasswordChar` aufgerufen wird und *ch* auf 0 festgelegt.  
  
 Weitere Informationen finden Sie unter [EM_SETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761653) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit Nr.&16;](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]  
  
##  <a name="setreadonly"></a>CEdit::SetReadOnly  
 Ruft diese Funktion zum Festlegen des schreibgeschützten Status eines Steuerelements bearbeiten.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bReadOnly`  
 Gibt an, ob festlegen oder entfernen den schreibgeschützten Zustand des Bearbeitungssteuerelements. Der Wert **TRUE** legt den Zustand schreibgeschützt, der Wert **FALSE** legt den Zustand Lese-/Schreibzugriff.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich ist, oder 0, wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Die aktuelle Einstellung finden Sie durch Testen der [ES_READONLY](edit-styles.md) -Flag in den Rückgabewert der [CWnd::GetStyle](cwnd-class.md#getstyle).  
  
 Weitere Informationen finden Sie unter [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&23;](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]  
  
##  <a name="setrect"></a>CEdit::SetRect  
 Rufen Sie diese Funktion, um die Dimensionen eines Rechtecks mit den angegebenen Koordinaten festgelegt.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf die `RECT` Struktur oder `CRect` Objekt, das die neuen Werte für die Formatierung Rechteck angibt.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Member wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 Verwendung `SetRect` zum Festlegen der Formatierung Rechteck eine mehrzeilige edit-Steuerelement. Die Formatierung Rechteck ist der begrenzende Rechteck des Texts, die unabhängig von der Größe des Fensters bearbeiten-Steuerelement ist. Wenn das Edit-Steuerelement erstellt wird, entspricht die Formatierung Rechteck Clientbereich des Fensters bearbeiten-Steuerelement. Mithilfe der `SetRect` Member-Funktion einer Anwendung kann, die Formatierung Rechteck größer oder kleiner als das Bearbeitungssteuerelement Fenster.  
  
 Weist das Steuerelement zum Bearbeiten keine Bildlaufleiste, wird Text abgeschnitten nicht umschlossen, erfolgt die Formatierung Rechteck größer als das Fenster. Wenn das Steuerelement zum Bearbeiten ein Rahmens enthält, wird die Formatierung Rechteck durch die Größe des Rahmens reduziert. Wenn Sie das von zurückgegebene Rechteck Anpassen der `GetRect` -Memberfunktion, müssen Sie die Größe des Rahmens entfernen, bevor Sie das Rechteck übergeben `SetRect`.  
  
 Wenn `SetRect` aufgerufen wird, wird das Steuerelement zum Bearbeiten der Text ebenfalls erneut formatiert und erneut angezeigt.  
  
 Weitere Informationen finden Sie unter [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#24;](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]  
  
##  <a name="setrectnp"></a>CEdit::SetRectNP  
 Rufen Sie diese Funktion, um die Formatierung Rechteck eines mehrzeiligen Edit-Steuerelements festzulegen.  
  
```  
void SetRectNP(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine `RECT` Struktur oder `CRect` Objekt, das die neuen Werte für das Rechteck angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Formatierung Rechteck ist der begrenzende Rechteck des Texts, die unabhängig von der Größe des Fensters bearbeiten-Steuerelement ist.  
  
 `SetRectNP`ist identisch mit der `SetRect` Memberfunktion, mit der Ausnahme, dass das Bearbeitungssteuerelement Fenster nicht neu gezeichnet wird.  
  
 Wenn das Edit-Steuerelement erstellt wird, entspricht die Formatierung Rechteck Clientbereich des Fensters bearbeiten-Steuerelement. Durch Aufrufen der `SetRectNP` Member-Funktion einer Anwendung kann, die Formatierung Rechteck größer oder kleiner als das Bearbeitungssteuerelement Fenster.  
  
 Weist das Steuerelement zum Bearbeiten keine Bildlaufleiste, wird Text abgeschnitten nicht umschlossen, erfolgt die Formatierung Rechteck größer als das Fenster.  
  
 Dieser Member wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 Weitere Informationen finden Sie unter [EM_SETRECTNP](http://msdn.microsoft.com/library/windows/desktop/bb761659) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::SetRect](#setrect).  
  
##  <a name="setsel"></a>CEdit::SetSel  
 Rufen Sie diese Funktion, um einen Bereich von Zeichen in einem Bearbeitungssteuerelement auszuwählen.  
  
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
 Gibt die Anfangsposition in das niederwertige Wort und die Endposition in das höherwertige Wort. Wenn das niederwertige Wort 0 ist, und das höherwertige Wort-1 ist, ist gesamten Text in der Edit-Steuerelement ausgewählt. Wenn das niederwertige Wort –&1; ist, ist aktuelle Auswahl entfernt.  
  
 *bNoScroll*  
 Gibt an, ob die Einfügemarke ein Bildlauf durchgeführt werden soll. Wenn **FALSE**, die Einfügemarke Bildlauf angezeigt. Wenn **TRUE**, die Einfügemarke nicht Bildlauf angezeigt.  
  
 `nStartChar`  
 Gibt die Position an. Wenn `nStartChar` ist 0 und `nEndChar` ist-1, alle der Text in der Edit-Steuerelement ausgewählt ist. Wenn `nStartChar` –&1; ist, ist aktuelle Auswahl wird entfernt.  
  
 `nEndChar`  
 Gibt die Endposition.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [EM_SETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761661) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEdit::GetSel](#getsel).  
  
##  <a name="settabstops"></a>CEdit::SetTabStops  
 Rufen Sie diese Funktion zum Festlegen von Tabstopps in einem mehrzeiligen Edit-Steuerelement.  
  
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
 Gibt die Anzahl der Tabstopps in enthaltenen `rgTabStops`. Diese Zahl muss größer als 1 sein.  
  
 `rgTabStops`  
 Verweist auf ein Array von Ganzzahlen ohne Vorzeichen, die Angabe der Registerkarte Tabstopps in Dialogeinheiten. Eine Dialogeinheit ist eine horizontale oder vertikale Abstand. Eine horizontale Dialogeinheit ein Viertel der aktuellen Dialogfeld Basis Breite Einheit entspricht, und 1 vertikale Dialogeinheit ein Achtel der aktuellen Dialogfeld Basis Höhe Einheit entspricht. Die Basis Dialogeinheiten werden basierend auf der Höhe und Breite des aktuellen Systemschriftart berechnet. Die **GetDialogBaseUnits** Windows-Funktion gibt das aktuelle Dialogfeld Basiseinheit in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Registerkarten festgelegt wurden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Text in ein mehrzeiliges Bearbeitungssteuerelement kopiert wird, bewirkt Tabstoppzeichen im Text Leerzeichen bis zum nächsten Tabstopp generiert werden.  
  
 Rufen Sie zum Festlegen von Tabstopps auf die Standardgröße von 32 Dialogeinheiten der parameterlosen Version von dieser Memberfunktion. Um eine andere Größe als 32 Tabstopps festzulegen, rufen Sie die Version mit der `cxEachStop` Parameter. Um ein Array von Größen Tabstopps festzulegen, verwenden Sie die Version mit zwei Parametern.  
  
 Diese Member-Funktion wird nur von mehrzeiligen Bearbeitungssteuerelementen verarbeitet.  
  
 `SetTabStops`wird nicht automatisch Fensters neu gezeichnet werden. Wenn Sie die Tabstopps für den Text in das Steuerelement zum Bearbeiten bereits ändern, rufen Sie [CWnd::InvalidateRect](cwnd-class.md#invalidaterect) Fensters neu gezeichnet.  
  
 Weitere Informationen finden Sie unter [EM_SETTABSTOPS](http://msdn.microsoft.com/library/windows/desktop/bb761663) und [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CEditView::SetTabStops](ceditview-class.md#settabstops).  
  
##  <a name="showballoontip"></a>CEdit::ShowBalloonTip  
 Zeigt eine SprechblasenInfo, die das aktuelle Edit-Steuerelement zugeordnet ist.  
  
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
|[in] `lpszText`|Ein Zeiger auf eine Unicode-Zeichenfolge, die die Sprechblase QuickInfo-Text enthält.|  
|[in] `ttiIcon`|Ein `INT` , der den Typ des Symbols zugeordnet, der die SprechblasenInfo angibt. Der Standardwert ist `TTI_NONE`. Weitere Informationen finden Sie unter der `ttiIcon` Mitglied der [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) Struktur.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sendet die [EM_SHOWBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761668) -Nachricht, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen finden Sie unter der [Edit_ShowBalloonTip](http://msdn.microsoft.com/library/windows/desktop/bb761707) Makro.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird eine Variable definiert `m_cedit`besteht, wird verwendet, um Zugriff auf das aktuelle Steuerelement zum Bearbeiten. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CEdit_s&#1;1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt eine SprechblasenInfo für ein Edit-Steuerelement an. Die [CEdit::ShowBalloonTip](#showballoontip) Methode gibt ein QuickInfo-Text für Titel und Sprechblase an.  
  
 [!code-cpp[NVC_MFC_CEdit_s1&3;](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]  
  
##  <a name="undo"></a>CEdit::Undo  
 Rufen Sie diese Funktion zum Rückgängigmachen des letzten Bearbeitungssteuerelement Vorgangs.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Für eine einzeilige Edit-Steuerelement ist der Rückgabewert immer ungleich NULL. Für ein mehrzeiliges Bearbeitungssteuerelement, ist der Rückgabewert ungleich NULL, wenn der Rückgängig-Vorgang erfolgreich ist oder 0, wenn der Rückgängig-Vorgang fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Ein Rückgängig-Vorgang kann auch rückgängig gemacht werden. Sie können z. B. gelöschten Text mit dem ersten Aufruf von wiederherstellen **Rückgängig**. Solange keine Beteiligte Bearbeitungsvorgangs vorhanden ist, können, entfernen Sie den Text erneut mit einem zweiten Aufruf von **Rückgängig**.  
  
 Weitere Informationen finden Sie unter [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CEdit&#25;](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]  
  
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

