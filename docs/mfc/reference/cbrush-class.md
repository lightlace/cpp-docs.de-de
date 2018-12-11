---
title: CBrush-Klasse
ms.date: 11/04/2016
f1_keywords:
- CBrush
- AFXWIN/CBrush
- AFXWIN/CBrush::CBrush
- AFXWIN/CBrush::CreateBrushIndirect
- AFXWIN/CBrush::CreateDIBPatternBrush
- AFXWIN/CBrush::CreateHatchBrush
- AFXWIN/CBrush::CreatePatternBrush
- AFXWIN/CBrush::CreateSolidBrush
- AFXWIN/CBrush::CreateSysColorBrush
- AFXWIN/CBrush::FromHandle
- AFXWIN/CBrush::GetLogBrush
helpviewer_keywords:
- CBrush [MFC], CBrush
- CBrush [MFC], CreateBrushIndirect
- CBrush [MFC], CreateDIBPatternBrush
- CBrush [MFC], CreateHatchBrush
- CBrush [MFC], CreatePatternBrush
- CBrush [MFC], CreateSolidBrush
- CBrush [MFC], CreateSysColorBrush
- CBrush [MFC], FromHandle
- CBrush [MFC], GetLogBrush
ms.assetid: e5ef2c62-dd95-4973-9090-f52f605900e1
ms.openlocfilehash: dbc5e36fdf613f1db2818ac6193709829e3bd001
ms.sourcegitcommit: 975098222db3e8b297607cecaa1f504570a11799
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53178706"
---
# <a name="cbrush-class"></a>CBrush-Klasse

Kapselt einen Pinsel der Windows GDI (Graphics Device Interface).

## <a name="syntax"></a>Syntax

