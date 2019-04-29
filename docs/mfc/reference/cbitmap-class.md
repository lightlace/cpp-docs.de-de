---
title: CBitmap-Klasse
ms.date: 11/04/2016
f1_keywords:
- CBitmap
- AFXWIN/CBitmap
- AFXWIN/CBitmap::CBitmap
- AFXWIN/CBitmap::CreateBitmap
- AFXWIN/CBitmap::CreateBitmapIndirect
- AFXWIN/CBitmap::CreateCompatibleBitmap
- AFXWIN/CBitmap::CreateDiscardableBitmap
- AFXWIN/CBitmap::FromHandle
- AFXWIN/CBitmap::GetBitmap
- AFXWIN/CBitmap::GetBitmapBits
- AFXWIN/CBitmap::GetBitmapDimension
- AFXWIN/CBitmap::LoadBitmap
- AFXWIN/CBitmap::LoadMappedBitmap
- AFXWIN/CBitmap::LoadOEMBitmap
- AFXWIN/CBitmap::SetBitmapBits
- AFXWIN/CBitmap::SetBitmapDimension
helpviewer_keywords:
- CBitmap [MFC], CBitmap
- CBitmap [MFC], CreateBitmap
- CBitmap [MFC], CreateBitmapIndirect
- CBitmap [MFC], CreateCompatibleBitmap
- CBitmap [MFC], CreateDiscardableBitmap
- CBitmap [MFC], FromHandle
- CBitmap [MFC], GetBitmap
- CBitmap [MFC], GetBitmapBits
- CBitmap [MFC], GetBitmapDimension
- CBitmap [MFC], LoadBitmap
- CBitmap [MFC], LoadMappedBitmap
- CBitmap [MFC], LoadOEMBitmap
- CBitmap [MFC], SetBitmapBits
- CBitmap [MFC], SetBitmapDimension
ms.assetid: 3980616a-c59d-495a-86e6-62bd3889c84c
ms.openlocfilehash: 11e210680bdf68f1a1dcbfaed18ae56ce006c8ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388448"
---
# <a name="cbitmap-class"></a>CBitmap-Klasse

Kapselt eine Bitmap der Windows GDI (Graphics Device Interface) und stellt Memberfunktionen zur Bearbeitung der Bitmap bereit.

## <a name="syntax"></a>Syntax

