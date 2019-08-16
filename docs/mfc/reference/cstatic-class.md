---
title: Cstatic-Klasse
ms.date: 11/04/2016
f1_keywords:
- CStatic
- AFXWIN/CStatic
- AFXWIN/CStatic::CStatic
- AFXWIN/CStatic::Create
- AFXWIN/CStatic::DrawItem
- AFXWIN/CStatic::GetBitmap
- AFXWIN/CStatic::GetCursor
- AFXWIN/CStatic::GetEnhMetaFile
- AFXWIN/CStatic::GetIcon
- AFXWIN/CStatic::SetBitmap
- AFXWIN/CStatic::SetCursor
- AFXWIN/CStatic::SetEnhMetaFile
- AFXWIN/CStatic::SetIcon
helpviewer_keywords:
- CStatic [MFC], CStatic
- CStatic [MFC], Create
- CStatic [MFC], DrawItem
- CStatic [MFC], GetBitmap
- CStatic [MFC], GetCursor
- CStatic [MFC], GetEnhMetaFile
- CStatic [MFC], GetIcon
- CStatic [MFC], SetBitmap
- CStatic [MFC], SetCursor
- CStatic [MFC], SetEnhMetaFile
- CStatic [MFC], SetIcon
ms.assetid: e7c94cd9-5ebd-428a-aa30-b3e51f8efb95
ms.openlocfilehash: fd7b6787b372e220a32770e19d54d149f5ba6934
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502413"
---
# <a name="cstatic-class"></a>Cstatic-Klasse

Stellt die Funktionalität eines statischen Windows-Steuerelements bereit.

## <a name="syntax"></a>Syntax

```
class CStatic : public CWnd
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CStatic::CStatic](#cstatic)|Erstellt ein `CStatic`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CStatic::Create](#create)|Erstellt das statische Windows-Steuerelement und fügt es `CStatic` an das-Objekt an.|
|[CStatic::DrawItem](#drawitem)|Überschreiben Sie, um ein vom Besitzer gezeichnetes statisches Steuerelement|
|[CStatic::GetBitmap](#getbitmap)|Ruft das Handle der Bitmap ab, die zuvor mit [SetBitmap](#setbitmap)festgelegt wurde.|
|[CStatic::GetCursor](#getcursor)|Ruft das Handle des Cursor Bilds ab, das zuvor mit [SetCursor](#setcursor)festgelegt wurde.|
|[CStatic::GetEnhMetaFile](#getenhmetafile)|Ruft das Handle der erweiterten Metadatei ab, die zuvor mit [setenhmetafile](#setenhmetafile)festgelegt wurde.|
|[CStatic::GetIcon](#geticon)|Ruft das Handle des Symbols ab, das zuvor mit [SetIcon](#seticon)festgelegt wurde.|
|[CStatic::SetBitmap](#setbitmap)|Gibt eine Bitmap an, die im statischen Steuerelement angezeigt werden soll.|
|[CStatic::SetCursor](#setcursor)|Gibt ein Cursor Bild an, das im statischen Steuerelement angezeigt werden soll.|
|[CStatic::SetEnhMetaFile](#setenhmetafile)|Gibt eine erweiterte Metadatendatei an, die im statischen Steuerelement angezeigt werden soll.|
|[CStatic::SetIcon](#seticon)|Gibt ein Symbol an, das im statischen Steuerelement angezeigt werden soll.|

## <a name="remarks"></a>Hinweise

Ein statisches Steuerelement zeigt Text Zeichenfolge, Feld, Rechteck, Symbol, Cursor, Bitmap oder erweiterte Metadatei an. Sie kann verwendet werden, um andere Steuerelemente zu bezeichnen, zu unterteilen oder zu trennen. Ein statisches Steuerelement nimmt normalerweise keine Eingabe an und stellt keine Ausgabe bereit. Sie kann jedoch das übergeordnete Element von Mausklicks Benachrichtigen, wenn es mit SS_NOTIFY Style erstellt wird.

Erstellen Sie ein statisches Steuerelement in zwei Schritten. Rufen Sie zuerst den-Konstruktor auf, `CStatic` um das-Objekt zu erstellen, und rufen Sie dann die [Create](#create) Member-Funktion auf, `CStatic` um das statische-Steuerelement zu erstellen und es an das

Wenn Sie ein `CStatic` -Objekt in einem Dialogfeld (über eine Dialogfeld Ressource) erstellen `CStatic` , wird das Objekt automatisch zerstört, wenn der Benutzer das Dialogfeld schließt.

Wenn Sie ein `CStatic` -Objekt in einem-Fenster erstellen, müssen Sie es möglicherweise auch zerstören. Ein `CStatic` -Objekt, das auf dem Stapel innerhalb eines Fensters erstellt wird, wird automatisch zerstört. Wenn Sie das `CStatic` Objekt auf dem Heap mithilfe der **neuen** Funktion erstellen, müssen Sie **Delete** für das-Objekt erstellen, um es zu zerstören, wenn Sie damit abgeschlossen sind.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="create"></a>Cstatic:: Create

Erstellt das statische Windows-Steuerelement und fügt es `CStatic` an das-Objekt an.

```
virtual BOOL Create(
    LPCTSTR lpszText,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID = 0xffff);
