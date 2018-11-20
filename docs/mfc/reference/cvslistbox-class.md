---
title: CVSListBox-Klasse
ms.date: 11/19/2018
f1_keywords:
- CVSListBox
- AFXVSLISTBOX/CVSListBox
- AFXVSLISTBOX/CVSListBox::CVSListBox
- AFXVSLISTBOX/CVSListBox::AddItem
- AFXVSLISTBOX/CVSListBox::EditItem
- AFXVSLISTBOX/CVSListBox::GetCount
- AFXVSLISTBOX/CVSListBox::GetItemData
- AFXVSLISTBOX/CVSListBox::GetItemText
- AFXVSLISTBOX/CVSListBox::GetSelItem
- AFXVSLISTBOX/CVSListBox::RemoveItem
- AFXVSLISTBOX/CVSListBox::SelectItem
- AFXVSLISTBOX/CVSListBox::SetItemData
- AFXVSLISTBOX/CVSListBox::GetListHwnd
helpviewer_keywords:
- CVSListBox [MFC], CVSListBox
- CVSListBox [MFC], AddItem
- CVSListBox [MFC], EditItem
- CVSListBox [MFC], GetCount
- CVSListBox [MFC], GetItemData
- CVSListBox [MFC], GetItemText
- CVSListBox [MFC], GetSelItem
- CVSListBox [MFC], RemoveItem
- CVSListBox [MFC], SelectItem
- CVSListBox [MFC], SetItemData
- CVSListBox [MFC], GetListHwnd
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
ms.openlocfilehash: fb12f17aec43653931343e80926d59560d879c3a
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176211"
---
# <a name="cvslistbox-class"></a>CVSListBox-Klasse

Die `CVSListBox` Klasse unterstützt ein bearbeitbares Listensteuerelement.

## <a name="syntax"></a>Syntax

