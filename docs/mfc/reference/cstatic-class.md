---
title: CStatic-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 084a3101b7415ae4b77ed11070c893a7bc44ac37
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439665"
---
# <a name="cstatic-class"></a>CStatic-Klasse

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
|[CStatic::Create](#create)|Erstellt die statische Windows-Steuerelement, und fügt es der `CStatic` Objekt.|
|[CStatic::DrawItem](#drawitem)|Außer Kraft setzen Sie, um ein vom Besitzer gezeichnetes statisches Steuerelement zu zeichnen.|
|[CStatic::GetBitmap](#getbitmap)|Ruft das Handle der Bitmap für die zuvor festgelegten mit [SetBitmap](#setbitmap).|
|[CStatic::GetCursor](#getcursor)|Ruft das Handle des Cursors Image zuvor festgelegt wird, mit [SetCursor](#setcursor).|
|[CStatic::GetEnhMetaFile](#getenhmetafile)|Ruft das Handle der erweiterten Metadatei mit zuvor festgelegten [SetEnhMetaFile](#setenhmetafile).|
|[CStatic::GetIcon](#geticon)|Ruft das Handle des Symbols, das zuvor mit festgelegten [SetIcon](#seticon).|
|[CStatic::SetBitmap](#setbitmap)|Gibt an, eine Bitmap im statischen Steuerelements angezeigt wird.|
|[CStatic::SetCursor](#setcursor)|Gibt ein Cursorbild im statischen Steuerelements angezeigt wird.|
|[CStatic::SetEnhMetaFile](#setenhmetafile)|Gibt an, eine erweiterte Metadatei im statischen Steuerelements angezeigt wird.|
|[CStatic::SetIcon](#seticon)|Gibt ein Symbol im statischen Steuerelements angezeigt wird.|

## <a name="remarks"></a>Hinweise

Ein statisches Steuerelement zeigt eine Textzeichenfolge, Box, Rechteck, Symbol, Cursor, Bitmap oder erweiterte Metadatei an. Sie können zu bezeichnen, Feld oder separat von anderen Steuerelementen verwendet werden. Ein statisches Steuerelement normalerweise keine Eingabe erfordert und keine Ausgabe enthält; Sie können jedoch übergeordneten Mausklicks benachrichtigt, wenn er mit SS_NOTIFY-Format erstellt wird.

Erstellen Sie ein statisches Steuerelement in zwei Schritten. Rufen Sie zunächst den Konstruktor zum Erstellen der `CStatic` Objekt aus, und rufen Sie dann die [erstellen](#create) Member-Funktion zum Erstellen des statischen Steuerelements und fügen Sie ihn auf die `CStatic` Objekt.

Bei der Erstellung einer `CStatic` Objekt in einem Dialogfeld (mithilfe einer Ressource), die `CStatic` Objekt wird automatisch zerstört, wenn der Benutzer das Dialogfeld geschlossen wird.

Bei der Erstellung einer `CStatic` Objekt innerhalb eines Zeitfensters, Sie müssen möglicherweise auch zerstören. Ein `CStatic` -Objekt erstellt, auf dem Stapel innerhalb eines Fensters automatisch gelöscht. Bei der Erstellung der `CStatic` Objekt auf dem Heap mit dem **neue** -Funktion, die Sie aufrufen müssen **löschen** auf das Objekt, das es zerstört, wenn Sie mehr benötigt werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CStatic`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="create"></a>  CStatic::Create

Erstellt die statische Windows-Steuerelement, und fügt es der `CStatic` Objekt.

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
Gibt den Text im Steuerelement platziert. Wenn der Wert NULL ist, werden ohne Text angezeigt.

*dwStyle*<br/>
Gibt die Fensterstil des statischen Steuerelements an. Wenden Sie eine beliebige Kombination von [Steuerelementtypen für die statische](../../mfc/reference/styles-used-by-mfc.md#static-styles) an das Steuerelement.

*Rect*<br/>
Gibt die Position und Größe des statischen Steuerelements an. Es kann sein, entweder eine `RECT` Struktur oder ein `CRect` Objekt.

*pParentWnd*<br/>
Gibt an, die `CStatic` übergeordnete Fenster, in der Regel eine `CDialog` Objekt. Es darf nicht NULL sein.

*nID*<br/>
Gibt an, der statische ID des Steuerelements-Steuerelement

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Erstellen einer `CStatic` Objekt in zwei Schritten. Rufen Sie zunächst den Konstruktor `CStatic`, und rufen Sie anschließend `Create`, die die statische Windows-Steuerelement erstellt, und fügt es der `CStatic` Objekt.

Übernehmen Sie das folgende [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) auf ein statisches Steuerelement:

- WS_CHILD immer

- WS_VISIBLE in der Regel

- WS_DISABLED selten

Wenn Sie vorhaben, um eine Bitmap, Cursor, Symbol oder Metadatei in statischen Steuerelements anzuzeigen, müssen Sie eine der folgenden Bedingungen [statische Stile](../../mfc/reference/styles-used-by-mfc.md#static-styles):

- SS_BITMAP verwenden Sie dieses Format für Bitmaps.

- SS_ICON verwenden Sie dieses Format für Cursor und Symbole.

- SS_ENHMETAFILE verwenden Sie dieses Format für Metadateien.

Cursor, Bitmaps oder Symbole können Sie auch das folgende Format verwenden möchten:

- SS_CENTERIMAGE-verwenden, um das Bild in statischen Steuerelements zentriert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#1](../../mfc/reference/codesnippet/cpp/cstatic-class_1.cpp)]

##  <a name="cstatic"></a>  CStatic::CStatic

Erstellt ein `CStatic`-Objekt.

```
CStatic();
```

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#2](../../mfc/reference/codesnippet/cpp/cstatic-class_2.cpp)]

##  <a name="drawitem"></a>  CStatic::DrawItem

Wird aufgerufen, durch das Framework um ein vom Besitzer gezeichnetes statisches Steuerelement zu zeichnen.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parameter

*lpDrawItemStruct*<br/>
Ein Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) Struktur. Die Struktur enthält Informationen über das Element, das gezeichnet werden und den Typ der Zeichnung, die erforderlich sind.

### <a name="remarks"></a>Hinweise

Überschreiben Sie diese Funktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CStatic` Objekt (das Steuerelement hat das Format SS_OWNERDRAW).

##  <a name="getbitmap"></a>  CStatic::GetBitmap

Ruft das Handle für die Bitmap, die zuvor festgelegten mit [SetBitmap](#setbitmap), d. h. zugeordneten `CStatic`.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für die aktuelle Bitmap oder NULL, wenn keine Bitmap festgelegt wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="getcursor"></a>  CStatic::GetCursor

Ruft das Handle des Cursors, der zuvor festgelegten mit [SetCursor](#setcursor), d. h. zugeordneten `CStatic`.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für den aktuellen Cursor oder NULL, wenn kein Cursor festgelegt wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="getenhmetafile"></a>  CStatic::GetEnhMetaFile

Ruft das Handle der erweiterten Metadatei, die zuvor festgelegten mit [SetEnhMetafile](#setenhmetafile), d. h. zugeordneten `CStatic`.

```
HENHMETAFILE GetEnhMetaFile() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für die aktuelle erweiterte Metadatei oder NULL, wenn keine erweiterte Metadatei festgelegt wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="geticon"></a>  CStatic::GetIcon

Ruft das Handle für das Symbol, die zuvor festgelegten mit [SetIcon](#seticon), d. h. zugeordneten `CStatic`.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für das aktuelle Symbol oder NULL, wenn das Symbol "keine" festgelegt wurde.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#6](../../mfc/reference/codesnippet/cpp/cstatic-class_6.cpp)]

##  <a name="setbitmap"></a>  CStatic::SetBitmap

Ordnet eine neue Bitmap mit statischen Steuerelements an.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parameter

*hBitmap*<br/>
Handle der Bitmap in statischen Steuerelements gezeichnet wird.

### <a name="return-value"></a>Rückgabewert

Das Handle der Bitmap, die zuvor mit der statischen Steuerelements oder NULL, verknüpft wurde, wenn keine Bitmap dem statischen Steuerelement zugeordnet wurde.

### <a name="remarks"></a>Hinweise

Die Bitmap wird automatisch in statischen Steuerelements gezeichnet werden. Standardmäßig wird Sie in der oberen linken Ecke gezeichnet werden, und statischen Steuerelements wird auf die Größe der Bitmap für die Größe geändert werden.

Sie können verschiedene Fenster und statische Steuerelementstile, u.a. folgende:

- SS_BITMAP verwenden Sie dieses Format für Bitmaps für immer.

- SS_CENTERIMAGE-verwenden, um das Bild in statischen Steuerelements zentriert. Wenn das Bild größer als das Steuerelement statisch ist, wird es abgeschnitten. Wenn es kleiner als das Steuerelement statisch ist, wird der freie Speicherplatz, um das Bild durch die Farbe des Pixels in der oberen linken Ecke der Bitmap aufgefüllt werden.

- MFC stellt die Klasse `CBitmap`, die Sie verwenden können, wenn Sie mehr mit einem Bitmapbild als rufen Sie einfach auf die Win32 funktionieren müssen `LoadBitmap`. `CBitmap`, enthält eine Art von GDI-Objekt, werden häufig in Zusammenarbeit mit `CStatic`, d.h. eine `CWnd` -Klasse, die für die Anzeige eines Grafikobjekts als ein statisches Steuerelement verwendet wird.

`CImage` ist eine ATL/MFC-Klasse, die Sie ganz einfach mit dem Gerät unabhängig von Bitmaps (DIBs) arbeiten kann. Weitere Informationen finden Sie unter [CImage-Klasse](../../atl-mfc-shared/reference/cimage-class.md).

- Typischerweise werden gerne `CStatic::SetBitmap` ein GDI-Objekt, das von der HBITMAP-Operator, der zurückgegeben wird ein `CBitmap` oder `CImage` Objekt. Der Code hierfür ähnelt die folgende Zeile.

```
MyStaticControl.SetBitmap(HBITMAP(MyBitmap));
```
Das folgende Beispiel erstellt zwei `CStatic` Objekte im Heap. Daraufhin lädt er eine mit einem Bitmap mit `CBitmap::LoadOEMBitmap` und die andere aus einer Datei mit `CImage::Load`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#3](../../mfc/reference/codesnippet/cpp/cstatic-class_3.cpp)]

##  <a name="setcursor"></a>  CStatic::SetCursor

Ordnet ein neues Image der Cursor mit statischen Steuerelements an.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Parameter

*hCursor*<br/>
Handle des Cursors in statischen Steuerelements gezeichnet wird.

### <a name="return-value"></a>Rückgabewert

Das Handle des Cursors zuvor zugeordnet waren der statischen Steuerelements oder NULL, wenn kein Cursor statischen Steuerelements zugeordnet wurde.

### <a name="remarks"></a>Hinweise

Der Cursor wird automatisch in statischen Steuerelements gezeichnet werden. Standardmäßig wird Sie in der oberen linken Ecke gezeichnet werden, und des statischen Steuerelements wird auf die Größe des Cursors geändert werden.

Sie können verschiedene Fenster und statisches Steuerelement-Formatvorlagen, einschließlich der folgenden verwenden:

- SS_ICON verwenden dieses Format immer für Cursor und Symbole.

- SS_CENTERIMAGE-Verwendung in statischen Steuerelements zentriert. Wenn das Bild größer als das Steuerelement statisch ist, wird es abgeschnitten. Wenn es kleiner als das Steuerelement statisch ist, wird der freie Speicherplatz, um das Bild mit der Hintergrundfarbe des statischen Steuerelements gefüllt werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#4](../../mfc/reference/codesnippet/cpp/cstatic-class_4.cpp)]

##  <a name="setenhmetafile"></a>  CStatic::SetEnhMetaFile

Ordnet ein neues Image für die erweiterte Metadatei mit statischen Steuerelements an.

```
HENHMETAFILE SetEnhMetaFile(HENHMETAFILE hMetaFile);
```

### <a name="parameters"></a>Parameter

*hMetaFile*<br/>
Handle der erweiterten Metadatei in statischen Steuerelements gezeichnet wird.

### <a name="return-value"></a>Rückgabewert

Das Handle der erweiterten Metadatei zuvor zugeordnet waren der statischen Steuerelements oder NULL, wenn keine erweiterte Metadatei statischen Steuerelements zugeordnet wurde.

### <a name="remarks"></a>Hinweise

Die erweiterte Metadatei wird automatisch in statischen Steuerelements gezeichnet werden soll. Die erweiterte Metadatei wird skaliert, um die Größe des statischen Steuerelements an.

Sie können verschiedene Fenster und statisches Steuerelement-Formatvorlagen, einschließlich der folgenden verwenden:

- SS_ENHMETAFILE verwenden immer diese Art von verbesserten für Metadateien.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFC_CStatic#5](../../mfc/reference/codesnippet/cpp/cstatic-class_5.cpp)]

##  <a name="seticon"></a>  CStatic::SetIcon

Ordnet ein neues Symbol-Image mithilfe des statischen Steuerelements an.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Parameter

*hIcon*<br/>
Handle des Symbols, das in statischen Steuerelements gezeichnet werden soll.

### <a name="return-value"></a>Rückgabewert

Das Handle des Symbols, das zuvor zugeordnet waren der statischen Steuerelements oder NULL, wenn kein Symbol des statischen Steuerelements zugeordnet wurde.

### <a name="remarks"></a>Hinweise

Das Symbol wird automatisch in statischen Steuerelements gezeichnet werden soll. Standardmäßig wird Sie in der oberen linken Ecke gezeichnet werden, und des statischen Steuerelements wird auf die Größe des Symbols, das geändert werden.

Sie können verschiedene Fenster und statisches Steuerelement-Formatvorlagen, einschließlich der folgenden verwenden:

- SS_ICON verwenden dieses Format immer für Cursor und Symbole.

- SS_CENTERIMAGE-Verwendung in statischen Steuerelements zentriert. Wenn das Bild größer als das Steuerelement statisch ist, wird es abgeschnitten. Wenn es kleiner als das Steuerelement statisch ist, wird der freie Speicherplatz, um das Bild mit der Hintergrundfarbe des statischen Steuerelements gefüllt werden.

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
