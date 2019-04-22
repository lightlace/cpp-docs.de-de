---
title: CDragListBox-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
helpviewer_keywords:
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
ms.openlocfilehash: d8afc5b14f5f52ca7a4d28a3d3c3c5440b7c819f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781587"
---
# <a name="cdraglistbox-class"></a>CDragListBox-Klasse

Abgesehen von der die Funktionalität eines Windows-Listenfelds die `CDragListBox` Klasse kann der Benutzer Listenfeldelemente, beispielsweise Dateinamen, innerhalb des Listenfelds verschieben.

## <a name="syntax"></a>Syntax

```
class CDragListBox : public CListBox
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDragListBox::CDragListBox](#cdraglistbox)|Erstellt ein `CDragListBox`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDragListBox::BeginDrag](#begindrag)|Wird vom Framework aufgerufen, wenn ein Ziehvorgang gestartet wird.|
|[CDragListBox::CancelDrag](#canceldrag)|Vom Framework aufgerufen, wenn ein Ziehvorgang abgebrochen wurde.|
|[CDragListBox::Dragging](#dragging)|Wird von Framework aufgerufen, während eines Ziehvorgangs.|
|[CDragListBox::DrawInsert](#drawinsert)|Zeichnet die Einfügemarke im Listenfeld Drag an.|
|[CDragListBox::Dropped](#dropped)|Vom Framework aufgerufen, nachdem das Element gelöscht wurde.|
|[CDragListBox::ItemFromPt](#itemfrompt)|Gibt die Koordinaten des gezogenen Elements zurück.|

## <a name="remarks"></a>Hinweise

Listenfelder mit dieser Funktion können Benutzer Elemente in beliebig besonders nützlich für sie ist in einer Liste sortieren. Standardmäßig wird im Listenfeld das Element an den neuen Speicherort in der Liste zu verschieben. Allerdings `CDragListBox` Objekte können angepasst werden, zum Kopieren von Elementen, anstatt sie zu verschieben.

Das Listenfeld-Steuerelement zugeordnete der `CDragListBox` Klasse darf keinen, die LBS_SORT oder den LBS_MULTIPLESELECT-Stil. Eine Beschreibung der Box-Stile aufzulisten, finden Sie unter [Listenfeldstile](../../mfc/reference/styles-used-by-mfc.md#list-box-styles).

Um ein Listenfeld, ziehen Sie das in einem vorhandenen Dialogfeld Ihrer Anwendung verwenden zu können, Ihre Dialogfeldvorlage mithilfe des Dialog-Editors ein Listenfeld-Steuerelement hinzugefügt, und weisen Sie dann eine Membervariable (Kategorie `Control` und Typ der Variable `CDragListBox`) entspricht, in das Listenfeld Steuern Sie in der Dialogfeldvorlage.

Weitere Informationen zum Zuweisen von Membervariablen von Steuerelementen finden Sie unter [Tastenkombination für das Definieren von Membervariablen für Dialogfeld-Steuerelemente](../../windows/defining-member-variables-for-dialog-controls.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CDragListBox`

## <a name="requirements"></a>Anforderungen

**Header:** afxcmn.h

##  <a name="begindrag"></a>  CDragListBox::BeginDrag

Wird aufgerufen, durch das Framework beim Auftreten eines Ereignisses, das einen Ziehvorgang auswirken, z. B. die linke Maustaste drückt einleiten kann.

```
virtual BOOL BeginDrag(CPoint pt);
```

### <a name="parameters"></a>Parameter

*pt*<br/>
Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt, das die Koordinaten des gezogenen Elements enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL Wenn ziehen zulässig ist, andernfalls 0.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, wenn Sie steuern möchten, was geschieht, wenn ein Ziehvorgang begonnen. Die standardmäßige Implementierung die Maus erfasst und in den Dragmodus bleibt, bis der Benutzer klickt auf die linke oder rechte Maustaste gedrückt, oder drücken ESC, woraufhin der Ziehvorgang abgebrochen wird.