```
class CVSListBox : public CVSListBoxBase
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CVSListBox::CVSListBox](#cvslistbox)|Erstellt ein `CVSListBox`-Objekt.|
|`CVSListBox::~CVSListBox`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CVSListBox::AddItem](#additem)|Fügt eine Zeichenfolge zu einem Listensteuerelement an. (Überschreibt `CVSListBoxBase::AddItem`.)|
|[CVSListBox::EditItem](#edititem)|Startet einen Bearbeitungsvorgang für den Text von einem Steuerelement ein Element an. (Überschreibt `CVSListBoxBase::EditItem`.)|
|[CVSListBox::GetCount](#getcount)|Ruft die Anzahl der Zeichenfolgen in ein bearbeitbares Listensteuerelement. (Überschreibt `CVSListBoxBase::GetCount`.)|
|[CVSListBox::GetItemData](#getitemdata)|Ruft ab eine anwendungsspezifische 32-Bit-Wert, der ein bearbeitbares Listenelement-Steuerelement zugeordnet ist. (Überschreibt `CVSListBoxBase::GetItemData`.)|
|[CVSListBox::GetItemText](#getitemtext)|Ruft den Text ein bearbeitbares Listenelement-Steuerelement. (Überschreibt `CVSListBoxBase::GetItemText`.)|
|[CVSListBox::GetSelItem](#getselitem)|Ruft ab, der nullbasierte Index des derzeit ausgewählten Elements in ein bearbeitbares Listensteuerelement. (Überschreibt `CVSListBoxBase::GetSelItem`.)|
|`CVSListBox::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie um weitergeleitet werden die [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/desktop/api/winuser/nf-winuser-dispatchmessage) Windows-Funktionen. Weitere Informationen und Methodensyntax finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CVSListBoxBase::PreTranslateMessage`.)|
|[CVSListBox::RemoveItem](#removeitem)|Entfernt ein Element aus der ein bearbeitbares Listensteuerelement. (Überschreibt `CVSListBoxBase::RemoveItem`.)|
|[CVSListBox::SelectItem](#selectitem)|Wählt eine bearbeitbare Liste-Zeichenfolge. (Überschreibt `CVSListBoxBase::SelectItem`.)|
|[CVSListBox::SetItemData](#setitemdata)|Ordnet einen anwendungsspezifische 32-Bit-Wert ein bearbeitbares Listenelement-Steuerelement. (Überschreibt `CVSListBoxBase::SetItemData`.)|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CVSListBox::GetListHwnd](#getlisthwnd)|Gibt das Handle an das aktuelle eingebettete Listenansicht-Steuerelement zurück.|

## <a name="remarks"></a>Hinweise

Die `CVSListBox` -Klasse bietet eine Reihe von Bearbeitungsschaltflächen, mit denen Benutzer zu erstellen, ändern, löschen oder neu anordnen der Elemente in einem Listensteuerelement.

Im folgenden finden ein Bild des Steuerelements bearbeitet werden. Der zweite Listeneintrag, der mit dem Titel "Element2" wird zur Bearbeitung ausgewählt.

![CVSListBox-Steuerelement](../../mfc/reference/media/cvslistbox.png "CVSListBox-Steuerelement")

Wenn Sie den Ressourcen-Editor ein bearbeitbares Listensteuerelement hinzufügen mithilfe, beachten Sie, dass die **Toolbox** Bereich des Editors bietet kein vordefinierte bearbeitbares Listensteuerelement. Fügen Sie stattdessen ein statisches Steuerelement z. B. die **Gruppenfeld** Steuerelement. Das Framework verwendet den statischen Steuerelements als Platzhalter an die Größe und Position des Steuerelements bearbeitet werden.

Um ein bearbeitbares Listensteuerelement in eine Dialogfeldvorlage verwenden zu können, deklarieren einen `CVSListBox` Variable in Ihre Dialogfeldklasse. Um den Datenaustausch zwischen Variablen und das Steuerelement zu unterstützen, definieren eine `DDX_Control` Makro-Eintrag in der `DoDataExchange` Methode des Dialogfelds. Standardmäßig wird die bearbeitbares Listensteuerelement ohne Bearbeitungsschaltflächen erstellt. Verwenden Sie die geerbte CVSListBoxBase::SetStandardButtons-Methode, um die Bearbeitungsschaltflächen zu aktivieren.

Weitere Informationen finden Sie im Verzeichnis "Samples", die `New Controls` Beispieldateien, die Page3.cpp und Page3.h.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CStatic](../../mfc/reference/cstatic-class.md)

`CVSListBoxBase`

[CVSListBox](../../mfc/reference/cvslistbox-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxvslistbox.h

##  <a name="additem"></a>  CVSListBox::AddItem

Fügt eine Zeichenfolge zu einem Listensteuerelement an.

```
virtual int AddItem(
    const CString& strIext,
    DWORD_PTR dwData=0,
    int iIndex=-1);
```

### <a name="parameters"></a>Parameter

*strIext*<br/>
[in] Ein Verweis auf eine Zeichenfolge.

*dwData*<br/>
[in] Eine anwendungsspezifische 32-Bit-Wert, der mit der Zeichenfolge zugeordnet ist. Der Standardwert ist 0.

*iIndex*<br/>
[in] Der nullbasierte Index der Position, die die Zeichenfolge enthält. Wenn die *iIndex* -Parameter ist -1, wird die Zeichenfolge am Ende der Liste hinzugefügt. Der Standardwert ist -1.

### <a name="return-value"></a>Rückgabewert

Der nullbasierte Index der Position der Zeichenfolge im Listensteuerelement.

### <a name="remarks"></a>Hinweise

Verwenden der [CVSListBox::GetItemData](#getitemdata) Methode zum Abrufen des Werts, der angegeben wird die *DwData* Parameter. Dieser Wert kann es sich um eine anwendungsspezifische ganze Zahl oder ein Zeiger auf andere Daten sein.

##  <a name="cvslistbox"></a>  CVSListBox::CVSListBox

Erstellt ein `CVSListBox`-Objekt.

```
CVSListBox();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="edititem"></a>  CVSListBox::EditItem

Startet einen Bearbeitungsvorgang für den Text von einem Steuerelement ein Element an.

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Nullbasierte Index von einem Steuerelement ein Element.

