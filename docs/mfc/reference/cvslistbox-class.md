---
title: Cvslistbox-Klasse
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
ms.openlocfilehash: 6a33f5b64c5094bfe2ca2ff259b5cd8654058ed3
ms.sourcegitcommit: 389c559918d9bfaf303d262ee5430d787a662e92
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "69502234"
---
# <a name="cvslistbox-class"></a>Cvslistbox-Klasse

Die `CVSListBox` -Klasse unterstützt ein bearbeitbares Listen Steuerelement.

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
|[CVSListBox::AddItem](#additem)|Fügt einem Listen Steuerelement eine Zeichenfolge hinzu. (Überschreibt `CVSListBoxBase::AddItem`.)|
|[CVSListBox::EditItem](#edititem)|Startet einen Bearbeitungsvorgang für den Text eines Listen Steuerelement Elements. (Überschreibt `CVSListBoxBase::EditItem`.)|
|[CVSListBox::GetCount](#getcount)|Ruft die Anzahl der Zeichen folgen in einem bearbeitbaren Listen Steuerelement ab. (Überschreibt `CVSListBoxBase::GetCount`.)|
|[CVSListBox::GetItemData](#getitemdata)|Ruft einen anwendungsspezifischen 32-Bit-Wert ab, der einem editierbaren Listen Steuerelement zugeordnet ist. (Überschreibt `CVSListBoxBase::GetItemData`.)|
|[CVSListBox::GetItemText](#getitemtext)|Ruft den Text eines bearbeitbaren Listen Steuerelement Elements ab. (Überschreibt `CVSListBoxBase::GetItemText`.)|
|[CVSListBox::GetSelItem](#getselitem)|Ruft den NULL basierten Index des derzeit ausgewählten Elements in einem bearbeitbaren Listen Steuerelement ab. (Überschreibt `CVSListBoxBase::GetSelItem`.)|
|`CVSListBox::PreTranslateMessage`|Übersetzt Fenster Meldungen, bevor diese an die Windows-Funktionen [translatemess](/windows/win32/api/winuser/nf-winuser-translatemessage) und [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) gesendet werden. Weitere Informationen und Methoden Syntax finden Sie unter [CWnd::P retranslatemess Age](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CVSListBoxBase::PreTranslateMessage`.)|
|[CVSListBox::RemoveItem](#removeitem)|Entfernt ein Element aus einem bearbeitbaren Listen Steuerelement. (Überschreibt `CVSListBoxBase::RemoveItem`.)|
|[CVSListBox::SelectItem](#selectitem)|Wählt eine bearbeitbare Listen Steuerungs Zeichenfolge aus. (Überschreibt `CVSListBoxBase::SelectItem`.)|
|[CVSListBox::SetItemData](#setitemdata)|Ordnet einen anwendungsspezifischen 32-Bit-Wert einem bearbeitbaren Listen Steuerungselement zu. (Überschreibt `CVSListBoxBase::SetItemData`.)|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CVSListBox::GetListHwnd](#getlisthwnd)|Gibt das Handle für das aktuelle eingebettete Listenansicht-Steuerelement zurück.|

## <a name="remarks"></a>Hinweise

Die `CVSListBox` -Klasse stellt einen Satz von Bearbeitungs Schaltflächen bereit, mit denen der Benutzer die Elemente in einem Listen Steuerelement erstellen, ändern, löschen oder neu anordnen kann.

Im folgenden finden Sie ein Bild des bearbeitbaren Listen Steuer Elements. Der zweite Listeneintrag mit dem Titel "item2" wird für die Bearbeitung ausgewählt.

![Cvslistbox-Steuer] Element (../../mfc/reference/media/cvslistbox.png "Cvslistbox-Steuer") Element

Wenn Sie den Ressourcen-Editor verwenden, um ein bearbeitbares Listen Steuerelement hinzuzufügen, beachten Sie, dass der Bereich **Toolbox** des Editors kein vordefiniertes bearbeitbares Listen Steuerelement bereitstellt. Fügen Sie stattdessen ein statisches Steuerelement wie das **Gruppenfeld** -Steuerelement hinzu. Das Framework verwendet das statische-Steuerelement als Platzhalter, um die Größe und Position des bearbeitbaren Listen Steuer Elements anzugeben.

Wenn Sie ein Editier bares Listen Steuerelement in einer Dialogfeld Vorlage verwenden `CVSListBox` möchten, deklarieren Sie eine Variable in der Dialogfeld Klasse. Um den Datenaustausch zwischen der Variablen und dem Steuerelement zu unter `DDX_Control` stützen, definieren Sie `DoDataExchange` in der-Methode des Dialog Felds einen Makro Eintrag. Standardmäßig wird das bearbeitbare Listen Steuerelement ohne Bearbeitungs Schaltflächen erstellt. Verwenden Sie die geerbte cvslistboxbase:: setstandardbuttons-Methode, um die Bearbeitungs Schaltflächen zu aktivieren.

Weitere Informationen finden Sie im Beispiel Verzeichnis, im `New Controls` Beispiel, in den Dateien Page3. cpp und Page3. h.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CStatic](../../mfc/reference/cstatic-class.md)

`CVSListBoxBase`

[CVSListBox](../../mfc/reference/cvslistbox-class.md)

## <a name="requirements"></a>Anforderungen

**Header:** afxvslistbox. h

##  <a name="additem"></a>Cvslistbox:: AddItem

Fügt einem Listen Steuerelement eine Zeichenfolge hinzu.

```
virtual int AddItem(
    const CString& strIext,
    DWORD_PTR dwData=0,
    int iIndex=-1);
```

### <a name="parameters"></a>Parameter

*strIext*<br/>
in Ein Verweis auf eine Zeichenfolge.

*dwData*<br/>
in Ein anwendungsspezifischer 32-Bit-Wert, der der Zeichenfolge zugeordnet ist. Der Standardwert ist 0.

*iIndex*<br/>
in Der null basierte Index der Position, an der die Zeichenfolge enthalten sein soll. Wenn der *iIndex* -Parameter-1 ist, wird die Zeichenfolge am Ende der Liste hinzugefügt. Der Standardwert ist -1.

### <a name="return-value"></a>Rückgabewert

Der null basierte Index der Position der Zeichenfolge im Listen Steuerelement.

### <a name="remarks"></a>Hinweise

Verwenden Sie die [cvslistbox:: GetItemData](#getitemdata) -Methode, um den Wert abzurufen, der durch den *dwdata* -Parameter angegeben wird. Bei diesem Wert kann es sich um eine anwendungsspezifische Ganzzahl oder einen Zeiger auf andere Daten handeln.

##  <a name="cvslistbox"></a>Cvslistbox:: cvslistbox

Erstellt ein `CVSListBox`-Objekt.

```
CVSListBox();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

##  <a name="edititem"></a>Cvslistbox:: EditItem

Startet einen Bearbeitungsvorgang für den Text eines Listen Steuerelement Elements.

```
virtual BOOL EditItem(int iIndex);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
in NULL basierter Index eines Listen Steuerelement Elements.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn der Bearbeitungsvorgang erfolgreich gestartet wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

Der Benutzer startet einen Bearbeitungsvorgang entweder durch Doppelklicken auf die Bezeichnung eines Elements oder durch Drücken der Taste **F2** oder **LEERTASTE** , wenn ein Element den Fokus besitzt.

##  <a name="getcount"></a>Cvslistbox:: GetCount

Ruft die Anzahl der Zeichen folgen in einem bearbeitbaren Listen Steuerelement ab.

```
virtual int GetCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Elemente im Listensteuerelement.

### <a name="remarks"></a>Hinweise

Beachten Sie, dass die Anzahl größer ist als der Indexwert des letzten Elements, da der Index NULL basiert ist.

##  <a name="getitemdata"></a>Cvslistbox:: GetItemData

Ruft einen anwendungsspezifischen 32-Bit-Wert ab, der einem editierbaren Listen Steuerelement zugeordnet ist.

```
virtual DWORD_PTR GetItemData(int iIndex) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
in Der null basierte Index eines bearbeitbaren Listen Steuerungs Elements.

### <a name="return-value"></a>Rückgabewert

Der 32-Bit-Wert, der dem angegebenen Element zugeordnet ist.

### <a name="remarks"></a>Hinweise

Verwenden Sie die [cvslistbox:: abtitemdata](#setitemdata) -Methode oder die [cvslistbox:: AddItem](#additem) -Methode, um den 32-Bit-Wert dem Listen Steuerelement zuzuordnen. Bei diesem Wert kann es sich um eine anwendungsspezifische Ganzzahl oder einen Zeiger auf andere Daten handeln.

##  <a name="getitemtext"></a>Cvslistbox:: GetItemText

Ruft den Text eines bearbeitbaren Listen Steuerelement Elements ab.

```
virtual CString GetItemText(int iIndex) const;
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
in Der null basierte Index eines bearbeitbaren Listen Steuerungs Elements.

### <a name="return-value"></a>Rückgabewert

Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den Text des angegebenen Elements enthält.

### <a name="remarks"></a>Hinweise

##  <a name="getlisthwnd"></a>Cvslistbox:: getlisthwnd

Gibt das Handle für das aktuelle eingebettete Listenansicht-Steuerelement zurück.

```
virtual HWND GetListHwnd() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für das eingebettete Listenansicht-Steuerelement.

### <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode, um ein Handle zum eingebetteten Listenansicht-Steuerelement abzurufen `CVSListBox` , das die-Klasse unterstützt.

##  <a name="getselitem"></a>Cvslistbox:: getselitem

Ruft den NULL basierten Index des derzeit ausgewählten Elements in einem bearbeitbaren Listen Steuerelement ab.

```
virtual int GetSelItem() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn diese Methode erfolgreich ist, der null basierte Index des derzeit ausgewählten Elements. andernfalls-1.

### <a name="remarks"></a>Hinweise

##  <a name="removeitem"></a>Cvslistbox:: RemoveItem

Entfernt ein Element aus einem bearbeitbaren Listen Steuerelement.

```
virtual BOOL RemoveItem(int iIndex);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
in Der null basierte Index eines bearbeitbaren Listen Steuerungs Elements.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das angegebene Element entfernt wurde. andernfalls false.

### <a name="remarks"></a>Hinweise

##  <a name="selectitem"></a>Cvslistbox:: SelectItem

Wählt eine bearbeitbare Listen Steuerungs Zeichenfolge aus.

```
virtual BOOL SelectItem(int iItem);
```

### <a name="parameters"></a>Parameter

*iItem*<br/>
in Der null basierte Index eines bearbeitbaren Listen Steuerungs Elements.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn diese Methode erfolgreich ist. andernfalls false.

### <a name="remarks"></a>Hinweise

Diese Methode wählt das angegebene Element aus, und wenn es erforderlich ist, führt einen Bildlauf zum Element durch.

##  <a name="setitemdata"></a>Cvslistbox:: abtitemdata

Ordnet einen anwendungsspezifischen 32-Bit-Wert einem bearbeitbaren Listen Steuerungselement zu.

```
virtual void SetItemData(
    int iIndex,
    DWORD_PTR dwData);
```

### <a name="parameters"></a>Parameter

*iIndex*<br/>
in Der null basierte Index eines bearbeitbaren Listen Steuerungs Elements.

*dwData*<br/>
in Ein 32-Bit-Wert. Bei diesem Wert kann es sich um eine anwendungsspezifische Ganzzahl oder einen Zeiger auf andere Daten handeln.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