##  <a name="canceldrag"></a>  CDragListBox::CancelDrag

Vom Framework aufgerufen, wenn ein Ziehvorgang abgebrochen wurde.

```
virtual void CancelDrag(CPoint pt);
```

### <a name="parameters"></a>Parameter

*pt*<br/>
Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt, das die Koordinaten des gezogenen Elements enthält.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion zur Verarbeitung der speziellen Verarbeitung für Ihre Listenfeld-Steuerelement.

##  <a name="cdraglistbox"></a>  CDragListBox::CDragListBox

Erstellt ein `CDragListBox`-Objekt.

```
CDragListBox();
```

##  <a name="dragging"></a>  CDragListBox::Dragging

Vom Framework aufgerufen, wenn ein Listenfeldelement in gezogen wird, wird die `CDragListBox` Objekt.

```
virtual UINT Dragging(CPoint pt);
```

### <a name="parameters"></a>Parameter

*pt*<br/>
Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) Objekt, das die x- und y enthält die Bildschirmkoordinaten des Cursors.

### <a name="return-value"></a>Rückgabewert

Die Ressourcen-ID des Cursors, der angezeigt werden. Die folgenden Werte sind möglich:

- DL_COPYCURSOR gibt an, dass das Element kopiert werden.

- DL_MOVECURSOR gibt an, dass das Element verschoben wird.

- DL_STOPCURSOR gibt an, dass die aktuellen Ablageziels nicht zulässig ist.

### <a name="remarks"></a>Hinweise

Das Standardverhalten gibt DL_MOVECURSOR zurück. Überschreiben Sie diese Funktion, wenn Sie zusätzliche Funktionen bereitstellen möchten.

##  <a name="drawinsert"></a>  CDragListBox::DrawInsert

Wird aufgerufen, durch das Framework, um den Einfügepunkt vor dem Element mit dem angegebenen Index zu zeichnen.

```
virtual void DrawInsert(int nItem);
```

### <a name="parameters"></a>Parameter

*nItem*<br/>
Nullbasierte Index der Einfügemarke.

### <a name="remarks"></a>Hinweise

Wert von - 1 wird die Einfügemarke gelöscht. Überschreiben Sie diese Funktion, um die Darstellung oder das Verhalten von den Einfügepunkt ändern.

##  <a name="dropped"></a>  CDragListBox::Dropped

Vom Framework aufgerufen, wenn ein Element, innerhalb gelöscht wird einer `CDragListBox` Objekt.

```
virtual void Dropped(
    int nSrcIndex,
    CPoint pt);
```

### <a name="parameters"></a>Parameter

*nSrcIndex*<br/>
Gibt den nullbasierten Index des gelöschten Zeichenfolge an.

*pt*<br/>
Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt, das die Koordinaten der Drop-Website enthält.

### <a name="remarks"></a>Hinweise

Das Standardverhalten das Listenfeldelement und die Daten an den neuen Speicherort kopiert und anschließend wird das ursprüngliche Element gelöscht. Überschreiben Sie diese Funktion, um das Standardverhalten, z. B. das Aktivieren von Kopien der Listenfeldelemente an anderen Speicherorten in der Liste gezogen werden anzupassen.

##  <a name="itemfrompt"></a>  CDragListBox::ItemFromPt

Aufruf dieser Funktion zum Abrufen des nullbasierten Indexes des das Listenfeldelement controllerarbeitsverzeichnis *pt*.

```
int ItemFromPt(
    CPoint pt,
    BOOL bAutoScroll = TRUE) const;
```

### <a name="parameters"></a>Parameter

*pt*<br/>
Ein [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) -Objekt, das die Koordinaten eines Punkts innerhalb des Listenfelds enthält.

*bAutoScroll*<br/>
Ungleich NULL wenn Bildlauf zulässig ist, andernfalls 0.

### <a name="return-value"></a>Rückgabewert

Nullbasierte Index des Listenelements Feld ziehen.

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox-Klasse](../../mfc/reference/clistbox-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CListBox-Klasse](../../mfc/reference/clistbox-class.md)