### <a name="return-value"></a>Rückgabewert

True, wenn der Bearbeitungsvorgang erfolgreich gestartet wurde. andernfalls "false".

### <a name="remarks"></a>Hinweise

Der Benutzer startet einen Bearbeitungsvorgang durch Doppelklicken auf die Bezeichnung eines Elements, oder drücken Sie die **F2** oder **LEERTASTE** Schlüssel, wenn ein Element den Fokus hat.

##  <a name="getcount"></a>  CVSListBox::GetCount

Ruft die Anzahl der Zeichenfolgen in ein bearbeitbares Listensteuerelement.

```
virtual int GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im Listensteuerelement.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass die Anzahl die eins größer ist als der Indexwert des letzten Elements ist, da der Index nullbasiert ist.

##  <a name="getitemdata"></a>  CVSListBox::GetItemData

Ruft ab eine anwendungsspezifische 32-Bit-Wert, der ein bearbeitbares Listenelement-Steuerelement zugeordnet ist.

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Der nullbasierte Index, der ein bearbeitbares Listenelement-Steuerelement.

### <a name="return-value"></a>Rückgabewert

Der 32-Bit-Wert, der mit dem angegebenen Element zugeordnet ist.

### <a name="remarks"></a>Hinweise

Verwenden der [CVSListBox::SetItemData](#setitemdata) oder [CVSListBox::AddItem](#additem) Methode die 32-Bit-Wert mit dem Listenelement-Steuerelement zugeordnet werden soll. Dieser Wert kann es sich um eine anwendungsspezifische ganze Zahl oder ein Zeiger auf andere Daten sein.

##  <a name="getitemtext"></a>  CVSListBox::GetItemText

Ruft den Text ein bearbeitbares Listenelement-Steuerelement.

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Der nullbasierte Index, der ein bearbeitbares Listenelement-Steuerelement.

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den Text des angegebenen Elements enthält.

### <a name="remarks"></a>Hinweise

##  <a name="getlisthwnd"></a>  CVSListBox::GetListHwnd

Gibt das Handle an das aktuelle eingebettete Listenansicht-Steuerelement zurück.

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für das eingebettete Listenansicht-Steuerelement.

### <a name="remarks"></a>Hinweise

Mit dieser Methode können Sie ein Handle für das eingebettete Listenansicht-Steuerelement abgerufen werden, die unterstützt die `CVSListBox` Klasse.

##  <a name="getselitem"></a>  CVSListBox::GetSelItem

Ruft ab, der nullbasierte Index des derzeit ausgewählten Elements in ein bearbeitbares Listensteuerelement.

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn diese Methode erfolgreich ist, ist der nullbasierte Index des derzeit ausgewählten Elements andernfalls -1.

### <a name="remarks"></a>Hinweise

##  <a name="removeitem"></a>  CVSListBox::RemoveItem

Entfernt ein Element aus der ein bearbeitbares Listensteuerelement.

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Der nullbasierte Index, der ein bearbeitbares Listenelement-Steuerelement.

### <a name="return-value"></a>Rückgabewert

True, wenn das angegebene Element entfernt wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

##  <a name="selectitem"></a>  CVSListBox::SelectItem

Wählt eine bearbeitbare Liste-Zeichenfolge.

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>Parameter

*iItem*<br/>
[in] Der nullbasierte Index, der ein bearbeitbares Listenelement-Steuerelement.

### <a name="return-value"></a>Rückgabewert

True, wenn diese Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Diese Methode wählt das angegebene Element aus, und bei Bedarf, verschiebt das Element in der Ansicht.

##  <a name="setitemdata"></a>  CVSListBox::SetItemData

Ordnet einen anwendungsspezifische 32-Bit-Wert ein bearbeitbares Listenelement-Steuerelement.

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
[in] Der nullbasierte Index, der ein bearbeitbares Listenelement-Steuerelement.

*dwData*<br/>
[in] Ein 32-Bit-Wert. Dieser Wert kann es sich um eine anwendungsspezifische ganze Zahl oder ein Zeiger auf andere Daten sein.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