```

### <a name="parameters"></a>Parameter

*lpszText*<br/>
Gibt den Text an, der im Steuerelement platziert werden soll. Wenn der Wert NULL ist, wird kein Text angezeigt.

*dwStyle*<br/>
Gibt den Fenster Stil des statischen Steuer Elements an. Wendet eine beliebige Kombination von [statischen Steuer](../../mfc/reference/styles-used-by-mfc.md#static-styles) Element Formaten auf das Steuerelement an.

*Rect*<br/>
Gibt die Position und die Größe des statischen Steuer Elements an. Dabei kann es sich um `RECT` eine Struktur oder `CRect` ein-Objekt handeln.

*pParentWnd*<br/>
Gibt das `CStatic` übergeordnete Fenster an, `CDialog` normalerweise ein-Objekt. Er darf nicht NULL sein.

*nID*<br/>
Gibt die Steuerelement-ID des statischen Steuer Elements an.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Erstellen Sie `CStatic` ein-Objekt in zwei Schritten. Zuerst wird der-Konstruktor `CStatic`aufgerufen, und dann `Create`wird aufgerufen, wodurch das statische Windows-Steuerelement erstellt und `CStatic` an das-Objekt angefügt wird.

Wenden Sie die folgenden [Fenster Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) auf ein statisches Steuerelement an:

- WS_CHILD immer

- WS_VISIBLE normalerweise

- WS_DISABLED selten

Wenn Sie eine Bitmap, einen Cursor, ein Symbol oder eine Metadatei im statischen Steuerelement anzeigen möchten, müssen Sie eines der folgenden [statischen Stile](../../mfc/reference/styles-used-by-mfc.md#static-styles)anwenden:

- SS_BITMAP verwenden Sie diesen Stil für Bitmaps.

- SS_ICON verwenden Sie diesen Stil für Cursor und Symbole.

- SS_ENHMETAFILE verwenden Sie diesen Stil für erweiterte Metadatendateien.

Bei Cursorn, Bitmaps oder Symbolen möchten Sie möglicherweise auch den folgenden Stil verwenden:

- SS_CENTERIMAGE verwenden Sie, um das Bild im statischen Steuerelement zu zentrieren.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

##  <a name="cstatic"></a>Cstatic:: cstatic

Erstellt ein `CStatic`-Objekt.

```
CStatic();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

##  <a name="drawitem"></a>Cstatic::D rawitem

Wird von Framework aufgerufen, um ein vom Besitzer gezeichnetes statisches Steuerelement zu zeichnen.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein Zeiger auf eine [drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) -Struktur. Die-Struktur enthält Informationen zu dem Element, das gezeichnet werden soll, und zum Zeichentyp, der gezeichnet werden soll.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion, um das Zeichnen für ein `CStatic` vom Besitzer gezeichnetes Objekt zu implementieren (das Steuerelement hat den Stil SS_OWNERDRAW).

##  <a name="getbitmap"></a>Cstatic:: getbitmap

