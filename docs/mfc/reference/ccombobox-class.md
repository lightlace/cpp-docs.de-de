---
title: CComboBox-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
dev_langs:
- C++
helpviewer_keywords:
- CComboBox [MFC], CComboBox
- CComboBox [MFC], AddString
- CComboBox [MFC], Clear
- CComboBox [MFC], CompareItem
- CComboBox [MFC], Copy
- CComboBox [MFC], Create
- CComboBox [MFC], Cut
- CComboBox [MFC], DeleteItem
- CComboBox [MFC], DeleteString
- CComboBox [MFC], Dir
- CComboBox [MFC], DrawItem
- CComboBox [MFC], FindString
- CComboBox [MFC], FindStringExact
- CComboBox [MFC], GetComboBoxInfo
- CComboBox [MFC], GetCount
- CComboBox [MFC], GetCueBanner
- CComboBox [MFC], GetCurSel
- CComboBox [MFC], GetDroppedControlRect
- CComboBox [MFC], GetDroppedState
- CComboBox [MFC], GetDroppedWidth
- CComboBox [MFC], GetEditSel
- CComboBox [MFC], GetExtendedUI
- CComboBox [MFC], GetHorizontalExtent
- CComboBox [MFC], GetItemData
- CComboBox [MFC], GetItemDataPtr
- CComboBox [MFC], GetItemHeight
- CComboBox [MFC], GetLBText
- CComboBox [MFC], GetLBTextLen
- CComboBox [MFC], GetLocale
- CComboBox [MFC], GetMinVisible
- CComboBox [MFC], GetTopIndex
- CComboBox [MFC], InitStorage
- CComboBox [MFC], InsertString
- CComboBox [MFC], LimitText
- CComboBox [MFC], MeasureItem
- CComboBox [MFC], Paste
- CComboBox [MFC], ResetContent
- CComboBox [MFC], SelectString
- CComboBox [MFC], SetCueBanner
- CComboBox [MFC], SetCurSel
- CComboBox [MFC], SetDroppedWidth
- CComboBox [MFC], SetEditSel
- CComboBox [MFC], SetExtendedUI
- CComboBox [MFC], SetHorizontalExtent
- CComboBox [MFC], SetItemData
- CComboBox [MFC], SetItemDataPtr
- CComboBox [MFC], SetItemHeight
- CComboBox [MFC], SetLocale
- CComboBox [MFC], SetMinVisibleItems
- CComboBox [MFC], SetTopIndex
- CComboBox [MFC], ShowDropDown
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fffa5c09f1572200ca7850c8870b7daee9e3e75f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccombobox-class"></a>CComboBox-Klasse
Stellt die Funktionalität eines Windows-Kombinationsfelds bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CComboBox : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComboBox::CComboBox](#ccombobox)|Erstellt ein `CComboBox`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComboBox:: AddString](#addstring)|Fügt eine Zeichenfolge bis zum Ende der Liste im Listenfeld eines Kombinationsfelds oder an der Position in der sortierten von Listenfeldern mit dem **CBS_SORT** Stil.|  
|[CComboBox::Clear](#clear)|Löscht (deaktiviert) die aktuelle Auswahl, sofern vorhanden, in das Bearbeitungssteuerelement.|  
|[CComboBox::CompareItem](#compareitem)|Vom Framework aufgerufen, die die relative Position eines neuen Listenelements in einem sortierten Ownerdrawn-Kombinationsfeld feststellen.|  
|[CComboBox::Copy](#copy)|Kopiert die aktuelle Auswahl, sofern vorhanden, in die Zwischenablage in **HIERSVR** Format.|  
|[CComboBox::Create](#create)|Erstellt das Kombinationsfeld und fügt es der `CComboBox` Objekt.|  
|[CComboBox::Cut](#cut)|(Teilstücke) Löscht die aktuelle Auswahl, sofern zutreffend, in den Bearbeitungsmodus zu steuern und den gelöschten Text in die Zwischenablage in kopiert **HIERSVR** Format.|  
|[CComboBox::DeleteItem](#deleteitem)|Vom Framework aufgerufen, wenn ein Listenelement aus einem Ownerdrawn-Kombinationsfeld gelöscht wird.|  
|[CComboBox::DeleteString](#deletestring)|Löscht eine Zeichenfolge aus dem Listenfeld eines Kombinationsfelds an.|  
|[CComboBox::Dir](#dir)|Fügt eine Liste von Dateinamen in das Listenfeld eines Kombinationsfelds an.|  
|[CComboBox::DrawItem](#drawitem)|Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines ein Ownerdrawn-Kombinationsfeld ändert.|  
|[CComboBox:: FindString](#findstring)|Sucht nach der ersten Zeichenfolge, die das angegebene Präfix in das Listenfeld eines Kombinationsfelds enthält.|  
|[CComboBox::FindStringExact](#findstringexact)|Sucht die erste Listenfeld Zeichenfolge (in ein Kombinationsfeld), die der angegebenen Zeichenfolge übereinstimmt.|  
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|Ruft Informationen über die `CComboBox` Objekt.|  
|[CComboBox::GetCount](#getcount)|Ruft die Anzahl der Elemente im Listenfeld eines Kombinationsfelds ab.|  
|[CComboBox::GetCueBanner](#getcuebanner)|Ruft den Hinweistext, der angezeigt wird, ist für ein Kombinationsfeld-Steuerelement ab.|  
|[CComboBox::GetCurSel](#getcursel)|Ruft den Index des derzeit ausgewählten Elements ab, sofern vorhanden, in das Listenfeld eines Kombinationsfelds.|  
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|Ruft die Bildschirmkoordinaten des sichtbar (Dropdown) Listenfeld der ein Dropdown-Kombinationsfeld ab.|  
|[CComboBox::GetDroppedState](#getdroppedstate)|Bestimmt, ob das Listenfeld im Dropdown-Kombinationsfeld angezeigt wird (unten gelöscht).|  
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|Ruft die minimal zulässige Breite für die tatsächlich im Dropdown-Listenfeld eines Kombinationsfelds ab.|  
|[CComboBox::GetEditSel](#geteditsel)|Ruft die Zeichenpositionen Start- und Enddatum, der die aktuelle Auswahl in das Steuerelement zum Bearbeiten eines Kombinationsfelds ab.|  
|[CComboBox::GetExtendedUI](#getextendedui)|Bestimmt, ob ein Kombinationsfeld die Standardbenutzeroberfläche oder die erweiterte Benutzeroberfläche hat.|  
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|Gibt die Breite in Pixel, der im Listenfeld Teil des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann.|  
|[CComboBox::GetItemData](#getitemdata)|Ruft den von der Anwendung bereitgestellten 32-Bit-Wert dem angegebenen Kombinationsfeld-Element zugeordnet.|  
|[CComboBox::GetItemDataPtr](#getitemdataptr)|Ruft ab, der von der Anwendung bereitgestellten 32-Bit-Zeiger, der dem angegebenen Kombinationsfeld-Element zugeordnet ist.|  
|[CComboBox::GetItemHeight](#getitemheight)|Ruft die Höhe der Listenelemente in einem Kombinationsfeld ab.|  
|[CComboBox::GetLBText](#getlbtext)|Ruft eine Zeichenfolge aus dem Listenfeld eines Kombinationsfelds ab.|  
|[CComboBox::GetLBTextLen](#getlbtextlen)|Ruft die Länge einer Zeichenfolge in das Listenfeld eines Kombinationsfelds ab.|  
|[CComboBox::GetLocale](#getlocale)|Ruft den Gebietsschemabezeichner für ein Kombinationsfeld ab.|  
|[CComboBox::GetMinVisible](#getminvisible)|Ruft die minimale Anzahl von sichtbaren Elemente in der Dropdown-Liste des Kombinationsfelds aktuelle ab.|  
|[CComboBox::GetTopIndex](#gettopindex)|Gibt den Index des ersten sichtbaren Elements im Listenfeld Teil des Kombinationsfelds zurück.|  
|[CComboBox::InitStorage](#initstorage)|Reserviert Speicherblöcke für Elemente und Zeichenfolgen in das Listenfeld Teil des Kombinationsfelds.|  
|[CComboBox::InsertString](#insertstring)|Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds ein.|  
|[CComboBox::LimitText](#limittext)|Beschränkt die Länge des Texts, die der Benutzer das Steuerelement zum Bearbeiten eines Kombinationsfelds eingeben kann.|  
|[CComboBox::MeasureItem](#measureitem)|Wird aufgerufen, durch das Framework Kombinationsfeld Feld Dimensionen zu bestimmen, wann ein Ownerdrawn-Kombinationsfeld erstellt wird.|  
|[CComboBox::Paste](#paste)|Die Daten aus der Zwischenablage in das Bearbeitungssteuerelement an der aktuellen Cursorposition eingefügt. Daten werden nur dann, wenn Daten in die Zwischenablage enthält, eingefügt **HIERSVR** Format.|  
|[CComboBox::ResetContent](#resetcontent)|Entfernt, die alle Elemente aus der Liste ein und Bearbeitungssteuerelement des Kombinationsfelds.|  
|[CComboBox::SelectString](#selectstring)|Sucht nach einer Zeichenfolge in das Listenfeld eines Kombinationsfelds und, wenn die Zeichenfolge gefunden wird, wählt die Zeichenfolge in der Liste und kopiert Sie die Zeichenfolge in das Bearbeitungssteuerelement.|  
|[CComboBox::SetCueBanner](#setcuebanner)|Legt den Hinweistext, der für ein Kombinationsfeld-Steuerelement angezeigt wird.|  
|[CComboBox::SetCurSel](#setcursel)|Wählt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds an.|  
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|Legt die Breite für die tatsächlich im Dropdown-Listenfeld eines Kombinationsfelds zulässige Mindestwert fest.|  
|[CComboBox::SetEditSel](#seteditsel)|Das Steuerelement zum Bearbeiten eines Kombinationsfelds markiert Zeichen.|  
|[CComboBox::SetExtendedUI](#setextendedui)|Wählt die Standardbenutzeroberfläche oder die erweiterte Benutzeroberfläche für ein Kombinationsfeld, ist die **CBS_DROPDOWN** oder **CBS_DROPDOWNLIST** Stil.|  
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|Legt die Breite in Pixel, der im Listenfeld Teil des Kombinationsfelds ein horizontaler Bildlauf durchgeführt werden kann.|  
|[CComboBox::SetItemData](#setitemdata)|Legt den 32-Bit-Wert, der das angegebene Element in einem Kombinationsfeld zugeordnet.|  
|[CComboBox::SetItemDataPtr](#setitemdataptr)|Legt fest, den 32-Bit-Zeiger, die das angegebene Element in einem Kombinationsfeld zugeordnet.|  
|[CComboBox::SetItemHeight](#setitemheight)|Legt die Höhe der Listenelemente in einem Kombinationsfeld oder die Höhe des bearbeiten-Steuerelement (oder statischer Text) Teil eines Kombinationsfelds fest.|  
|[CComboBox::SetLocale](#setlocale)|Legt den Gebietsschemabezeichner für ein Kombinationsfeld.|  
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|Legt die minimale Anzahl von sichtbaren Elemente in der Dropdown-Liste des aktuellen Kombinationsfelds fest.|  
|[CComboBox::SetTopIndex](#settopindex)|Weist den im Listenfeld Teil Kombinationsfeld, um das Element mit dem angegebenen Index am oberen anzuzeigen.|  
|[CComboBox::ShowDropDown](#showdropdown)|Blendet das Listenfeld eines Kombinationsfelds, die verfügt die **CBS_DROPDOWN** oder **CBS_DROPDOWNLIST** Stil.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Kombinationsfeld besteht aus einem Listenfeld, das mit einem statischen Steuerelement oder Bearbeitungssteuerelement kombiniert. Listenfeld Teil des Steuerelements kann jederzeit angezeigt werden oder kann nur nach unten löschen, wenn der Benutzer auf den Dropdown Pfeil neben dem Steuerelement auswählt.  
  
 Das aktuell ausgewählte Element im Listenfeld (sofern vorhanden) wird in der statischen oder edit-Steuerelement. Darüber hinaus verfügt das Kombinationsfeld das Format der Dropdown-Liste, der Benutzer kann das erste Zeichen eines der Elemente in der Liste eingeben, und klicken Sie im Listenfeld wenn sichtbar ist, wird markieren das nächste Element mit diesem ersten Zeichen.  
  
 Die folgende Tabelle vergleicht die drei Kombinationsfeld [Stile](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles).  
  
|Stil|Wenn im Listenfeld angezeigt wird|Statische oder Edit-Steuerelement|  
|-----------|-------------------------------|-----------------------------|  
|Einfach|Immer|Bearbeiten|  
|Drop-down|Wenn Sie gelöscht|Bearbeiten|  
|Dropdownliste|Wenn Sie gelöscht|Statisch|  
  
 Sie erstellen eine `CComboBox` Objekt aus entweder einer Dialogfeldvorlage oder direkt im Code. In beiden Fällen rufen Sie zunächst den Konstruktor `CComboBox` zum Erstellen der `CComboBox` Objekt; rufen Sie anschließend die [erstellen](#create) Memberfunktion versucht, erstellen Sie das Steuerelement, und fügen Sie es auf die `CComboBox` Objekt.  
  
 Wenn Sie Windows gesendete benachrichtigungsmeldungen von einem Kombinationsfeld an der übergeordnete behandeln möchten (normalerweise eine abgeleitete Klasse `CDialog`), die übergeordnete Klasse für jede Nachricht eine meldungszuordnung Eintrag und Nachrichtenhandler Memberfunktion hinzufügen.  
  
 Jede Meldungszuordnungseintrags weist folgende Form auf:  
  
 **ON_**Benachrichtigung **(**`id`**,**`memberFxn`**)**  
  
 wobei `id` gibt die ID der untergeordneten Fenster des Kombinationsfeld Steuerelements Senden der Benachrichtigung und `memberFxn` ist der Name der übergeordneten-Memberfunktion, die Sie geschrieben haben, um die Benachrichtigung zu verarbeiten.  
  
 Das übergeordnete Funktionsprototyp lautet wie folgt:  
  
 **Afx_msg** `void` `memberFxn` **();**  
  
 Die Reihenfolge, in der bestimmte Benachrichtigungen gesendet werden sollen, kann nicht vorhergesagt werden. Insbesondere eine **CBN_SELCHANGE** Benachrichtigung kann auftreten, entweder vor oder nach einem **CBN_CLOSEUP** Benachrichtigung.  
  
 Potenzielle Meldungszuordnungseinträge lauten wie folgt:  
  
- **ON_CBN_CLOSEUP** (Windows 3.1 und höher.) Das Listenfeld eines Kombinationsfelds wurde geschlossen. Diese Nachricht wird nicht gesendet, für ein Kombinationsfeld, ist die [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.  
  
- **ON_CBN_DBLCLK** der Benutzer auf eine Zeichenfolge in das Listenfeld eines Kombinationsfelds doppelklickt. Diese Benachrichtigung wird nur gesendet, eines Kombinationsfelds mit der **CBS_SIMPLE** Stil. Für ein Kombinationsfeld, mit der [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) formatieren, Doppelklick ist nicht möglich, da nur ein Klick Blendet Sie aus dem Listenfeld.  
  
- **ON_CBN_DROPDOWN** das Listenfeld eines Kombinationsfelds zum Dropdown-Liste ist (sichtbar gemacht werden). Diese Benachrichtigung ist möglich, nur für ein Kombinationsfeld, mit der **CBS_DROPDOWN** oder **CBS_DROPDOWNLIST** Stil.  
  
- **ON_CBN_EDITCHANGE** der Benutzer eine Aktion, die den Text im Bearbeitungssteuerelement Teil eines Kombinationsfelds möglicherweise geändert haben übernommen hat. Im Gegensatz zu den **CBN_EDITUPDATE** Nachricht diese Nachricht wird gesendet, nachdem Windows den Bildschirm aktualisiert. Es wird nicht gesendet, wenn das Kombinationsfeld kann die **CBS_DROPDOWNLIST** Stil.  
  
- **ON_CBN_EDITUPDATE** das Bearbeitungssteuerelement Teil eines Kombinationsfelds zum geänderten Text angezeigt wird. Diese Benachrichtigung wird gesendet, nachdem das Steuerelement den Text formatiert hat, aber bevor der Text angezeigt. Es wird nicht gesendet, wenn das Kombinationsfeld kann die **CBS_DROPDOWNLIST** Stil.  
  
- **ON_CBN_ERRSPACE** im Kombinationsfeld nicht genügend Speicherplatz, um eine bestimmte Anforderung zu erfüllen zuweisen.  
  
- **ON_CBN_SELENDCANCEL** (Windows 3.1 und höher.) Gibt an, dass die Auswahl des Benutzers abgebrochen werden soll. Der Benutzer klickt auf ein Element, und klickt dann auf ein anderes Fenster oder Steuerelement, um das Listenfeld eines Kombinationsfelds auszublenden. Diese Benachrichtigung wird gesendet, bevor die **CBN_CLOSEUP** Benachrichtigung, um anzugeben, dass die Auswahl des Benutzers ignoriert werden sollen. Die **CBN_SELENDCANCEL** oder **CBN_SELENDOK** Nachricht wird gesendet, auch wenn die **CBN_CLOSEUP** Benachrichtigung wird nicht gesendet (wie bei einem Kombinationsfeld mit der **CBS_SIMPLE** Stil).  
  
- **ON_CBN_SELENDOK** der Benutzer wählt ein Element aus und klicken Sie dann die EINGABETASTE drückt oder klickt auf die unten-Taste, um das Listenfeld eines Kombinationsfelds auszublenden. Diese Benachrichtigung wird gesendet, bevor die **CBN_CLOSEUP** Nachricht, um anzugeben, dass die Auswahl des Benutzers als gültig eingestuft werden soll. Die **CBN_SELENDCANCEL** oder **CBN_SELENDOK** Nachricht wird gesendet, auch wenn die **CBN_CLOSEUP** Benachrichtigung wird nicht gesendet (wie bei einem Kombinationsfeld mit der **CBS_SIMPLE** Stil).  
  
- **ON_CBN_KILLFOCUS** im Kombinationsfeld den Eingabefokus verliert.  
  
- **ON_CBN_SELCHANGE** die Auswahl im Listenfeld eines Kombinationsfelds ist aufgrund der Benutzer aus, klicken Sie im Listenfeld oder ändern die Auswahl mithilfe der Pfeiltasten geändert werden. Bei der Verarbeitung dieser Nachricht der Text im Bearbeitungssteuerelement des Kombinationsfelds kann nur abgerufen werden über `GetLBText` oder eine andere ähnliche Funktion. `GetWindowText`kann nicht verwendet werden.  
  
- **ON_CBN_SETFOCUS** im Kombinationsfeld den Eingabefokus erhält.  
  
 Bei Erstellung einer `CComboBox` Objekt in einem Dialogfeld (über eine Dialogfeldressource), die `CComboBox` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.  
  
 Wenn Sie Einbetten einer `CComboBox` Objekt in ein anderes Fenster Objekt, das Sie brauchen sie zerstört werden. Bei Erstellung der `CComboBox` Objekt im Stapel befindet, automatisch zerstört wird. Bei Erstellung der `CComboBox` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das sie zerstört werden, wenn die Windows-Kombinationsfelds zerstört wird.  
  
 **Hinweis** Wenn Sie behandeln möchten `WM_KEYDOWN` und `WM_CHAR` Nachrichten müssen Unterklasse des Kombinationsfelds bearbeiten und Liste Listenfeldsteuerelemente, leiten Sie eine Klasse von `CEdit` und `CListBox`, und die abgeleiteten Handler für diese Nachrichten hinzufügen Klassen. Weitere Informationen finden Sie unter [Http://support.microsoft.com/default.aspxscid=kb;en-us; Q174667](http://support.microsoft.com/default.aspxscid=kb;en-us;q174667) und [CWnd:: SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="addstring"></a>CComboBox:: AddString  
 Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds an.  
  
```  
int AddString(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszString`  
 Verweist auf die Null-terminierte Zeichenfolge, die hinzugefügt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Rückgabewert größer als oder gleich 0 ist, ist es der nullbasierte Index in der Zeichenfolge im Listenfeld aus. Der Rückgabewert ist **CB_ERR** Wenn ein Fehler auftritt; der Rückgabewert ist **CB_ERRSPACE** ist nicht genügend Speicherplatz zum Speichern der neuen Zeichenfolge zur Verfügung.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Listenfeld nicht erstellt wurde, mit der [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil, wird die Zeichenfolge am Ende der Liste hinzugefügt. Andernfalls die Zeichenfolge wird in der Liste eingefügt, und die Liste sortiert wird.  
  
> [!NOTE]
>  Diese Funktion wird vom Windows **ComboBoxEx** -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775738) im Windows SDK.  
  
 Verwenden Sie zum Einfügen einer Zeichenfolge in einer bestimmten Position in der Liste der [InsertString](#insertstring) Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]  
  
##  <a name="ccombobox"></a>CComboBox::CComboBox  
 Erstellt ein `CComboBox`-Objekt.  
  
```  
CComboBox();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]  
  
##  <a name="clear"></a>CComboBox::Clear  
 Löscht (deaktiviert) die aktuelle Auswahl, sofern vorhanden, in das Bearbeitungssteuerelement des Kombinationsfelds.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Löschen der aktuellen Auswahl, und fügen Sie den gelöschten Inhalt in die Zwischenablage, die [Ausschneiden](#cut) Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]  
  
##  <a name="compareitem"></a>CComboBox::CompareItem  
 Wird aufgerufen, durch das Framework, um die relative Position eines neuen Elements im Listenfeld Teil einer sortierten Ownerdrawn-Kombinationsfeld zu bestimmen.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpCompareItemStruct`  
 Eine long-Zeiger auf eine [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die relative Position der beiden Elemente, die in beschriebenen an die `COMPAREITEMSTRUCT` Struktur. Die folgenden Werte sind möglich:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|- 1|Element 1 wird vor Element 2 sortiert.|  
|0|Artikel 1 und Artikel 2 sortieren identisch.|  
|1|Element 1 sortiert nach dem Element 2.|  
  
 Finden Sie unter [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) eine Beschreibung der `COMPAREITEMSTRUCT`.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Memberfunktion keine Aktion ausgeführt. Wenn Sie ein Ownerdrawn-Kombinationsfeld mit Erstellen der **LBS_SORT** Stil, müssen Sie diese Memberfunktion, um das Framework Unterstützung bei der Sortierung neue Elemente hinzugefügt werden, in das Listenfeld überschreiben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]  
  
##  <a name="copy"></a>CComboBox::Copy  
 Kopiert die aktuelle Auswahl ggf. in das Bearbeitungssteuerelement des Kombinationsfelds in die Zwischenablage in **HIERSVR** Format.  
  
```  
void Copy();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]  
  
##  <a name="create"></a>CComboBox::Create  
 Erstellt das Kombinationsfeld und fügt es der `CComboBox` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Gibt das Format des Kombinationsfelds. Wenden Sie eine beliebige Kombination von [kombinationsfeldstile](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) in das Feld.  
  
 `rect`  
 Verweist auf die Position und Größe des Kombinationsfelds. Kann eine [RECT-Struktur](../../mfc/reference/rect-structure1.md) oder ein `CRect` Objekt.  
  
 `pParentWnd`  
 Gibt an, das Kombinationsfeld des übergeordneten Fensters (in der Regel eine `CDialog`). Es muss nicht **NULL**.  
  
 `nID`  
 Gibt an, das Kombinationsfeld-Steuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CComboBox` Objekt in zwei Schritten. Zuerst wird den Konstruktor aufrufen und dann **erstellen**, das erstellt die Windows-Kombinationsfelds und fügt es der `CComboBox` Objekt.  
  
 Wenn **erstellen** ausgeführt wird, sendet Windows die [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), und [WM_ GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Nachrichten dem Kombinationsfeld.  
  
 Diese Nachrichten werden standardmäßig verarbeitet der [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), und [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) Memberfunktionen in der `CWnd` Basisklasse. Um die Standard-Meldungsbehandlung zu erweitern, leiten Sie eine Klasse von `CComboBox`eine meldungszuordnung an die neue Klasse hinzufügen und die vorherigen Meldungshandler Memberfunktionen überschreiben. Überschreiben Sie `OnCreate`, z. B. für die erforderliche Initialisierung für eine neue Klasse.  
  
 Übernehmen Sie die folgenden [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) an ein Kombinationsfeld Steuerelement. :  
  
- **WS_CHILD** immer  
  
- **WS_VISIBLE** in der Regel  
  
- **WS_DISABLED** selten  
  
- **WS_VSCROLL** vertikaler Bildlauf für das Listenfeld im Kombinationsfeld hinzufügen  
  
- **WS_HSCROLL** horizontalen Bildlauf für das Listenfeld im Kombinationsfeld hinzufügen  
  
- **WS_GROUP** zum Gruppieren von Steuerelementen  
  
- **WS_TABSTOP** im Kombinationsfeld in der Tabulatorreihenfolge eingeschlossen werden sollen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]  
  
##  <a name="cut"></a>CComboBox::Cut  
 Löscht (Teilstücke) die aktuelle Auswahl, wenn ein in das Kombinationsfeld Bearbeiten steuern und kopiert den gelöschten Text in die Zwischenablage in **HIERSVR** Format.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Hinweise  
 Um die aktuelle Auswahl ohne platzieren den gelöschten Text in die Zwischenablage zu löschen, rufen die [deaktivieren](#clear) Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]  
  
##  <a name="deleteitem"></a>CComboBox::DeleteItem  
 Vom Framework aufgerufen, wenn der Benutzer ein Element aus einem Besitzer gezeichneten löscht `CComboBox` Objekt oder Kombinationsfeld zerstört.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDeleteItemStruct`  
 Eine long-Zeiger auf ein Windows [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) -Struktur, die Informationen über das gelöschte Element enthält. Finden Sie unter [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) eine Beschreibung dieser Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Standardimplementierung dieser Funktion wird keine Aktion ausgeführt. Überschreiben Sie diese Funktion, um das Kombinationsfeld neu gezeichnet werden nach Bedarf.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]  
  
##  <a name="deletestring"></a>CComboBox::DeleteString  
 Löscht das Element an Position `nIndex` aus dem Kombinationsfeld.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den Index in der Zeichenfolge, die gelöscht werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Rückgabewert größer als oder gleich 0 ist, ist es die Anzahl der Zeichenfolgen in der Liste Verbleibende. Der Rückgabewert ist **CB_ERR** Wenn `nIndex` Index größer als die Anzahl der Elemente in der Liste angibt.  
  
### <a name="remarks"></a>Hinweise  
 Alle Elemente, die nach `nIndex` nun eine Position nach unten verschieben. Z. B. wenn ein Kombinationsfeld zwei Elemente enthält, verursacht löschen das erste Element der verbleibenden Element aus, um in der ersten Position aussehen. `nIndex`= 0 für das Element in der ersten Position.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]  
  
##  <a name="dir"></a>CComboBox::Dir  
 Fügt eine Liste der Dateinamen oder Laufwerke in das Listenfeld eines Kombinationsfelds an.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>Parameter  
 `attr`  
 Kann eine beliebige Kombination der `enum` Werte, die in beschriebenen [CFile:: GetStatus](../../mfc/reference/cfile-class.md#getstatus) oder eine beliebige Kombination der folgenden Werte:  
  
- **DDL_READWRITE** Datei auslesen oder geschrieben werden kann.  
  
- **DDL_READONLY** Datei auslesen, jedoch nicht geschrieben werden kann.  
  
- **DDL_HIDDEN** Datei ausgeblendet ist und nicht in einer Verzeichnisliste angezeigt.  
  
- **DDL_SYSTEM** Datei ist eine Systemdatei.  
  
- **DDL_DIRECTORY** angegebene `lpszWildCard` gibt das Verzeichnis an.  
  
- **DDL_ARCHIVE** Datei wurde archiviert.  
  
- **DDL_DRIVES** umfassen alle Laufwerke, die die vom angegebenen Namen entsprechen `lpszWildCard`.  
  
- **DDL_EXCLUSIVE** exklusive Flag. Wenn die exklusive Flag festgelegt ist, werden nur Dateien des angegebenen Typs aufgeführt. Dateien des angegebenen Typs werden hingegen neben "Standard"-Dateien aufgeführt.  
  
 `lpszWildCard`  
 Zeigt auf eine Dateispezifikation Zeichenfolge. Die Zeichenfolge kann Platzhalter enthalten (z. B. *.\*).  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Rückgabewert größer als oder gleich 0 ist, wird es den nullbasierten Index des letzten Dateinamen zur Liste hinzugefügt. Der Rückgabewert ist **CB_ERR** Wenn ein Fehler auftritt; der Rückgabewert ist **CB_ERRSPACE** ist nicht genügend Speicherplatz zur Verfügung, um die neuen Zeichenfolgen zu speichern.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Windows **ComboBoxEx** -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775738) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]  
  
##  <a name="drawitem"></a>CComboBox::DrawItem  
 Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines ein Ownerdrawn-Kombinationsfeld ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) -Struktur, die Informationen über den Typ der Zeichnung erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Die **ItemAction** Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll. Finden Sie unter [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) eine Beschreibung dieser Struktur.  
  
 Standardmäßig wird diese Memberfunktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für ein Ownerdrawn- `CComboBox` Objekt. Bevor diese Memberfunktion beendet wird, sollte die Anwendung alle Device Interface (GDI) Grafikobjekten ausgewählt, für der Anzeigekontext in bereitgestellten wiederherstellen `lpDrawItemStruct`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]  
  
##  <a name="findstring"></a>CComboBox:: FindString  
 Sucht nach, jedoch nicht auswählen, die erste Zeichenfolge, die das angegebene Präfix in das Listenfeld eines Kombinationsfelds enthält.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszString) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nStartAfter`  
 Enthält den nullbasierten Index des Elements vor dem ersten zu durchsuchenden Element. Wenn die Suche am Ende das Listenfeld erreicht wird, weiterhin von der obersten Position des Listenfelds zurück durch angegebene Element `nStartAfter`. Wenn 1, wird der gesamte Listenfeld vom Anfang durchsucht.  
  
 `lpszString`  
 Verweist auf die auf Null endende Zeichenfolge, die das Präfix für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Rückgabewert größer als oder gleich 0 ist, ist es der nullbasierte Index des entsprechenden Elements. Es ist **CB_ERR** , wenn die Suche nicht erfolgreich war.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion wird vom Windows **ComboBoxEx** -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775738) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]  
  
##  <a name="findstringexact"></a>CComboBox::FindStringExact  
 Rufen Sie die `FindStringExact` Member-Funktion, um die erste im Listenfeld-Zeichenfolge (in ein Kombinationsfeld) zu suchen, der im angegebenen Zeichenfolge übereinstimmt `lpszFind`.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndexStart`  
 Gibt den nullbasierten Index des Elements vor dem ersten zu durchsuchenden Element. Wenn die Suche am Ende das Listenfeld erreicht wird, weiterhin von der obersten Position des Listenfelds zurück durch angegebene Element `nIndexStart`. Wenn `nIndexStart` ist-1 und das gesamte Listenfeld wird vom Anfang durchsucht.  
  
 `lpszFind`  
 Verweist auf die Null-terminierte Zeichenfolge gesucht. Diese Zeichenfolge kann einen vollständigen Dateinamen, einschließlich der Erweiterung enthalten. Die Suche ist nicht Groß-/Kleinschreibung beachtet, sodass diese Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des entsprechenden Elements oder **CB_ERR** , wenn die Suche nicht erfolgreich war.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Kombinationsfeld mit einem Ownerdrawn-Stil, aber ohne erstellt wurde die [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil `FindStringExact` versucht, mit der Doppelwort Wert gegen den Wert von `lpszFind`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]  
  
##  <a name="getcomboboxinfo"></a>CComboBox::GetComboBoxInfo  
 Ruft Informationen für die `CComboBox` Objekt.  
  
```  
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *pcbi*  
 Ein Zeiger auf die [COMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775798) Struktur.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion emuliert die Funktionen des die [CB_GETCOMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775839) Nachricht, wie im Windows SDK beschrieben.  
  
##  <a name="getcount"></a>CComboBox::GetCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Elemente in der im Listenfeld eines Kombinationsfelds an.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente. Die zurückgegebene Anzahl ist größer als der Indexwert des letzten Elements (der Index ist nullbasiert). Es ist **CB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]  
  
##  <a name="getcuebanner"></a>CComboBox::GetCueBanner  
 Ruft den Hinweistext, der angezeigt wird, ist für ein Kombinationsfeld-Steuerelement ab.  
  
```  
CString GetCueBanner() const;  
  
BOOL GetCueBanner(
    LPTSTR lpszText,   
    int cchText) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[out] `lpszText`|Ein Zeiger auf einen Puffer, der den hinweisbannertext empfängt.|  
|[in] `cchText`|Größe des Puffers, der `lpszText` -Parameter zeigt.|  
  
### <a name="return-value"></a>Rückgabewert  
 In der ersten Überladung eine [CString](../../atl-mfc-shared/using-cstring.md) Objekt, das den hinweisbannertext enthält, wenn er vorhanden ist, andernfalls ein `CString` -Objekt, das 0 (null) Länge aufweist.  
  
 - oder -   
  
 In der zweiten Überladung `true` Wenn diese Methode erfolgreich, andernfalls ist `false`.  
  
### <a name="remarks"></a>Hinweise  
 Hinweistext ist eine Aufforderung, die in das Eingabefeld ein Kombinationsfeld-Steuerelement angezeigt wird. Der Hinweistext wird angezeigt, bis der Benutzer die Eingabe bereitstellt.  
  
 Diese Methode sendet die [CB_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775843) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="getcursel"></a>CComboBox::GetCurSel  
 Rufen Sie diese Memberfunktion, um zu bestimmen, welches Element im Kombinationsfeld ausgewählt wird.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des derzeit ausgewählten Elements im Listenfeld eines Kombinationsfelds oder **CB_ERR** Wenn kein Element ausgewählt ist.  
  
### <a name="remarks"></a>Hinweise  
 `GetCurSel`Gibt einen Index in der Liste zurück.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]  
  
##  <a name="getdroppedcontrolrect"></a>CComboBox::GetDroppedControlRect  
 Rufen Sie die `GetDroppedControlRect` Memberfunktion die Bildschirmkoordinaten des Felds sichtbar (gelöscht) Dropdownliste der ein Dropdown-Kombinationsfeld abgerufen.  
  
```  
void GetDroppedControlRect(LPRECT lprect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lprect*  
 Verweist auf die [RECT-Struktur](../../mfc/reference/rect-structure1.md) , die die Koordinaten empfangen wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]  
  
##  <a name="getdroppedstate"></a>CComboBox::GetDroppedState  
 Rufen Sie die `GetDroppedState` Member-Funktion, um festzustellen, ob das Listenfeld im Dropdown-Kombinationsfeld angezeigt wird (unten gelöscht).  
  
```  
BOOL GetDroppedState() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Sie im Listenfeld angezeigt wird; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]  
  
##  <a name="getdroppedwidth"></a>CComboBox::GetDroppedWidth  
 Rufen Sie diese Funktion, um die minimale zulässige Breite in Pixel, der im Listenfeld eines Kombinationsfelds abzurufen.  
  
```  
int GetDroppedWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Im Erfolgsfall die minimale zulässige Breite in Pixel; andernfalls **CB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gilt nur für Kombinationsfelder, mit der [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.  
  
 Standardmäßig ist die minimale zulässige Breite des Dropdown-Listenfelds 0. Die minimale zulässige Breite kann festgelegt werden, durch den Aufruf [SetDroppedWidth](#setdroppedwidth). Wenn das Listenfeld Teil des Kombinationsfelds angezeigt wird, wird seine Breite größer als die zulässige Mindestbreite oder das Kombinationsfeld Feldbreite.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [SetDroppedWidth](#setdroppedwidth).  
  
##  <a name="geteditsel"></a>CComboBox::GetEditSel  
 Ruft die Zeichenpositionen Start- und Enddatum, der die aktuelle Auswahl in das Steuerelement zum Bearbeiten eines Kombinationsfelds ab.  
  
```  
DWORD GetEditSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein 32-Bit-Wert, der Startposition in das niederwertige Wort und die Position des ersten Zeichens nicht ausgewählten nach dem Ende der Auswahl in das höherwertige Wort enthält. Wenn diese Funktion, in einem Kombinationsfeld ohne ein Bearbeitungssteuerelement verwendet wird **CB_ERR** wird zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]  
  
##  <a name="getextendedui"></a>CComboBox::GetExtendedUI  
 Rufen Sie die `GetExtendedUI` Member-Funktion, um festzustellen, ob ein Kombinationsfeld die Standardbenutzeroberfläche oder die erweiterte Benutzeroberfläche hat.  
  
```  
BOOL GetExtendedUI() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Kombinationsfeld die erweiterte Benutzeroberfläche hat; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die erweiterte Benutzeroberfläche kann auf folgende Weise identifiziert werden:  
  
-   Nach Klicken auf die statisches Steuerelement wird im Listenfeld nur für Kombinationsfelder, mit der [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.  
  
-   Drücken die nach-unten-Taste zeigt das Listenfeld (F4 ist deaktiviert).  
  
 Durchführen eines Bildlaufs im statischen Steuerelement ist deaktiviert, wenn die Elementliste nicht sichtbar (Pfeil) Schlüssel deaktiviert werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]  
  
##  <a name="gethorizontalextent"></a>CComboBox::GetHorizontalExtent  
 Ruft die Breite in Pixel, die mit denen Listenfeld Teil des Kombinationsfelds horizontal gescrollt werden kann, aus dem Kombinationsfeld ab.  
  
```  
UINT GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die bildlauffähigen Breite des Bereichs im Listenfeld des im Kombinationsfeld in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist nur anwendbar, wenn das Listenfeld-Teil des Kombinationsfelds eine horizontale Bildlaufleiste angezeigt wurde.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]  
  
##  <a name="getitemdata"></a>CComboBox::GetItemData  
 Ruft den von der Anwendung bereitgestellten 32-Bit-Wert dem angegebenen Kombinationsfeld-Element zugeordnet.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index eines Elements im Listenfeld des Kombinationsfelds.  
  
### <a name="return-value"></a>Rückgabewert  
 Der 32-Bit-Wert, der dem Element zugeordnet oder **CB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Die 32-Bit-Wert kann festgelegt werden, mit der `dwItemData` Parameter, der eine [SetItemData](#setitemdata) memberfunktionsaufruf. Verwenden der `GetItemDataPtr` Memberfunktion, wenn der 32-Bit-Wert abgerufen werden soll, ein Zeiger ist ( **"void"\***).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]  
  
##  <a name="getitemdataptr"></a>CComboBox::GetItemDataPtr  
 Ruft ab, der von der Anwendung bereitgestellten 32-Bit-Wert zugeordnet ist, mit dem angegebenen Kombinationsfeld-Element als ein Zeiger ( **"void"\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index eines Elements im Listenfeld des Kombinationsfelds.  
  
### <a name="return-value"></a>Rückgabewert  
 Ruft ab einen Zeiger oder -1, wenn ein Fehler auftritt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]  
  
##  <a name="getitemheight"></a>CComboBox::GetItemHeight  
 Rufen Sie die `GetItemHeight` Member-Funktion, um die Höhe der Listenelemente in einem Kombinationsfeld abzurufen.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt die Komponente des Kombinationsfelds, dessen Höhe ist abgerufen werden sollen. Wenn die `nIndex` Parameter ist-1, der die Höhe der Edit-Steuerelement (oder statischer Text) Teil des Kombinationsfelds abgerufen wird. Wenn das Kombinationsfeld kann die [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil `nIndex` gibt den nullbasierten Index des Listenelements, dessen Höhe ist abgerufen werden sollen. Andernfalls `nIndex` muss auf 0 festgelegt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des angegebenen Elements in einem Kombinationsfeld in Pixel. Der Rückgabewert beim Auftreten eines Fehlers ist **CB_ERR** .  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]  
  
##  <a name="getlbtext"></a>CComboBox::GetLBText  
 Ruft eine Zeichenfolge aus dem Listenfeld eines Kombinationsfelds ab.  
  
```  
int GetLBText(
    int nIndex,  
    LPTSTR lpszText) const;  
  
void GetLBText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index der Zeichenfolge im Listenfeld kopiert werden soll.  
  
 `lpszText`  
 Zeigt auf einen Puffer, der die Zeichenfolge empfangen. Der Puffer muss genügend Speicherplatz für die Zeichenfolge und ein abschließendes Nullzeichen aufweisen.  
  
 `rString`  
 Ein Verweis auf eine `CString`.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge (in Byte) der Zeichenfolge ist, außer das abschließende Nullzeichen. Wenn `nIndex` gibt keinen gültigen Index, der Rückgabewert ist **CB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Die zweite Form dieses Members-Funktion füllt eine `CString` Objekt mit den Text des Elements.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]  
  
##  <a name="getlbtextlen"></a>CComboBox::GetLBTextLen  
 Ruft die Länge einer Zeichenfolge in das Listenfeld eines Kombinationsfelds ab.  
  
```  
int GetLBTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index der Zeichenfolge im Listenfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge der Zeichenfolge in Bytes, ausgenommen das abschließende Nullzeichen. Wenn `nIndex` gibt keinen gültigen Index, der Rückgabewert ist **CB_ERR**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CComboBox::GetLBText](#getlbtext).  
  
##  <a name="getlocale"></a>CComboBox::GetLocale  
 Ruft das Gebietsschema verwendet wird, indem Sie im Kombinationsfeld ab.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert des Gebietsschemabezeichners (LCID) für die Zeichenfolgen im Kombinationsfeld.  
  
### <a name="remarks"></a>Hinweise  
 Das Gebietsschema wird beispielsweise verwendet, um die Sortierreihenfolge der Zeichenfolgen in einem sortierten Kombinationsfeld zu bestimmen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CComboBox::SetLocale](#setlocale).  
  
##  <a name="getminvisible"></a>CComboBox::GetMinVisible  
 Ruft die minimale Anzahl von sichtbaren Elemente in der Dropdown-Liste der aktuellen ein Kombinationsfeld-Steuerelement ab.  
  
```  
int GetMinVisible() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die minimale Anzahl der sichtbaren Elemente in der aktuellen Dropdown-Liste.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [CB_GETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) Nachricht, die im Windows SDK beschrieben wird.  
  
##  <a name="gettopindex"></a>CComboBox::GetTopIndex  
 Ruft den nullbasierten Index des ersten sichtbaren Elements im Listenfeld Teil im Kombinationsfeld ab.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des ersten sichtbaren Elements im Listenfeld Teil im Kombinationsfeld im Erfolgsfall **CB_ERR** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Zu Beginn Element 0 befindet sich oben im Listenfeld, aber wenn das Listenfeld ein Bildlauf durchgeführt wird, möglicherweise ein anderes Element oben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]  
  
##  <a name="initstorage"></a>CComboBox::InitStorage  
 Belegt Speicher zum Speichern von Listenfeldelemente in das Listenfeld Teil des Kombinationsfelds.  
  
```  
int InitStorage(
    int nItems,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>Parameter  
 `nItems`  
 Gibt die Anzahl von Elementen hinzufügen.  
  
 `nBytes`  
 Gibt die Größe des Speichers in Bytes, die für Element Zeichenfolgen zugeordnet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, die maximale Anzahl von Elementen, die im Listenfeld Teil des Kombinationsfelds kann gespeichert werden, bevor eine neuzuordnung von Arbeitsspeicher, andernfalls erforderlich ist **CB_ERRSPACE**, d. h. nicht genügend Arbeitsspeicher verfügbar ist.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird vor dem Hinzufügen von einer großen Anzahl von Elementen zu der im Listenfeld Teil der `CComboBox`.  
  
 Windows 95/98: der `wParam` Parameter ist auf 16-Bit-Werte beschränkt. Dies bedeutet, dass Listenfelder mehr als 32.767 Elemente enthalten können. Obwohl die Anzahl der Elemente eingeschränkt ist, ist die Gesamtgröße der Elemente in einem Listenfeld, das nur durch den verfügbaren Speicher beschränkt.  
  
 Diese Funktion hilft der Initialisierung des Listenfelder beschleunigen, die eine große Anzahl von Elementen (mehr als 100) aufweisen. Es reserviert so, dass bei nachfolgenden angegebene Arbeitsspeichermenge [AddString](#addstring), [InsertString](#insertstring), und [Dir](#dir) akzeptieren Funktionen kurz wie möglich. Sie können die Schätzungen für die Parameter verwenden. Wenn Sie überschätzen, wird zusätzlicher Arbeitsspeicher reserviert. Wenn Sie unterschätzen, wird die normale Verteilung für Elemente verwendet, die den eingeteilt überschreiten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]  
  
##  <a name="insertstring"></a>CComboBox::InsertString  
 Fügt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds ein.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält den nullbasierten Index der Position im Listenfeld, die die Zeichenfolge aufnehmen soll. Wenn dieser Parameter-1 ist, wird die Zeichenfolge am Ende der Liste hinzugefügt.  
  
 `lpszString`  
 Zeigt auf die einzufügende nullterminierte Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index der Position, an der die Zeichenfolge eingefügt wurde. Der Rückgabewert beim Auftreten eines Fehlers ist **CB_ERR** . Der Rückgabewert ist **CB_ERRSPACE** , wenn zum Speichern der neuen Zeichenfolge nicht genügend Platz vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu der [AddString](#addstring) Memberfunktion, die `InsertString` Memberfunktion führt nicht dazu, dass eine Liste mit den [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil sortiert werden.  
  
> [!NOTE]
>  Diese Funktion wird vom Windows **ComboBoxEx** -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775738) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]  
  
##  <a name="limittext"></a>CComboBox::LimitText  
 Beschränkt die Länge in Bytes des Texts, die der Benutzer das Steuerelement zum Bearbeiten eines Kombinationsfelds eingeben kann.  
  
```  
BOOL LimitText(int nMaxChars);
```  
  
### <a name="parameters"></a>Parameter  
 `nMaxChars`  
 Gibt die Länge (in Bytes) des Texts, der der Benutzer eingeben kann. Wenn dieser Parameter 0 ist, wird die Textlänge auf 65.535 Byte festgelegt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg. Wenn für ein Kombinationsfeld, in dem Format aufgerufen [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder für ein Kombinationsfeld, ohne ein Bearbeitungssteuerelement, ist der Rückgabewert **CB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Kombinationsfeld keinen den Stil [CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles), festlegen, die größer als die Größe des Bearbeitungssteuerelements sein Text hat keine Auswirkungen.  
  
 `LimitText`den Text, den der Benutzer eingeben kann Größe beschränkt. Es hat keine Auswirkungen auf einen beschreibenden Text ein bereits in das Bearbeitungssteuerelement die Nachricht gesendet wird, oder auf die Länge des Texts in das Bearbeitungssteuerelement kopiert, wenn eine Zeichenfolge in der Liste ausgewählt ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]  
  
##  <a name="measureitem"></a>CComboBox::MeasureItem  
 Vom Framework aufgerufen, wenn ein Kombinationsfeld in einem Ownerdrawn-Format erstellt wird.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMeasureItemStruct`  
 Eine long-Zeiger auf eine [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Memberfunktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion auf, und geben Sie die `MEASUREITEMSTRUCT` Struktur informiert Windows über die Abmessungen der Liste im Kombinationsfeld Feld. Wenn das Kombinationsfeld erstellt wird, mit der [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Format, das Framework ruft diese Memberfunktion für jedes Element im Listenfeld. Andernfalls wird bei diesem Member nur einmal aufgerufen.  
  
 Mithilfe der **CBS_OWNERDRAWFIXED** Format in ein Ownerdrawn-Kombinationsfeld mit erstellt die [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) Memberfunktion der `CWnd` umfasst weitere Programmierung Überlegungen. Finden Sie unter den Ausführungen im [technischen Hinweis 14](../../mfc/tn014-custom-controls.md).  
  
 Finden Sie unter [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) eine Beschreibung der `MEASUREITEMSTRUCT` Struktur.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]  
  
##  <a name="paste"></a>CComboBox::Paste  
 Die Daten aus der Zwischenablage in das Bearbeitungssteuerelement des Kombinationsfelds an der aktuellen Cursorposition eingefügt.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Hinweise  
 Daten werden nur dann, wenn Daten in die Zwischenablage enthält, eingefügt **HIERSVR** Format.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]  
  
##  <a name="resetcontent"></a>CComboBox::ResetContent  
 Entfernt, die alle Elemente aus der Liste ein und Bearbeitungssteuerelement des Kombinationsfelds.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]  
  
##  <a name="selectstring"></a>CComboBox::SelectString  
 Sucht nach einer Zeichenfolge in das Listenfeld eines Kombinationsfelds, und wenn die Zeichenfolge gefunden wird, wählt die Zeichenfolge in der Liste und kopiert ihn in das Bearbeitungssteuerelement.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Parameter  
 `nStartAfter`  
 Enthält den nullbasierten Index des Elements vor dem ersten zu durchsuchenden Element. Wenn die Suche am Ende das Listenfeld erreicht wird, weiterhin von der obersten Position des Listenfelds zurück durch angegebene Element `nStartAfter`. Wenn 1, wird der gesamte Listenfeld vom Anfang durchsucht.  
  
 `lpszString`  
 Verweist auf die auf Null endende Zeichenfolge, die das Präfix für die Suche enthält. Die Suche gilt unabhängig, damit diese Zeichenfolge eine beliebige Kombination von Groß- und Kleinbuchstaben enthalten kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des ausgewählten Elements, wenn die Zeichenfolge gefunden wurde. Wenn die Suche nicht erfolgreich war, ist der Rückgabewert **CB_ERR** und die aktuelle Auswahl nicht geändert wird.  
  
### <a name="remarks"></a>Hinweise  
 Eine Zeichenfolge, die ausgewählt ist, nur, wenn die ersten Zeichen (aus den Ausgangspunkt) mit den Zeichen in die Präfixzeichenfolge übereinstimmen.  
  
 Beachten Sie, dass die `SelectString` und `FindString` Memberfunktionen beide suchen Sie nach einer Zeichenfolge, aber die `SelectString` Memberfunktion wählt auch die Zeichenfolge.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]  
  
##  <a name="setcuebanner"></a>CComboBox::SetCueBanner  
 Legt den Hinweistext, der für ein Kombinationsfeld-Steuerelement angezeigt wird.  
  
```  
BOOL SetCueBanner(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] *LpszText*|Zeiger auf einen Null-terminierte Puffer, der den Hinweistext enthält.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn die Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Hinweistext ist eine Aufforderung, die in das Eingabefeld ein Kombinationsfeld-Steuerelement angezeigt wird. Der Hinweistext wird angezeigt, bis der Benutzer die Eingabe bereitstellt.  
  
 Diese Methode sendet die [CB_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775897) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_combobox`, d. h. verwendet, um ein Kombinationsfeld-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird das hinweisbanner für ein Kombinationsfeld-Steuerelement.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="setcursel"></a>CComboBox::SetCurSel  
 Wählt eine Zeichenfolge in das Listenfeld eines Kombinationsfelds an.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>Parameter  
 `nSelect`  
 Gibt den nullbasierten Index des zu wählen Sie die Zeichenfolge an. Wenn-1 und aktuelle Auswahl im Listenfeld entfernt, und das Bearbeitungssteuerelement ist deaktiviert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der nullbasierte Index des Elements ausgewählt, wenn die Nachricht erfolgreich ist. Der Rückgabewert ist **CB_ERR** Wenn `nSelect` ist größer als die Anzahl der Elemente in der Liste oder wenn `nSelect` wird auf-1 festgelegt, die die Auswahl löscht.  
  
### <a name="remarks"></a>Hinweise  
 Bei Bedarf führt einen Bildlauf im Listenfeld die Zeichenfolge in der Ansicht (Wenn Sie im Listenfeld angezeigt wird). Der Text im Bearbeitungssteuerelement des Kombinationsfelds wird geändert, um die neue Auswahl angewendet. Die vorherige Auswahl im Listenfeld wird entfernt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]  
  
##  <a name="setdroppedwidth"></a>CComboBox::SetDroppedWidth  
 Rufen Sie diese Funktion, um die minimale zulässige Breite in Pixel, der im Listenfeld eines Kombinationsfelds festgelegt.  
  
```  
int SetDroppedWidth(UINT nWidth);
```  
  
### <a name="parameters"></a>Parameter  
 `nWidth`  
 Die zulässige Mindestbreite des Listenfeld Teils der im Kombinationsfeld in Pixel.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, die neue Breite auf der Liste, andernfalls Feld **CB_ERR**.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion gilt nur für Kombinationsfelder, mit der [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.  
  
 Standardmäßig ist die minimale zulässige Breite des Dropdown-Listenfelds 0. Wenn das Listenfeld Teil des Kombinationsfelds angezeigt wird, wird seine Breite größer als die zulässige Mindestbreite oder das Kombinationsfeld Feldbreite.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]  
  
##  <a name="seteditsel"></a>CComboBox::SetEditSel  
 Das Steuerelement zum Bearbeiten eines Kombinationsfelds markiert Zeichen.  
  
```  
BOOL SetEditSel(
    int nStartChar,  
    int nEndChar);
```  
  
### <a name="parameters"></a>Parameter  
 `nStartChar`  
 Gibt die Startposition. Wenn die Anfangsposition auf-1 festgelegt ist, wird die vorhandene Auswahl entfernt.  
  
 `nEndChar`  
 Gibt die Endposition. Wenn die Endposition-1, klicken Sie dann alle Text aus der Startposition, bis zum letzten festgelegt ist wird Zeichen in das Bearbeitungssteuerelement ausgewählt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Member-Funktion erfolgreich ist; andernfalls 0. Es ist **CB_ERR** Wenn `CComboBox` hat die [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) formatieren oder verfügt nicht über ein Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Die Positionen sind nullbasiert. Um das erste Zeichen des Bearbeitungssteuerelements auszuwählen, geben Sie die Startposition 0. Die Endposition ist für das Zeichen direkt hinter dem letzten Zeichen auswählen. Um die ersten vier Zeichen des Bearbeitungssteuerelements ausgewählt haben, würden Sie z. B. Startposition 0 und einer Endposition 4 verwenden.  
  
> [!NOTE]
>  Diese Funktion wird vom Windows **ComboBoxEx** -Steuerelement nicht unterstützt. Weitere Informationen zu diesem Steuerelement finden Sie unter [ComboBoxEx-Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb775738) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CComboBox::GetEditSel](#geteditsel).  
  
##  <a name="setextendedui"></a>CComboBox::SetExtendedUI  
 Rufen Sie die `SetExtendedUI` Memberfunktion versucht, wählen Sie entweder die Standardbenutzeroberfläche oder die erweiterte Benutzeroberfläche für ein Kombinationsfeld, ist die [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.  
  
```  
int SetExtendedUI(BOOL bExtended = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bDie*  
 Gibt an, ob das Kombinationsfeld die erweiterte Benutzeroberfläche oder die Standardbenutzeroberfläche verwenden möchten. Der Wert **"true"** wählt die erweiterte Benutzeroberfläche, der Wert **"false"** wählt die Standardbenutzeroberfläche.  
  
### <a name="return-value"></a>Rückgabewert  
 **CB_OKAY** Wenn der Vorgang erfolgreich ist oder **CB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Die erweiterte Benutzeroberfläche kann auf folgende Weise identifiziert werden:  
  
-   Nach Klicken auf die statisches Steuerelement wird im Listenfeld nur für Kombinationsfelder, mit der **CBS_DROPDOWNLIST** Stil.  
  
-   Drücken die nach-unten-Taste zeigt das Listenfeld (F4 ist deaktiviert).  
  
 Durchführen eines Bildlaufs im statischen Steuerelement ist deaktiviert, wenn die Elementliste nicht angezeigt wird (die Pfeiltasten sind deaktiviert).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CComboBox::GetExtendedUI](#getextendedui).  
  
##  <a name="sethorizontalextent"></a>CComboBox::SetHorizontalExtent  
 Legt die Breite in Pixel, der im Listenfeld Teil des Kombinationsfelds horizontal gescrollt werden kann.  
  
```  
void SetHorizontalExtent(UINT nExtent);
```  
  
### <a name="parameters"></a>Parameter  
 *nExtent*  
 Gibt die Anzahl der Pixel, die mit denen Listenfeld Teil des Kombinationsfelds horizontal gescrollt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Breite des Listenfelds kleiner als dieser Wert ist, wird die horizontale Bildlaufleiste Elemente im Listenfeld die horizontale Bildlaufleiste. Die horizontale Bildlaufleiste wird ausgeblendet, wenn die Breite des Listenfelds gleich oder größer als dieser Wert ist, oder, wenn das Kombinationsfeld kann die [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil deaktiviert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]  
  
##  <a name="setitemdata"></a>CComboBox::SetItemData  
 Legt den 32-Bit-Wert, der das angegebene Element in einem Kombinationsfeld zugeordnet.  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält einen nullbasierte Index des Elements festlegen.  
  
 `dwItemData`  
 Enthält den neuen Wert des Elements zugeordnet werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 **CB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der `SetItemDataPtr` Memberfunktion, wenn die 32-Bit-Element ist ein Zeiger sein.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]  
  
##  <a name="setitemdataptr"></a>CComboBox::SetItemDataPtr  
 Legt den 32-Bit-Wert, der das angegebene Element in einem Kombinationsfeld des angegebenen Zeigers sein zugeordnet ( **"void"\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Enthält einen nullbasierten Index des Elements an.  
  
 `pData`  
 Enthält die Zeiger auf die Verknüpfung mit dem Element.  
  
### <a name="return-value"></a>Rückgabewert  
 **CB_ERR** , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 This-Zeiger bleibt gültig, für die Lebensdauer des im Kombinationsfeld, auch wenn das Element relativen Position innerhalb des Kombinationsfelds ändern kann, wie Elemente hinzugefügt oder entfernt werden. Daher kann der Index des Elements in das Feld ändern, aber der Zeiger bleibt zuverlässige.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]  
  
##  <a name="setitemheight"></a>CComboBox::SetItemHeight  
 Rufen Sie die `SetItemHeight` Memberfunktion versucht, die die Höhe der Listenelemente in einem Kombinationsfeld oder die Höhe des bearbeiten-Steuerelement (oder statischer Text) Teil eines Kombinationsfelds festgelegt.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt an, ob die Höhe der Listenelemente oder die Höhe der Edit-Steuerelement (oder statischer Text) Teil des Kombinationsfelds festgelegt ist.  
  
 Wenn das Kombinationsfeld kann die [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil `nIndex` gibt den nullbasierten Index des Listenelements, dessen Höhe ist auf festgelegt ist, andernfalls werden `nIndex` 0 und die Höhe der alle Liste Elemente festgelegt werden muss.  
  
 Wenn `nIndex` ist-1 und die Höhe des Bearbeitungssteuerelements- oder statischer Text Aspekt des Kombinationsfelds besteht darin, festgelegt werden.  
  
 `cyItemHeight`  
 Gibt die Höhe in Pixel, der im Kombinationsfeld Komponente identifizierten `nIndex`.  
  
### <a name="return-value"></a>Rückgabewert  
 **CB_ERR** , wenn der Index oder der Höhe ungültig, andernfalls 0 ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Höhe der Edit-Steuerelement (oder statischer Text) Teil des Kombinationsfelds ist unabhängig von die Höhe der Listenelemente festgelegt. Eine Anwendung sicherstellen muss, dass die Höhe des Teils bearbeiten-Steuerelement (oder statischer Text) nicht kleiner als die Höhe eines bestimmten Listenfeld-Elements ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]  
  
##  <a name="setlocale"></a>CComboBox::SetLocale  
 Legt den Gebietsschemabezeichner für dieses Kombinationsfelds fest.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>Parameter  
 `nNewLocale`  
 Das neue Gebietsschema Gebietsschemabezeichner (LCID) für das Kombinationsfeld festzulegende Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Gebietsschema-ID (LCID) Wert für dieses Kombinationsfeld.  
  
### <a name="remarks"></a>Hinweise  
 Wenn **SetLocale** nicht aufgerufen wird, die Standardeinstellung Gebietsschema wird vom System abgerufen. Diese Standardgebietsschemas kann geändert werden, mithilfe der Systemsteuerung des regionalen (oder International)-Anwendung.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]  
  
##  <a name="setminvisibleitems"></a>CComboBox::SetMinVisibleItems  
 Legt die minimale Anzahl von sichtbaren Elemente in der Dropdown-Liste des aktuellen Kombinationsfeld-Steuerelement fest.  
  
```  
BOOL SetMinVisibleItems(int iMinVisible);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `iMinVisible`|Gibt die minimale Anzahl von sichtbaren Elemente an.|  
  
### <a name="return-value"></a>Rückgabewert  
 `true`Wenn diese Methode erfolgreich ist; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet die [CB_SETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) Nachricht, die im Windows SDK beschrieben wird.  
  
### <a name="example"></a>Beispiel  
 Das folgende Codebeispiel definiert die Variable `m_combobox`, d. h. verwendet, um ein Kombinationsfeld-Steuerelement programmgesteuert zugreifen. Diese Variable wird im nächsten Beispiel verwendet.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel fügt 20 Elemente in der Dropdown-Liste von einem Kombinationsfeld-Steuerelement. Dann wird angegeben, dass mindestens 10 Elemente angezeigt werden, wenn ein Benutzer auf den Dropdown Pfeil drückt.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="settopindex"></a>CComboBox::SetTopIndex  
 Stellt sicher, dass ein bestimmtes Element im Listenfeld Teil im Kombinationsfeld angezeigt wird.  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Gibt den nullbasierten Index des Elements im Listenfeld an.  
  
### <a name="return-value"></a>Rückgabewert  
 NULL Wenn erfolgreich, oder **CB_ERR** Wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Das System führt einen Bildlauf im Listenfeld, bis das durch angegebene Element `nIndex` wird am oberen Rand der Liste im Feld oder den maximalen Bildlaufbereich wurde erreicht.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]  
  
##  <a name="showdropdown"></a>CComboBox::ShowDropDown  
 Blendet das Listenfeld eines Kombinationsfelds, die verfügt die [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) oder [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.  
  
```  
void ShowDropDown(BOOL bShowIt = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *bShowIt*  
 Gibt an, ob der Dropdown-Listenfeld angezeigt oder ausgeblendet werden. Der Wert **"true"** das Listenfeld zeigt. Der Wert **"false"** Blendet Sie aus dem Listenfeld.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird ein Kombinationsfeld dieses Formats im Listenfeld angezeigt.  
  
 Diese Memberfunktion wirkt sich nicht in einem Kombinationsfeld erstellt, mit der [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) Stil.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CComboBox::GetDroppedState](#getdroppedstate).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel jeder](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [CButton-Klasse](../../mfc/reference/cbutton-class.md)   
 [CEdit-Klasse](../../mfc/reference/cedit-class.md)   
 [CListBox-Klasse](../../mfc/reference/clistbox-class.md)   
 [CScrollBar-Klasse](../../mfc/reference/cscrollbar-class.md)   
 [CStatic-Klasse](../../mfc/reference/cstatic-class.md)   
 [CDialog-Klasse](../../mfc/reference/cdialog-class.md)