```
class CBitmap : public CGdiObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CBitmap::CBitmap](#cbitmap)|Erstellt ein `CBitmap`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CBitmap::CreateBitmap](#createbitmap)|Initialisiert das Objekt mit einem Gerät geräteabhängige speicherbitmap, die einer angegebenen Breite, Höhe und Bitmuster aufweist.|
|[CBitmap::CreateBitmapIndirect](#createbitmapindirect)|Initialisiert das Objekt mit einer Bitmap mit Breite, Höhe und Bitmuster (sofern vorhanden) im angegebenen ein `BITMAP` Struktur.|
|[CBitmap::CreateCompatibleBitmap](#createcompatiblebitmap)|Initialisiert das Objekt mit einer Bitmap, damit er mit einem angegebenen Gerät kompatibel ist.|
|[CBitmap::CreateDiscardableBitmap](#creatediscardablebitmap)|Initialisiert das Objekt mit einer entfernbare Bitmap, die mit einem angegebenen Gerät kompatibel ist.|
|[CBitmap::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CBitmap` Objekt, wenn ein Handle auf ein Windows gewährt `HBITMAP` Bitmap.|
|[CBitmap::GetBitmap](#getbitmap)|Füllt ein `BITMAP` -Struktur mit Informationen über die Bitmap.|
|[CBitmap::GetBitmapBits](#getbitmapbits)|Kopiert die angegebene Bitmap die Bits in den angegebenen Puffer.|
|[CBitmap::GetBitmapDimension](#getbitmapdimension)|Gibt die Breite und Höhe der Bitmap. Die Höhe und Breite werden als zuvor festgelegt wurden, indem die [SetBitmapDimension](#setbitmapdimension) Member-Funktion.|
|[CBitmap::LoadBitmap](#loadbitmap)|Initialisiert das Objekt von einer benannten Bitmap-Ressource aus der ausführbaren Datei der Anwendung geladen und Anfügen der Bitmaps auf das Objekt an.|
|[CBitmap::LoadMappedBitmap](#loadmappedbitmap)|Lädt eine Bitmap und aktuelle Systemfarben Farben zugeordnet.|
|[CBitmap::LoadOEMBitmap](#loadoembitmap)|Initialisiert das Objekt durch eine vordefinierte Windows-Bitmap zu laden und Anfügen der Bitmaps auf das Objekt an.|
|[CBitmap::SetBitmapBits](#setbitmapbits)|Legt die Bits einer Bitmap auf die angegebene Bit fest.|
|[CBitmap::SetBitmapDimension](#setbitmapdimension)|Weist eine Breite und Höhe einer Bitmap in Einheiten von 0.1-Millimeter.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CBitmap::operator HBITMAP](#operator_hbitmap)|Gibt zurück, das Windows-Handle, das angefügt wird, um die `CBitmap` Objekt.|

## <a name="remarks"></a>Hinweise

Verwenden einer `CBitmap` Objekt, das Objekt zu erstellen, fügen Sie ein Bitmaphandle an mit einem der Initialisierung Memberfunktionen und rufen Sie dann die Member des Objekts Funktionen.

Weitere Informationen zur Verwendung von Grafikobjekten wie `CBitmap`, finden Sie unter [Grafik Objekte](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBitmap`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cbitmap"></a>  CBitmap::CBitmap

Erstellt ein `CBitmap`-Objekt.

```
CBitmap();
```

### <a name="remarks"></a>Hinweise

Das resultierende Objekt muss mit einem der Memberfunktionen Initialisierung initialisiert werden.

##  <a name="createbitmap"></a>  CBitmap::CreateBitmap

Initialisiert eine geräteabhängige Speicherbitmap, die die angegebene Breite, Höhe und das angegebene Bitmuster aufweist.

```
BOOL CreateBitmap(
    int nWidth,
    int nHeight,
    UINT nPlanes,
    UINT nBitcount,
    const void* lpBits);
```

### <a name="parameters"></a>Parameter

*nWidth*<br/>
Gibt die Breite der Bitmap (in Pixeln) an.

*nHeight*<br/>
Gibt die Höhe der Bitmap (in Pixeln) an.

*nPlanes*<br/>
Gibt die Anzahl von Farbebenen in der Bitmap an.

*nBitcount*<br/>
Gibt die Anzahl der Farbbits pro Anzeigepixel an.

*lpBits*<br/>
Zeigt auf ein Array von Bytes, das die ursprünglichen Bitwerte der Bitmap enthält. Wenn es NULL ist, bleibt die neue Bitmap nicht initialisiert.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Für eine Farbbitmap muss entweder die *nPlanes* oder *nBitcount* Parameter sollte auf 1 festgelegt werden. Wenn beide Parameter auf 1 festgelegt sind, erstellt `CreateBitmap` eine monochrome Bitmap.

Obwohl eine Bitmap nicht direkt für ein Anzeigegerät ausgewählt werden kann, kann sie als aktuelle Bitmap für einen „Speichergerätekontext“ mithilfe von [CDC::SelectObject](../../mfc/reference/cdc-class.md#selectobject) ausgewählt und mithilfe der [CDC::BitBlt](../../mfc/reference/cdc-class.md#bitblt) -Funktion auf einen beliebigen kompatiblen Gerätekontext kopiert werden.

Wenn Sie mit dem `CBitmap` -Objekt fertig sind, das von der `CreateBitmap` -Funktion erstellt wurde, wählen Sie zunächst die Bitmap im Gerätekontext aus, und löschen Sie dann das `CBitmap` -Objekt.

Weitere Informationen finden Sie unter der Beschreibung des der `bmBits` -Feld in der `BITMAP` Struktur. Die [BITMAP](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap) -Struktur wird unter der [CBitmap::CreateBitmapIndirect](#createbitmapindirect) -Memberfunktion beschrieben.

##  <a name="createbitmapindirect"></a>  CBitmap::CreateBitmapIndirect

Initialisiert eine Bitmap, die Breite, Höhe und die Bitmuster (sofern vorhanden), die in der Struktur verweist erhält *LpBitmap*.

```
BOOL CreateBitmapIndirect(LPBITMAP lpBitmap);
```

### <a name="parameters"></a>Parameter

*lpBitmap*<br/>
Verweist auf eine [BITMAP](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap) -Struktur, die Informationen über die Bitmap enthält.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Obwohl eine Bitmap kann nicht direkt für ein Anzeigegerät ausgewählt werden, es kann ausgewählt werden als aktuelle Bitmap für einen Gerätekontext Arbeitsspeicher mit [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) und auf einen beliebigen kompatiblen Gerätekontext kopiert werden, mithilfe der [CDC:: BitBlt](../../mfc/reference/cdc-class.md#bitblt) oder [CDC::StretchBlt](../../mfc/reference/cdc-class.md#stretchblt) Funktion. (Die [CDC::PatBlt](../../mfc/reference/cdc-class.md#patblt) Funktion kann die Bitmap für den aktuellen Pinsel direkt für den Anzeigekontext für das Gerät kopieren.)

Wenn die `BITMAP` Struktur, um die durch die *LpBitmap* Parameter ausgefüllt wurde mithilfe der `GetObject` -Funktion, die Bits der Bitmap nicht angegeben sind, und die Bitmap nicht initialisiert ist. Um die Bitmap zu initialisieren, eine Anwendung können eine Funktion wie z. B. [CDC:: BitBlt](../../mfc/reference/cdc-class.md#bitblt) oder [SetDIBits](/windows/desktop/api/wingdi/nf-wingdi-setdibits) zum Kopieren von Bits aus der Bitmap, die den ersten Parameter identifizierte `CGdiObject::GetObject` auf die Bitmap erstellt `CreateBitmapIndirect`.

Wenn Sie fertig sind, mit der `CBitmap` mit erstelltes Objekt `CreateBitmapIndirect` funktionieren müssen zunächst die Bitmap im Gerätekontext auswählen und dann Löschen der `CBitmap` Objekt.

##  <a name="createcompatiblebitmap"></a>  CBitmap::CreateCompatibleBitmap

Initialisiert eine Bitmap, die kompatibel mit dem Gerät gemäß *pDC*.

```
BOOL CreateCompatibleBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Gibt den Gerätekontext.

*nWidth*<br/>
Gibt die Breite der Bitmap (in Pixeln) an.

*nHeight*<br/>
Gibt die Höhe der Bitmap (in Pixeln) an.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Die Bitmap hat die gleiche Anzahl von Farbebenen oder das gleiche Bits pro Pixel-Format als den angegebenen Gerätekontext. Es kann ausgewählt werden, als aktuelle Bitmap für alle Speicher-Geräte, die kompatibel mit dem von *pDC*.

Wenn *pDC* ist ein Arbeitsspeicher-Gerätekontext, die Bitmap zurückgegeben hat das gleiche Format wie das aktuell ausgewählte Bitmuster in dieser Gerätekontext. Ein "Speichergerätekontext" ist ein Speicherblock, der eine Anzeigeoberfläche darstellt. Es kann verwendet werden, zum Vorbereiten von Images im Arbeitsspeicher, bevor sie in der der tatsächlichen Anzeigeoberfläche das kompatible Gerät kopiert.

Wenn ein Arbeitsspeicher-Gerätekontext erstellt wird, wählt GDI automatisch eine monochrome Bitmap für die vordefinierte dafür.

Da ein Farbe Speichergerätekontext "Color" oder monochrome Bitmaps ausgewählt aufweisen kann, wird das Format der Bitmap von zurückgegebenen der `CreateCompatibleBitmap` Funktion ist nicht immer identisch; allerdings ist das Format einer Bitmap kompatibel, für einen Gerätekontext Panik immer in der Format des Geräts.

Wenn Sie fertig sind, mit der `CBitmap` Objekt erstellt wurde, mit der `CreateCompatibleBitmap` Funktion, zunächst die Bitmap im Gerätekontext auswählen und dann löschen Sie die `CBitmap` Objekt.

##  <a name="creatediscardablebitmap"></a>  CBitmap::CreateDiscardableBitmap

Initialisiert eine entfernbare Bitmap, die kompatibel mit den Gerätekontext identifizierte *pDC*.

```
BOOL CreateDiscardableBitmap(
    CDC* pDC,
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parameter

*pDC*<br/>
Gibt einen Gerätekontext.

*nWidth*<br/>
Gibt die Breite (in Bit) der Bitmap.

*nHeight*<br/>
Gibt die Höhe (in Bit) der Bitmap.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Die Bitmap hat die gleiche Anzahl von Farbebenen oder das gleiche Bits pro Pixel-Format als den angegebenen Gerätekontext. Eine Anwendung kann diese Bitmap auswählen, als aktuelle Bitmap für ein Speichergerät, die kompatibel mit dem von *pDC*.

Windows kann eine Bitmap, die von dieser Funktion nur erstellt, wenn eine Anwendung sie nicht in einen Anzeigekontext ausgewählt wurde verworfen. Wenn Windows die Bitmap verwirft, wenn es nicht aktiviert ist und die Anwendung später versucht wird, um diese auszuwählen, die [CDC:: SelectObject](../../mfc/reference/cdc-class.md#selectobject) die Funktion gibt NULL zurück.

Wenn Sie fertig sind, mit der `CBitmap` Objekt erstellt wurde, mit der `CreateDiscardableBitmap` Funktion, zunächst die Bitmap im Gerätekontext auswählen und dann löschen Sie die `CBitmap` Objekt.

##  <a name="fromhandle"></a>  CBitmap::FromHandle

Gibt einen Zeiger auf eine `CBitmap` Objekt, wenn ein Handle für eine Windows-GDI-Bitmap zu erhalten.

```
static CBitmap* PASCAL FromHandle(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parameter

*hBitmap*<br/>
Gibt an, eine Windows-GDI-Bitmap.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine `CBitmap` -Objekt, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn eine `CBitmap` Objekt ist noch nicht auf das Handle, eine temporäre angefügt `CBitmap` Objekt erstellt und angefügt. Diese temporären `CBitmap` Objekt ist nur dann gültig, bis das nächste Mal die Anwendung Zeit im Leerlauf in seiner Ereignisschleife verfügt, an der Zeit, dass alle temporären Grafik Objekte gelöscht werden. Anders ausgedrückt: Dies ist, dass der Zugriff auf das temporäre Objekt während der Verarbeitung der Nachricht von einem Fenster nur gültig ist.

##  <a name="getbitmap"></a>  CBitmap::GetBitmap

Ruft die Eigenschaften für die angefügten Bitmap ab.

```
int GetBitmap(BITMAP* pBitMap);
```

### <a name="parameters"></a>Parameter

*pBitMap*<br/>
Zeiger auf eine [BITMAP](/windows/desktop/api/wingdi/ns-wingdi-tagbitmap) -Struktur, die die abbildeigenschaften erhält. Dieser Parameter darf nicht NULL sein.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die Methode erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

##  <a name="getbitmapbits"></a>  CBitmap::GetBitmapBits

Kopiert das Bitmuster der Bitmap für die angefügten in den angegebenen Puffer.

```
DWORD GetBitmapBits(
    DWORD dwCount,
    LPVOID lpBits) const;
```

### <a name="parameters"></a>Parameter

*dwCount*<br/>
Die Anzahl von Bytes, die in den Puffer kopiert werden sollen.

*lpBits*<br/>
Zeiger auf den Puffer, der die Bitmap erhält.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Bytes, die in den Puffer kopiert werden, wenn die Methode erfolgreich war; andernfalls 0.

### <a name="remarks"></a>Hinweise

Verwendung [CBitmap::GetBitmap](#getbitmap) um die Größe des erforderlichen Puffers zu bestimmen.

##  <a name="getbitmapdimension"></a>  CBitmap::GetBitmapDimension

Gibt die Breite und Höhe der Bitmap.

```
CSize GetBitmapDimension() const;
```

### <a name="return-value"></a>Rückgabewert

Die Breite und Höhe der Bitmap, gemessen in Einheiten von 0.1-Millimeter. Die Höhe wird der `cy` Mitglied der `CSize` -Objekt, und die Breite hat die `cx` Member. Wenn die Bitmap-Breite und Höhe mit nicht festgelegt wurden `SetBitmapDimension`, wird 0 zurückgegeben.

### <a name="remarks"></a>Hinweise

Die Höhe und Breite werden als zuvor festgelegt wurden mithilfe der [SetBitmapDimension](#setbitmapdimension) Member-Funktion.

##  <a name="loadbitmap"></a>  LoadBitmap

Lädt die Bitmapressource, die mit dem Namen von *LpszResourceName* oder durch die ID-Nummer identifiziert *nIDResource* aus ausführbaren Datei der Anwendung.

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>Parameter

*lpszResourceName*<br/>
Verweist auf eine auf Null endende Zeichenfolge, die den Namen der Bitmapressource enthält.

*nIDResource*<br/>
Gibt die Ressourcen-ID-Nummer der Bitmapressource an.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Die Bitmap geladene angefügt ist die `CBitmap` Objekt.

Wenn die Bitmap identifizierte *LpszResourceName* ist nicht vorhanden oder ist nicht genügend Arbeitsspeicher zum Laden der Bitmaps, die Funktion gibt 0 zurück.

Können Sie die [CGdiObject::DeleteObject](../../mfc/reference/cgdiobject-class.md#deleteobject) von Funktion, um das Löschen der Bitmap geladen werden die `LoadBitmap` -Funktion oder die `CBitmap` Destruktor wird das Objekt für Sie zu löschen.

> [!CAUTION]
>  Bevor Sie das Objekt löschen, stellen Sie sicher, dass es einen Gerätekontext nicht aktiviert ist.

Die folgenden Bitmaps wurden Windows-Versionen 3.1 und höher hinzugefügt:

OBM_UPARRROWIOBM_DNARROWIOBM_RGARROWIOBM_LFARROWI

Diese Bitmaps werden in der Gerätetreiber für Windows-Versionen 3.0 und früheren Versionen nicht gefunden. Eine vollständige Liste von Bitmaps sowie eine Ansicht mit ihrer Darstellung anzuzeigen finden Sie im Windows-SDK.

##  <a name="loadmappedbitmap"></a>  CBitmap::LoadMappedBitmap

Rufen Sie diese Memberfunktion zum Laden einer Bitmaps aus, und ordnen Sie die Farben in der aktuellen Systemfarben an.

```
BOOL LoadMappedBitmap(
    UINT nIDBitmap,
    UINT nFlags = 0,
    LPCOLORMAP lpColorMap = NULL,
    int nMapSize = 0);
```

### <a name="parameters"></a>Parameter

*nIDBitmap*<br/>
Die ID der Bitmapressource.

*nFlags*<br/>
Ein Flag für eine Bitmap. 0 (null) oder CMB_MASKED kann sein.

*lpColorMap*<br/>
Ein Zeiger auf eine `COLORMAP` Struktur, die die Farbe erforderlichen Informationen zum Zuordnen von Bitmaps enthält. Wenn dieser Parameter NULL ist, verwendet die Funktion der standardfarbzuordnung.

*nMapSize*<br/>
Die Anzahl der farbkarten verweist *LpColorMap*.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

In der Standardeinstellung `LoadMappedBitmap` werden häufig in der Schaltfläche Symbole verwendete Farben zugeordnet.

Informationen zum Erstellen einer Bitmap zugeordneten, finden Sie unter der Windows-Funktion [CreateMappedBitmap](http://go.microsoft.com/fwlink/p/?linkid=230562) und [COLORMAP](/windows/desktop/api/commctrl/ns-commctrl-_colormap) Struktur im Windows SDK.

##  <a name="loadoembitmap"></a>  CBitmap::LoadOEMBitmap

Lädt eine vordefinierte Bitmap, die von Windows verwendet.

```
BOOL LoadOEMBitmap(UINT nIDBitmap);
```

### <a name="parameters"></a>Parameter

*nIDBitmap*<br/>
ID-Nummer der vordefinierten Windows-Bitmap. Die möglichen Werte sind unten aufgeführt, unter WINDOWS. H:

|||
|-|-|
|OBM_BTNCORNERS|OBM_OLD_RESTORE|
|OBM_BTSIZE|OBM_OLD_RGARROW|
|OBM_CHECK|OBM_OLD_UPARROW|
|OBM_CHECKBOXES|OBM_OLD_ZOOM|
|OBM_CLOSE|OBM_REDUCE|
|OBM_COMBO|OBM_REDUCED|
|OBM_DNARROW|OBM_RESTORE|
|OBM_DNARROWD|OBM_RESTORED|
|OBM_DNARROWI|OBM_RGARROW|
|OBM_LFARROW|OBM_RGARROWD|
|OBM_LFARROWD|OBM_RGARROWI|
|OBM_LFARROWI|OBM_SIZE|
|OBM_MNARROW|OBM_UPARROW|
|OBM_OLD_CLOSE|OBM_UPARROWD|
|OBM_OLD_DNARROW|OBM_UPARROW|
|OBM_OLD_LFARROW|OBM_ZOOM|
|OBM_OLD_REDUCE|OBM_ZOOMD|

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Bitmap-Namen, die mit OBM_OLD beginnen darstellen, Bitmaps, die von Windows-Versionen vor 3.0 verwendet wird.

Beachten Sie, dass die Konstante OEMRESOURCE einschließlich WINDOWS definiert werden muss. H, um Sie verwenden die **OBM_** Konstanten.

##  <a name="operator_hbitmap"></a>  CBitmap::operator HBITMAP

Verwenden Sie diesen Operator, um das angefügte Windows-GDI-Handle des erhalten die `CBitmap` Objekt.

```
operator HBITMAP() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CBitmap` Objekt; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Dieser Operator ist ein Umwandlungsoperator, die direkte Verwendung von unterstützt eine `HBITMAP` Objekt.

Weitere Informationen zur Verwendung von Grafikobjekten finden Sie unter [Grafik Objekte](/windows/desktop/gdi/graphic-objects) im Windows SDK.

##  <a name="setbitmapbits"></a>  CBitmap::SetBitmapBits

Legt die Bits einer Bitmap auf den Bit-Werte, die vom *LpBits*.

```
DWORD SetBitmapBits(
    DWORD dwCount,
    const void* lpBits);
```

### <a name="parameters"></a>Parameter

*dwCount*<br/>
Gibt die Anzahl der Bytes, die auf den von *LpBits*.

*lpBits*<br/>
Verweist auf das Bytearray mit den Pixelwerten zum Kopieren der `CBitmap` Objekt. In der Reihenfolge für die Bitmap, damit das Image ordnungsgemäß gerendert werden kann sollten die Werte formatiert werden, um die Werte der Tiefe Höhe, Breite und Farbe zu entsprechen, die angegeben wurden, wenn die CBitmap-Instanz erstellt wurde. Weitere Informationen finden Sie unter [CBitmap::CreateBitmap](#createbitmap).

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Bytes, die bei der Festlegung der Bitmap-Bits verwendet werden soll; 0, wenn die Funktion fehlerhaft ist.

##  <a name="setbitmapdimension"></a>  CBitmap::SetBitmapDimension

Weist eine Breite und Höhe einer Bitmap in Einheiten von 0.1-Millimeter.

```
CSize SetBitmapDimension(
    int nWidth,
    int nHeight);
```

### <a name="parameters"></a>Parameter

*nWidth*<br/>
Gibt die Breite der Bitmap (in Einheiten von 0.1-Millimeter).

*nHeight*<br/>
Gibt die Höhe der Bitmap (in Einheiten von 0.1-Millimeter).

### <a name="return-value"></a>Rückgabewert

Die vorherige Bitmapdimensionen. Höhe befindet sich in der `cy` Membervariable der der `CSize` Objekt und Breite befindet sich in der `cx` Membervariablen gespeichert.

### <a name="remarks"></a>Hinweise

Die GDI verwendet diese Werte mit Ausnahme der zum zurücksenden, wenn eine Anwendung ruft keine der [GetBitmapDimension](#getbitmapdimension) Member-Funktion.

## <a name="see-also"></a>Siehe auch

[MDI MFC-Beispiel](../../overview/visual-cpp-samples.md)<br/>
[CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)