Ruft das Handle der Bitmap ab, die zuvor mit [SetBitmap](#setbitmap)festgelegt wurde, das `CStatic`zugeordnet ist.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für die aktuelle Bitmap oder NULL, wenn keine Bitmap festgelegt wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="getcursor"></a>Cstatic:: GetCursor

Ruft das Handle des Cursors ab, der zuvor mit [SetCursor](#setcursor)festgelegt wurde, der `CStatic`zugeordnet ist.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für den aktuellen Cursor oder NULL, wenn kein Cursor festgelegt wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="getenhmetafile"></a>Cstatic:: GetEnhMetaFile

Ruft das Handle der erweiterten Metadatei ab, die zuvor mit " [setenhmetafile](#setenhmetafile)" festgelegt wurde `CStatic`, das zugeordnet ist.

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für die aktuelle erweiterte Metadatendatei oder NULL, wenn keine erweiterte Metadatei festgelegt wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="geticon"></a>Cstatic:: getIcon

Ruft das Handle des Symbols ab, das zuvor mit [SetIcon](#seticon)festgelegt wurde, das `CStatic`zugeordnet ist.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für das aktuelle Symbol oder NULL, wenn kein Symbol festgelegt wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

##  <a name="setbitmap"></a>Cstatic:: SetBitmap

Ordnet dem statischen Steuerelement eine neue Bitmap zu.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parameter

*hBitmap*<br/>
Handle der Bitmap, die im statischen Steuerelement gezeichnet werden soll.

### <a name="return-value"></a>Rückgabewert

Das Handle der Bitmap, das zuvor dem statischen Steuerelement zugeordnet war, oder NULL, wenn dem statischen Steuerelement keine Bitmap zugeordnet wurde.

### <a name="remarks"></a>Hinweise

Die Bitmap wird automatisch im statischen Steuerelement gezeichnet. Standardmäßig wird Sie in der oberen linken Ecke gezeichnet, und die Größe des statischen Steuer Elements wird auf die Größe der Bitmap angepasst.

Sie können verschiedene Fenster-und statische Steuerelement Stile verwenden, einschließlich der folgenden:

- SS_BITMAP verwenden Sie diesen Stil immer für Bitmaps.

- SS_CENTERIMAGE verwenden Sie, um das Bild im statischen Steuerelement zu zentrieren. Wenn das Bild größer als das statische Steuerelement ist, wird es abgeschnitten. Wenn Sie kleiner als das statische Steuerelement ist, wird der leere Leerraum um das Bild durch die Farbe des Pixels in der oberen linken Ecke der Bitmap gefüllt.

- MFC stellt die- `CBitmap`Klasse bereit, die Sie verwenden können, wenn Sie mehr mit einem Bitmap-Bild ausführen müssen, als nur `LoadBitmap`die Win32-Funktion aufzurufen. `CBitmap`, das eine Art von GDI-Objekt enthält, wird häufig in Zusammenarbeit `CStatic`mit verwendet. hierbei `CWnd` handelt es sich um eine Klasse, die zum Anzeigen eines Grafik Objekts als statisches Steuerelement verwendet wird.

`CImage`ist eine ATL-/MFC-Klasse, mit der Sie leichter mit geräteunabhängigen Bitmaps (DIB) arbeiten können. Weitere Informationen finden Sie unter [CImage-Klasse](../../atl-mfc-shared/reference/cimage-class.md).

- Die typische Verwendung besteht darin `CStatic::SetBitmap` , ein GDI-Objekt zu übergeben, das vom HBITMAP- `CBitmap` Operator `CImage` eines-oder-Objekts zurückgegeben wird. Der Code hierfür ähnelt der folgenden Zeile.

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```
Im folgenden Beispiel werden zwei `CStatic` -Objekte auf dem Heap erstellt. Anschließend wird eine mit einer System Bitmap mithilfe `CBitmap::LoadOEMBitmap` von und der andere aus einer `CImage::Load`Datei mit geladen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="setcursor"></a>Cstatic:: SetCursor

Ordnet dem statischen Steuerelement ein neues Cursor Bild zu.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Parameter

*hcursor*<br/>
Handle des Cursors, der im statischen Steuerelement gezeichnet werden soll.

### <a name="return-value"></a>Rückgabewert

Das Handle des Cursors, der zuvor dem statischen Steuerelement zugeordnet wurde, oder NULL, wenn dem statischen Steuerelement kein Cursor zugeordnet wurde.

### <a name="remarks"></a>Hinweise

Der Cursor wird automatisch im statischen Steuerelement gezeichnet. Standardmäßig wird Sie in der oberen linken Ecke gezeichnet, und die Größe des statischen Steuer Elements wird auf die Größe des Cursors angepasst.

Sie können verschiedene Fenster-und statische Steuerelement Stile verwenden, einschließlich der folgenden:

- SS_ICON verwenden Sie diesen Stil immer für Cursor und Symbole.

- SS_CENTERIMAGE verwenden Sie, um im statischen Steuerelement zu zentrieren. Wenn das Bild größer als das statische Steuerelement ist, wird es abgeschnitten. Wenn Sie kleiner als das statische Steuerelement ist, wird der leere Leerraum um das Bild mit der Hintergrundfarbe des statischen Steuer Elements gefüllt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="setenhmetafile"></a>Cstatic:: abtenhmetafile

Ordnet dem statischen Steuerelement ein neues verbessertes Metadateibild zu.

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>Parameter

*hMetaFile*<br/>
Handle der erweiterten Metadatendatei, die im statischen Steuerelement gezeichnet werden soll.

### <a name="return-value"></a>Rückgabewert

Das Handle der erweiterten Metadatei, das zuvor dem statischen Steuerelement zugeordnet wurde, oder NULL, wenn dem statischen Steuerelement keine erweiterte Metadatendatei zugeordnet wurde.

### <a name="remarks"></a>Hinweise

Die erweiterte Metadatei wird automatisch im statischen Steuerelement gezeichnet. Die erweiterte Metadatei wird so skaliert, dass Sie der Größe des statischen Steuer Elements entspricht.

Sie können verschiedene Fenster-und statische Steuerelement Stile verwenden, einschließlich der folgenden:

- SS_ENHMETAFILE verwenden Sie diesen Stil immer für erweiterte Metadatendateien.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="seticon"></a>Cstatic:: abticon

Ordnet dem statischen Steuerelement ein neues Symbolbild zu.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Parameter

*hIcon*<br/>
Handle des Symbols, das im statischen Steuerelement gezeichnet werden soll.

### <a name="return-value"></a>Rückgabewert

Das Handle des Symbols, das zuvor dem statischen Steuerelement zugeordnet wurde, oder NULL, wenn dem statischen Steuerelement kein Symbol zugeordnet wurde.

### <a name="remarks"></a>Hinweise

Das Symbol wird automatisch im statischen Steuerelement gezeichnet. Standardmäßig wird Sie in der oberen linken Ecke gezeichnet, und die Größe des statischen Steuer Elements wird auf die Größe des Symbols angepasst.

Sie können verschiedene Fenster-und statische Steuerelement Stile verwenden, einschließlich der folgenden:

- SS_ICON verwenden Sie diesen Stil immer für Cursor und Symbole.

- SS_CENTERIMAGE verwenden Sie, um im statischen Steuerelement zu zentrieren. Wenn das Bild größer als das statische Steuerelement ist, wird es abgeschnitten. Wenn Sie kleiner als das statische Steuerelement ist, wird der leere Leerraum um das Bild mit der Hintergrundfarbe des statischen Steuer Elements gefüllt.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

## <a name="see-also"></a>Siehe auch

[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CWnd-Klasse](../../mfc/reference/cwnd-class.md)<br/>
[CButton-Klasse](../../mfc/reference/cbutton-class.md)<br/>
[CComboBox-Klasse](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit-Klasse](../../mfc/reference/cedit-class.md)<br/>
[CListBox-Klasse](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar-Klasse](../../mfc/reference/cscrollbar-class.md)<br/>
[CDialog-Klasse](../../mfc/reference/cdialog-class.md)