```
class CBrush : public CGdiObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CBrush::CBrush](#cbrush)|Erstellt ein `CBrush`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CBrush::CreateBrushIndirect](#createbrushindirect)|Initialisiert einen Pinsel, mit der Formatvorlage, die Farbe und im angegebenen Muster eine [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) Struktur.|
|[CBrush::CreateDIBPatternBrush](#createdibpatternbrush)|Initialisiert einen Pinsel mit einem Muster, die durch eine geräteunabhängige Bitmap (DIB) angegeben.|
|[CBrush::CreateHatchBrush](#createhatchbrush)|Initialisiert einen Pinsel, mit der angegebenen Schraffurmuster und Farbe.|
|[CBrush::CreatePatternBrush](#createpatternbrush)|Initialisiert einen Pinsel mit einem Muster, die durch eine Bitmap angegeben.|
|[CBrush::CreateSolidBrush](#createsolidbrush)|Initialisiert einen Pinsel, mit der angegebenen Volltonfarbe entspricht.|
|[CBrush::CreateSysColorBrush](#createsyscolorbrush)|Erstellt einen Pinsel, der die Standardsystemfarbe ist.|
|[CBrush::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CBrush` Objekt, wenn ein Handle auf ein Windows gewährt `HBRUSH` Objekt.|
|[CBrush::GetLogBrush](#getlogbrush)|Ruft eine [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) Struktur.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CBrush::operator HBRUSH](#operator_hbrush)|Gibt zurück, das Windows-Handle, das angefügt wird, um die `CBrush` Objekt.|

## <a name="remarks"></a>Hinweise

Verwenden einer `CBrush` Objekt, das Erstellen einer `CBrush` -Objekt und übergeben Sie es auf eine `CDC` Memberfunktion, die einen Pinsel erfordert.

Pinsel können durchgezogen, ausgebrütet oder Muster sein.

Weitere Informationen zu `CBrush`, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CBrush`

## <a name="requirements"></a>Anforderungen

**Header:** afxwin.h

##  <a name="cbrush"></a>  CBrush::CBrush

Erstellt ein `CBrush`-Objekt.

```
CBrush();
CBrush(COLORREF crColor);
CBrush(int nIndex, COLORREF crColor);
explicit CBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Parameter

*crColor*<br/>
Gibt die Vordergrundfarbe des Pinsels als eine RGB-Farbe. Wenn der Pinsel ausgebrütet ist, gibt dieser Parameter die Farbe der Schraffur an.

*nIndex*<br/>
Gibt die Schraffurart des Pinsels. Eine der folgenden Werte sind möglich:

- HS_BDIAGONAL Schraffierung nach unten (von links nach rechts) auf 45 Grad

- HS_CROSS horizontale und vertikale Schraffur

- HS_DIAGCROSS Kreuzschraffur auf 45 Grad

- HS_FDIAGONAL nach oben Schraffur (von links nach rechts) auf 45 Grad

- Horizontale HS_HORIZONTAL Schraffur

- Vertikale HS_VERTICAL Schraffur

*pBitmap*<br/>
Verweist auf eine `CBitmap` -Objekt, das einer Bitmap gibt an, mit denen der Pinsel zeichnet.

### <a name="remarks"></a>Hinweise

`CBrush` verfügt über vier Konstruktoren überladen. Der Konstruktor ohne Argumente erstellt ein nicht initialisiertes `CBrush` -Objekt, das initialisiert werden muss, bevor sie verwendet werden kann.

Wenn Sie den Konstruktor ohne Argumente verwenden, müssen Sie die resultierende initialisieren `CBrush` Objekt mit [CreateSolidBrush](#createsolidbrush), [CreateHatchBrush](#createhatchbrush), [CreateBrushIndirect](#createbrushindirect), [CreatePatternBrush](#createpatternbrush), oder [CreateDIBPatternBrush](#createdibpatternbrush). Bei Verwendung eines Konstruktors, die Argumente akzeptiert, ist keine weitere Initialisierung erforderlich. Die Konstruktoren mit Argumenten können eine Ausnahme auslösen, wenn Fehler auftreten, während der Konstruktor ohne Argumente immer erfolgreich ist, wird.

Der Konstruktor mit einem einzelnen [COLORREF](/windows/desktop/gdi/colorref) Parameter erstellt einen einfarbigen Pinsel, mit der angegebenen Farbe. Die Farbe Gibt einen RGB-Wert und kann mit dem RGB-Makro in WINDOWS erstellt werden. H.

Der Konstruktor mit zwei Parametern konstruiert ein Schraffurpinsel. Die *nIndex* Parameter gibt den Index einer Schraffurmuster. Die *CrColor* Parameter gibt die Farbe an.

Der Konstruktor mit einem `CBitmap` -Parameter erstellt einen Pinsel. Der Parameter bezeichnet eine Bitmap. Wird angenommen, dass die Bitmap erstellt wurden, indem Sie mithilfe von [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap:: Createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), oder [ CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap). Die minimale Größe für eine Bitmap, die in einem Muster für die Füllung verwendet werden, ist 8 x 8 Pixel.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#21](../../mfc/codesnippet/cpp/cbrush-class_1.cpp)]

##  <a name="createbrushindirect"></a>  CBrush::CreateBrushIndirect

Initialisiert einen Pinsel, mit einem Stil, Farbe und im angegebenen Muster eine [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) Struktur.

```
BOOL CreateBrushIndirect(const LOGBRUSH* lpLogBrush);
```

### <a name="parameters"></a>Parameter

*lpLogBrush*<br/>
Verweist auf eine [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) -Struktur, die Informationen zu den Pinsel enthält.

### <a name="return-value"></a>Rückgabewert

Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).

### <a name="remarks"></a>Hinweise

Der Pinsel kann anschließend als den aktuellen Pinsel für einen beliebigen Gerätekontext ausgewählt werden.

Ein Pinsel, der mithilfe einer Bitmap Monochrom (1-Ebene, 1 Bit pro Pixel) erstellt wird unter Verwendung der aktuellen Farben für Text und Hintergrund gezeichnet. Pixel, dargestellt durch ein Bit auf 0 festgelegt, werden in der aktuellen Text gezeichnet werden. Pixel, dargestellt durch ein Bit auf 1 festgelegt, werden mit der aktuellen Hintergrundfarbe gezeichnet werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#22](../../mfc/codesnippet/cpp/cbrush-class_2.cpp)]

##  <a name="createdibpatternbrush"></a>  CBrush::CreateDIBPatternBrush

Initialisiert einen Pinsel mit dem Muster, die durch eine geräteunabhängige Bitmap (DIB) angegeben.

```
BOOL CreateDIBPatternBrush(
    HGLOBAL hPackedDIB,
    UINT nUsage);

BOOL CreateDIBPatternBrush(
    const void* lpPackedDIB,
    UINT nUsage);
```

### <a name="parameters"></a>Parameter

*hPackedDIB*<br/>
Identifiziert einen globalen Arbeitsspeicher-Objekt, die eine gepackte geräteunabhängige Bitmap (DIB) enthält.

*Nsyntax*<br/>
Gibt an, ob die `bmiColors[]` Felder der [BITMAPINFO](/windows/desktop/api/wingdi/ns-wingdi-tagbitmapinfo) Datenstruktur (ein Teil von "gepackt das DIB") enthalten die explizite RGB-Werte oder Indizes in der derzeit realisierten logische Palette. Der Parameter muss einen der folgenden Werte sein:

- DIB_PAL_COLORS die Farbtabelle besteht aus einem Array von 16-Bit-Indizes.

- DIB_RGB_COLORS die Farbtabelle enthält Literale RGB-Werte.

*lpPackedDIB*<br/>
Verweist auf eine gepackte DIB bestehend aus einem `BITMAPINFO` Struktur folgt unmittelbar ein Array von Bytes, die die Pixel der Bitmap definieren.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Der Pinsel kann anschließend für einen beliebigen Gerätekontext ausgewählt werden, die Raster-Vorgänge unterstützt.

Die beiden Versionen unterscheiden sich in der, wie Sie die DIB behandelt:

- In der ersten Version, um ein Handle für das DIB-Datei erhalten Sie die Windows aufrufen `GlobalAlloc` Funktion, um einen globalen Speicherblock zuordnen und geben Sie dann den Arbeitsspeicher mit gepackte DIB-Datei.

- In der zweiten Version, ist es nicht notwendig, `GlobalAlloc` zum Belegen von Arbeitsspeicher für die gepackte DIB-Datei.

Eine gepackte DIB besteht aus einem `BITMAPINFO` Datenstruktur, die unmittelbar nach der das Array von Bytes, die die Pixel der Bitmap definiert. Bitmaps, die als Füllung Muster sollte 8 x 8 Pixel sein. Wenn die Bitmap größer ist, erstellt Windows ein Fill-Muster verwenden nur die Bits, die für die ersten 8 Zeilen und 8 Spalten der Pixel in der oberen linken Ecke der Bitmap.

Wenn eine Anwendung einen zwei-DIB Musterpinsel für einen Kontext monochromen Gerät auswählt, wird Windows ignoriert die Farben in DIB-Datei angegeben, sondern zeigt stattdessen die Musterpinsel, mit der aktuellen Text- und Hintergrundfarben des Gerätekontexts. Pixel der ersten Farbe (am Offset 0 in der Farbtabelle DIB) der DIB-Datei zugeordnet werden, verwenden die Textfarbe angezeigt. Pixel, die zweite Farbe (am Offset von 1 in der Farbtabelle) zugeordnet werden, mit der Hintergrundfarbe angezeigt.

Informationen zur Verwendung der folgenden Windows-Funktionen finden Sie im Windows-SDK:

- [CreateDIBPatternBrush](/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrush) (diese Funktion wird nur bereitgestellt, um Kompatibilität mit Anwendungen für Windows-Versionen vor 3.0 geschrieben wurden; verwenden Sie die `CreateDIBPatternBrushPt` Funktion.)

- [CreateDIBPatternBrushPt](/windows/desktop/api/wingdi/nf-wingdi-createdibpatternbrushpt) (diese Funktion sollte für die Win32-basierten Anwendungen verwendet werden.)

- [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc)

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#23](../../mfc/codesnippet/cpp/cbrush-class_3.cpp)]

##  <a name="createhatchbrush"></a>  CBrush::CreateHatchBrush

Initialisiert einen Pinsel, mit der angegebenen Schraffurmuster und Farbe.

```
BOOL CreateHatchBrush(
    int nIndex,
    COLORREF crColor);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt die Schraffurart des Pinsels. Eine der folgenden Werte sind möglich:

- HS_BDIAGONAL Schraffierung nach unten (von links nach rechts) auf 45 Grad

- HS_CROSS horizontale und vertikale Schraffur

- HS_DIAGCROSS Kreuzschraffur auf 45 Grad

- HS_FDIAGONAL nach oben Schraffur (von links nach rechts) auf 45 Grad

- Horizontale HS_HORIZONTAL Schraffur

- Vertikale HS_VERTICAL Schraffur

*crColor*<br/>
Gibt die Vordergrundfarbe des Pinsels als eine RGB-Farbe (die Farbe der Schraffuren) an. Finden Sie unter [COLORREF](/windows/desktop/gdi/colorref) im Windows SDK für Weitere Informationen.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Der Pinsel kann anschließend als den aktuellen Pinsel für einen beliebigen Gerätekontext ausgewählt werden.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#24](../../mfc/codesnippet/cpp/cbrush-class_4.cpp)]

##  <a name="createpatternbrush"></a>  CBrush::CreatePatternBrush

Initialisiert einen Pinsel mit einem Muster, die durch eine Bitmap angegeben.

```
BOOL CreatePatternBrush(CBitmap* pBitmap);
```

### <a name="parameters"></a>Parameter

*pBitmap*<br/>
Eine Bitmap bezeichnet.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Der Pinsel kann anschließend für einen beliebigen Gerätekontext ausgewählt werden, die Raster-Vorgänge unterstützt. Die Bitmap identifizierte *pBitmap* wird in der Regel mit initialisiert die [CBitmap::CreateBitmap](../../mfc/reference/cbitmap-class.md#createbitmap), [CBitmap:: Createbitmapindirect](../../mfc/reference/cbitmap-class.md#createbitmapindirect), [CBitmap:: LoadBitmap](../../mfc/reference/cbitmap-class.md#loadbitmap), oder [CBitmap::CreateCompatibleBitmap](../../mfc/reference/cbitmap-class.md#createcompatiblebitmap) Funktion.

Bitmaps, die als Füllung Muster sollte 8 x 8 Pixel sein. Wenn die Bitmap größer ist, verwendet Windows nur die Bits für die ersten 8 Zeilen und Spalten der Pixel in der oberen linken Ecke der Bitmap.

Ein Musterpinsel kann gelöscht werden, ohne Auswirkungen auf die zugeordnete Bitmap. Dies bedeutet, dass die Bitmap verwendet werden kann, um eine beliebige Anzahl von Musterpinsel zu erstellen.

Ein Pinsel, mit der eine monochrome Bitmap (Ebene 1 Farbe, 1 Bit pro Pixel) erstellt wird unter Verwendung der aktuellen Farben für Text und Hintergrund gezeichnet. Pixel, dargestellt durch ein Bit auf 0 festgelegt, werden mit der aktuellen Farbe des Texts gezeichnet. Pixel, dargestellt durch ein Bit auf 1 festgelegt, werden mit der aktuellen Hintergrundfarbe gezeichnet.

Informationen zur Verwendung [CreatePatternBrush](/windows/desktop/api/wingdi/nf-wingdi-createpatternbrush), ein Windows funktionieren, finden Sie im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#25](../../mfc/codesnippet/cpp/cbrush-class_5.cpp)]

##  <a name="createsolidbrush"></a>  CBrush::CreateSolidBrush

Initialisiert einen Pinsel mit Volltonfarbe angegebenen.

```
BOOL CreateSolidBrush(COLORREF crColor);
```

### <a name="parameters"></a>Parameter

*crColor*<br/>
Ein [COLORREF](/windows/desktop/gdi/colorref) Struktur, die die Farbe des Pinsels angibt. Die Farbe Gibt einen RGB-Wert und kann mit dem RGB-Makro in WINDOWS erstellt werden. H.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Der Pinsel kann anschließend als den aktuellen Pinsel für einen beliebigen Gerätekontext ausgewählt werden.

Wenn eine Anwendung wurde mit dem Pinsel erstellt `CreateSolidBrush`, sollten sie den Pinsel im Gerätekontext auswählen.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CBrush::CBrush](#cbrush).

##  <a name="createsyscolorbrush"></a>  CBrush::CreateSysColorBrush

Initialisiert eine Pinselfarbe.

```
BOOL CreateSysColorBrush(int nIndex);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Gibt einen Farbenindex an. Dieser Wert entspricht der Farbe verwendet, um eines der Fensterelemente 21 gezeichnet werden soll. Finden Sie unter [GetSysColor](/windows/desktop/api/winuser/nf-winuser-getsyscolor) im Windows SDK für eine Liste von Werten.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Der Pinsel kann anschließend als den aktuellen Pinsel für einen beliebigen Gerätekontext ausgewählt werden.

Wenn eine Anwendung wurde mit dem Pinsel erstellt `CreateSysColorBrush`, sollten sie den Pinsel im Gerätekontext auswählen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#26](../../mfc/codesnippet/cpp/cbrush-class_6.cpp)]

##  <a name="fromhandle"></a>  CBrush::FromHandle

Gibt einen Zeiger auf eine `CBrush` Objekt, wenn ein Handle auf ein Windows gewährt [HBRUSH](#operator_hbrush) Objekt.

```
static CBrush* PASCAL FromHandle(HBRUSH hBrush);
```

### <a name="parameters"></a>Parameter

*hBrush*<br/>
HANDLE für einen Windows-GDI-Pinsel.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine `CBrush` -Objekt, wenn erfolgreich; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn eine `CBrush` Objekt ist noch nicht auf das Handle, eine temporäre angefügt `CBrush` Objekt erstellt und angefügt. Diese temporären `CBrush` Objekt nur bis zur nächsten Ausführung, die die Anwendung hat die Zeit im Leerlauf in seiner Ereignisschleife gültig ist. Zu diesem Zeitpunkt werden alle temporären grafische Objekte gelöscht. Das heißt, ist das temporäre Objekt nur während der Verarbeitung der Nachricht für ein Fenster gültig.

Weitere Informationen zur Verwendung von Grafikobjekten finden Sie unter [Grafik Objekte](/windows/desktop/gdi/graphic-objects) im Windows SDK.

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [CBrush::CBrush](#cbrush).

##  <a name="getlogbrush"></a>  CBrush::GetLogBrush

Rufen Sie diese Memberfunktion zum Abrufen der `LOGBRUSH` Struktur.

```
int GetLogBrush(LOGBRUSH* pLogBrush);
```

### <a name="parameters"></a>Parameter

*pLogBrush*<br/>
Verweist auf eine [LOGBRUSH](/windows/desktop/api/wingdi/ns-wingdi-taglogbrush) -Struktur, die Informationen zu den Pinsel enthält.

### <a name="return-value"></a>Rückgabewert

Wenn die Funktion erfolgreich ist, und *pLogBrush* gültiger Zeiger ist, ist der Rückgabewert ist die Anzahl der Bytes im Puffer gespeichert.

Wenn die Funktion erfolgreich ist, und *pLogBrush* NULL ist, der Rückgabewert ist die Anzahl von Bytes erforderlich, um die Informationen über die Funktion aufzunehmen speichern in den Puffer.

Wenn die Funktion fehlschlägt, ist der Rückgabewert 0.

### <a name="remarks"></a>Hinweise

Die `LOGBRUSH` Struktur definiert, der Stil, Farbe und Muster eines Pinsels.

Rufen Sie z. B. `GetLogBrush` mit dem bestimmten Farbe oder ein Muster einer Bitmap übereinstimmen.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#27](../../mfc/codesnippet/cpp/cbrush-class_7.cpp)]

##  <a name="operator_hbrush"></a>  CBrush::operator HBRUSH

Verwenden Sie diesen Operator, um das angefügte Windows-GDI-Handle des erhalten die `CBrush` Objekt.

```
operator HBRUSH() const;
```

### <a name="return-value"></a>Rückgabewert

Wenn erfolgreich, ein Handle für das Windows-GDI-Objekt durch dargestellt die `CBrush` Objekt; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Dieser Operator ist ein Umwandlungsoperator, die direkte Verwendung eines Objekts HBRUSH unterstützt.

Weitere Informationen zur Verwendung von Grafikobjekten finden Sie unter [Grafik Objekte](/windows/desktop/gdi/graphic-objects) im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDocView#28](../../mfc/codesnippet/cpp/cbrush-class_8.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-Beispiel PROPDLG](../../visual-cpp-samples.md)<br/>
[CGdiObject-Klasse](../../mfc/reference/cgdiobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CBitmap-Klasse](../../mfc/reference/cbitmap-class.md)<br/>
[CDC-Klasse](../../mfc/reference/cdc-class.md)
