---
title: CDrawingManager-Klasse
ms.date: 11/04/2016
f1_keywords:
- CDrawingManager
- AFXDRAWMANAGER/CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CDrawingManager
- AFXDRAWMANAGER/CDrawingManager::CreateBitmap_32
- AFXDRAWMANAGER/CDrawingManager::DrawAlpha
- AFXDRAWMANAGER/CDrawingManager::DrawRotated
- AFXDRAWMANAGER/CDrawingManager::DrawEllipse
- AFXDRAWMANAGER/CDrawingManager::DrawGradientRing
- AFXDRAWMANAGER/CDrawingManager::DrawRect
- AFXDRAWMANAGER/CDrawingManager::DrawShadow
- AFXDRAWMANAGER/CDrawingManager::Fill4ColorsGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient
- AFXDRAWMANAGER/CDrawingManager::FillGradient2
- AFXDRAWMANAGER/CDrawingManager::GrayRect
- AFXDRAWMANAGER/CDrawingManager::HighlightRect
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_ONE
- AFXDRAWMANAGER/CDrawingManager::HLStoRGB_TWO
- AFXDRAWMANAGER/CDrawingManager::HSVtoRGB
- AFXDRAWMANAGER/CDrawingManager::HuetoRGB
- AFXDRAWMANAGER/CDrawingManager::MirrorRect
- AFXDRAWMANAGER/CDrawingManager::PixelAlpha
- AFXDRAWMANAGER/CDrawingManager::PrepareShadowMask
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSL
- AFXDRAWMANAGER/CDrawingManager::RGBtoHSV
- AFXDRAWMANAGER/CDrawingManager::SetAlphaPixel
- AFXDRAWMANAGER/CDrawingManager::SetPixel
- AFXDRAWMANAGER/CDrawingManager::SmartMixColors
helpviewer_keywords:
- CDrawingManager [MFC], CDrawingManager
- CDrawingManager [MFC], CreateBitmap_32
- CDrawingManager [MFC], DrawAlpha
- CDrawingManager [MFC], DrawRotated
- CDrawingManager [MFC], DrawEllipse
- CDrawingManager [MFC], DrawGradientRing
- CDrawingManager [MFC], DrawRect
- CDrawingManager [MFC], DrawShadow
- CDrawingManager [MFC], Fill4ColorsGradient
- CDrawingManager [MFC], FillGradient
- CDrawingManager [MFC], FillGradient2
- CDrawingManager [MFC], GrayRect
- CDrawingManager [MFC], HighlightRect
- CDrawingManager [MFC], HLStoRGB_ONE
- CDrawingManager [MFC], HLStoRGB_TWO
- CDrawingManager [MFC], HSVtoRGB
- CDrawingManager [MFC], HuetoRGB
- CDrawingManager [MFC], MirrorRect
- CDrawingManager [MFC], PixelAlpha
- CDrawingManager [MFC], PrepareShadowMask
- CDrawingManager [MFC], RGBtoHSL
- CDrawingManager [MFC], RGBtoHSV
- CDrawingManager [MFC], SetAlphaPixel
- CDrawingManager [MFC], SetPixel
- CDrawingManager [MFC], SmartMixColors
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
ms.openlocfilehash: 506ab7a06653942ecff05043a7e7efabd535115f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781691"
---
# <a name="cdrawingmanager-class"></a>CDrawingManager-Klasse

Die `CDrawingManager` -Klasse implementiert komplexe zeichnen Algorithmen.

## <a name="syntax"></a>Syntax

```
class CDrawingManager : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|Erstellt ein `CDrawingManager`-Objekt.|
|`CDrawingManager::~CDrawingManager`|Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|Erstellt eine 32-Bit-geräteunabhängige Bitmap (DIB), der Anwendungen direkt in schreiben können.|
|[CDrawingManager::DrawAlpha](#drawalpha)|Zeigt die Bitmaps, die transparent oder halbtransparent Pixel aufweisen.|
|[CDrawingManager::DrawRotated](#drawrotated)|Ein Quell-DC-Inhalt in einem angegebenen Rechteck von +/-um 90 Grad rotiert|
|[CDrawingManager::DrawEllipse](#drawellipse)|Zeichnet eine Ellipse mit der angegebenen Füllung und die Rahmenfarben.|
|[CDrawingManager::DrawGradientRing](#drawgradientring)|Zeichnet einen Ring aus, und füllt es mit einem Farbverlauf.|
|[CDrawingManager::DrawLine, CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|Zeichnet eine Linie.|
|[CDrawingManager::DrawRect](#drawrect)|Zeichnet ein Rechteck mit den angegebenen Farben für Füllung und Rahmen.|
|[CDrawingManager::DrawShadow](#drawshadow)|Zeichnet einen Schatten für einen rechteckigen Bereich an.|
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|Füllt einen rechteckigen Bereich mit zwei Farbverläufen.|
|[CDrawingManager::FillGradient](#fillgradient)|Füllt einen rechteckigen Bereich mit einem angegebenen Farbverlauf an.|
|[CDrawingManager::FillGradient2](#fillgradient2)|Füllt einen rechteckigen Bereich mit einem angegebenen Farbverlauf an. Die Richtung des Ändern der Farbe des Farbverlaufsstopps wird ebenfalls angegeben.|
|[CDrawingManager::GrayRect](#grayrect)|Füllt ein Rechteck mit einer angegebenen graue Farbe an.|
|[CDrawingManager::HighlightRect](#highlightrect)|Hebt einen rechteckigen Bereich an.|
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|Konvertiert eine Farbe aus einer Darstellung HLS in eine RGB-Darstellung.|
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|Konvertiert eine Farbe aus einer Darstellung HLS in eine RGB-Darstellung.|
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|Konvertiert eine Farbe aus einer Darstellung HSV in eine RGB-Darstellung.|
|[CDrawingManager::HuetoRGB](#huetorgb)|Hilfsmethode, die eine Farbtonwert in einer roten, grünen oder blauen Komponente konvertiert werden.|
|[CDrawingManager::MirrorRect](#mirrorrect)|Kippt ein rechteckiges Bereichs.|
|[CDrawingManager::PixelAlpha](#pixelalpha)|Hilfsmethode, die die endgültige Farbe für ein halbtransparenten Pixel bestimmt.|
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|Erstellt eine Bitmap, die als einen Schatten verwendet werden kann.|
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|Konvertiert eine Farbe aus einer RGB-Darstellung in eine HSL-Darstellung.|
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|Konvertiert eine Farbe aus einer RGB-Darstellung mit Ihrer Darstellung in einem HSV an.|
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|Hilfsmethode, die Farben ein teilweise transparentes Pixels in einer Bitmap.|
|[CDrawingManager::SetPixel](#setpixel)|Hilfsmethode, die ein einzelnes Pixel in einer Bitmap in der angegebenen Farbe ändert.|
|[CDrawingManager::SmartMixColors](#smartmixcolors)|Kombiniert zwei Farben basierend auf einer gewichteten Verhältnis.|

## <a name="remarks"></a>Hinweise

Die `CDrawingManager` Klasse stellt Funktionen zum Zeichnen von Schatten, Farbverläufen und hervorgehobene Rechtecke bereit. Er führt auch eine Alpha-Blending überlagern. Sie können diese Klasse verwenden, um Benutzeroberfläches Ihrer Anwendung direkt zu ändern.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)<br/>
`CDrawingManager`

## <a name="requirements"></a>Anforderungen

**Header:** afxdrawmanager.h

##  <a name="cdrawingmanager"></a>  CDrawingManager::CDrawingManager

Erstellt eine [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) Objekt.

```
CDrawingManager(CDC& dc);
```

### <a name="parameters"></a>Parameter

*dc*<br/>
[in] Ein Verweis auf einen Gerätekontext. Die `CDrawingManager` dieser Kontext zum Zeichnen verwendet.

##  <a name="createbitmap_32"></a>  CDrawingManager::CreateBitmap_32

Erstellt eine 32-Bit-geräteunabhängige Bitmap (DIB), der Anwendungen direkt in schreiben können.

```
static HBITMAP __stdcall CreateBitmap_32(
    const CSize& size,
    void** pBits);

static HBITMAP __stdcall CreateBitmap_32(
    HBITMAP bitmap,
    COLORREF clrTransparent = -1);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*size*|[in] Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Parameter, der die Größe der Bitmap angibt.|
|*pBits*|[out] Ein Zeiger auf einen Datenzeiger, der den Speicherort des DIB empfängt bit-Werten.|
|*bitmap*|Ein Handle für die ursprüngliche bitmap|
|*clrTransparent*|Ein RGB-Wert, transparente Farbe des der ursprünglichen Bitmap angibt.|

### <a name="return-value"></a>Rückgabewert

Ein Handle auf die neu erstellte DIB Bitmap aus, wenn diese Methode erfolgreich ist; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Weitere Informationen dazu, wie Sie eine DIB-Bitmap zu erstellen, finden Sie unter [CreateDIBSection](/windows/desktop/api/wingdi/nf-wingdi-createdibitmap).

##  <a name="drawalpha"></a>  CDrawingManager::DrawAlpha

Zeigt die Bitmaps, die transparent oder halbtransparent Pixel aufweisen.

```
void DrawAlpha(
    CDC* pDstDC,
    const CRect& rectDst,
    CDC* pSrcDC,
    const CRect& rectSrc);
```

### <a name="parameters"></a>Parameter

*pDstDC*<br/>
[in] Ein Zeiger auf den Gerätekontext für das Ziel.

*rectDst*<br/>
[in] Das Zielrechteck.

*pSrcDC*<br/>
[in] Ein Zeiger auf den Gerätekontext für die Quelle.

*rectSrc*<br/>
[in] Das Quellrechteck.

### <a name="remarks"></a>Hinweise

Diese Methode führt Alpha-blending für zwei Bitmaps auf. Weitere Informationen zu den Alpha-Blending überlagern, finden Sie unter [AlphaBlend](/windows/desktop/api/wingdi/nf-wingdi-alphablend) im Windows SDK.

##  <a name="drawellipse"></a>  CDrawingManager::DrawEllipse

Zeichnet eine Ellipse mit der angegebenen Füllung und die Rahmenfarben.

```
void DrawEllipse(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[in] Das umschließende Rechteck für die Ellipse.

*clrFill*<br/>
[in] Die Farbe, die diese Methode verwendet, um die Ellipse ausgefüllt.

*clrLine*<br/>
[in] Die Farbe verwendet diese Methode als Rahmen der Ellipse.

### <a name="remarks"></a>Hinweise

Diese Methode gibt zurück, ohne eine Ellipse zeichnen, wenn entweder Farbe auf-1 festgelegt ist. Es gibt auch ohne eine Ellipse zeichnen, wenn entweder Dimension des umgebenden Rechtecks 0 zurück.

##  <a name="drawgradientring"></a>  CDrawingManager::DrawGradientRing

Zeichnet einen Ring aus, und füllt es mit einem Farbverlauf.

```
BOOL DrawGradientRing(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    COLORREF colorBorder,
    int nAngle,
    int nWidth,
    COLORREF clrFace = (COLORREF)-1);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[in] Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Parameter, der die Grenze für den Farbverlauf Ring angibt.

*colorStart*<br/>
[in] Die erste Farbe des Farbverlaufs.

*colorFinish*<br/>
[in] Die letzte Farbe des Farbverlaufs.

*colorBorder*<br/>
[in] Die Farbe des Rahmens.

*nAngle*<br/>
[in] Ein Parameter, der angibt, die anfängliche Winkel der Verlaufsfläche zeichnen. Dieser Wert sollte zwischen 0 und 360 liegen.

*nWidth*<br/>
[in] Die Breite des Rahmens für den Ring.

*clrFace*<br/>
[in] Die Farbe der das Innere des Rings.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Die definierten Rechtecks *Rect* müssen mindestens 5 Pixel breit und 5 Pixel hoch sein.

##  <a name="drawline_cdrawingmanager__drawlinea"></a>  CDrawingManager::DrawLine, CDrawingManager::DrawLineA

Zeichnet eine Linie.

```
void DrawLine(
    int x1,
    int y1,
    int x2,
    int y2,
    COLORREF clrLine);

void DrawLineA(
    double x1,
    double y1,
    double x2,
    double y2,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*x1*|[in] Die X-Koordinate, an der Zeile beginnt.|
|*y1*|[in] Die y-Koordinate, an der Zeile beginnt.|
|*x2*|[in] Die X-Koordinate, an dem die Linie endet.|
|*y2*|[in] Die y-Koordinate, an dem die Linie endet.|
|*clrLine*|[in] Die Farbe der Linie.|

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl, wenn *ClrLine* gleich -1.

##  <a name="drawrect"></a>  CDrawingManager::DrawRect

Zeichnet ein Rechteck mit den angegebenen Farben für Füllung und Rahmen.

```
void DrawRect(
    const CRect& rect,
    COLORREF clrFill,
    COLORREF clrLine);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[in] Die Grenzen für das Rechteck.

*clrFill*<br/>
[in] Die Farbe, die diese Methode, die zum Ausfüllen des Rechtecks verwendet wird.

*clrLine*<br/>
[in] Die Farbe, die diese Methode für den Rand des Rechtecks verwendet wird.

### <a name="remarks"></a>Hinweise

Diese Methode gibt zurück, ohne ein Rechteck zeichnen, wenn entweder Farbe auf-1 festgelegt ist. Gibt zurück, auch wenn beide Dimension des Rechtecks 0.

##  <a name="drawshadow"></a>  CDrawingManager::DrawShadow

Zeichnet einen Schatten für einen rechteckigen Bereich an.

```
BOOL DrawShadow(
    CRect rect,
    int nDepth,
    int iMinBrightness = 100,
    int iMaxBrightness = 50,
    CBitmap* pBmpSaveBottom = NULL,
    CBitmap* pBmpSaveRight = NULL,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bRightShadow = TRUE);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[in] Eine rechteckige Bereich in Ihrer Anwendung. Der Zeichnen-Manager wird eine Schattenkopie unterhalb dieser Bereich gezeichnet.

*nDepth*<br/>
[in] Die Breite und Höhe des Schattens.

*iMinBrightness*<br/>
[in] Die minimale Helligkeit des Schattens.

*iMaxBrightness*<br/>
[in] Die maximale Helligkeit des Schattens.

*pBmpSaveBottom*<br/>
[in] Ein Zeiger auf eine Bitmap, die das Bild für den unteren Teil des Schattens enthält.

*pBmpSaveRight*<br/>
[in] Ein Zeiger auf eine Bitmap, die das Bild für den Schatten enthält, die auf der rechten Seite des Rechtecks gezeichnet wird.

*clrBase*<br/>
[in] Die Farbe des Schattens.

*bRightShadow*<br/>
[in] Ein boolescher Parameter, der angibt, wie der Schatten gezeichnet wird. Wenn *bRightShadow* ist `TRUE`, `DrawShadow` zeichnet einen Schatten auf der rechten Seite des Rechtecks.

### <a name="return-value"></a>Rückgabewert

Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).

### <a name="remarks"></a>Hinweise

Sie können zwei gültige Bitmaps für den unteren und rechten Shadows bereitstellen, mit den Parametern *pBmpSaveBottom* und *pBmpSaveRight*. Wenn diese [CBitmap](../../mfc/reference/cbitmap-class.md) Objekte verfügen über eine angefügte GDI-Objekt, `DrawShadow` verwendet diese Bitmaps als Schatten. Wenn die `CBitmap` Parameter müssen sich nicht auf eine angefügte GDI-Objekt, `DrawShadow` den Schatten gezeichnet, und fügt die Bitmaps für die Parameter. In Zukunft Aufrufe `DrawShadow`, Sie können angeben, dass diese Bitmaps, um die Zeichnung zu beschleunigen. Weitere Informationen zu den `CBitmap` -Klasse und GDI-Objekte, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).

Wenn dieser Parameter ist `NULL`, `DrawShadow` wird automatisch den Schatten gezeichnet.

Setzen Sie *bRightShadow* auf "false", der Schatten gezeichnet wird, unter und auf der linken Seite des rechteckigen Bereichs.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `DrawShadow` Methode der `CDrawingManager` Klasse. Dieser Codeausschnitt ist Teil der [Prop Blatt Demobeispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]

##  <a name="fill4colorsgradient"></a>  CDrawingManager::Fill4ColorsGradient

Füllt einen rechteckigen Bereich mit zwei Farbverläufen.

```
void Fill4ColorsGradient(
    CRect rect,
    COLORREF colorStart1,
    COLORREF colorFinish1,
    COLORREF colorStart2,
    COLORREF colorFinish2,
    BOOL bHorz = TRUE,
    int nPercentage = 50);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[in] Die zu füllenden Rechtecks.

*colorStart1*<br/>
[in] Die erste Farbe für den ersten Farbverlauf.

*colorFinish1*<br/>
[in] Die endgültige Farbe für den ersten Farbverlauf.

*colorStart2*<br/>
[in] Die erste Farbe für den zweiten Farbverlauf.

*colorFinish2*<br/>
[in] Die endgültige Farbe für den zweiten Farbverlauf.

*bHorz*<br/>
[in] Ein boolescher Parameter, der angibt, ob `Fill4ColorsGradient` Farben ein horizontales oder vertikales Farbverlaufs. TRUE gibt an, ein horizontaler Farbverlauf.

*nPercentage*<br/>
[in] Eine ganze Zahl zwischen 0 und 100. Dieser Wert gibt an, den Prozentsatz des Rechtecks, das mit den ersten Farbverlauf gefüllt wird.

### <a name="remarks"></a>Hinweise

Falls ein Rechteck mit zwei Farbverläufen gefüllt ist, handelt es sich entweder über miteinander befindet oder Weiter, abhängig vom Wert *bHorz*. Jede Farbverlauf wird unabhängig voneinander berechnet, mit der Methode [CDrawingManager::FillGradient](#fillgradient).

Diese Methode generiert ein Assertionsfehler ausgelöst, wenn *nPercentage* ist kleiner als 0 oder mehr als 100.

##  <a name="fillgradient"></a>  CDrawingManager::FillGradient

Füllt einen rechteckigen Bereich mit den angegebenen Farbverlauf an.

```
void FillGradient(
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    BOOL bHorz = TRUE,
    int nStartFlatPercentage = 0,
    int nEndFlatPercentage = 0);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[in] Der rechteckige Bereich, um zu füllen.

*colorStart*<br/>
[in] Die erste Farbe des Farbverlaufs.

*colorFinish*<br/>
[in] Die endgültige Farbe des Farbverlaufs.

*bHorz*<br/>
[in] Ein boolescher Parameter, der angibt, ob `FillGradient` einen horizontalen oder vertikalen Farbverlauf zeichnen soll.

*nStartFlatPercentage*<br/>
[in] Der Prozentsatz des Rechtecks, `FillGradient` füllt mit *ColorStart* vor dem Beginn des Farbverlaufs.

*nEndFlatPercentage*<br/>
[in] Der Prozentsatz des Rechtecks, `FillGradient` füllt mit *ColorFinish* nach Abschluss des Farbverlaufs.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `FillGradient` Methode der `CDrawingManager` Klasse. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]

##  <a name="fillgradient2"></a>  CDrawingManager::FillGradient2

Füllt einen rechteckigen Bereich mit einem angegebenen Farbverlauf an.

```
void FillGradient2 (
    CRect rect,
    COLORREF colorStart,
    COLORREF colorFinish,
    int nAngle = 0);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[in] Der rechteckige Bereich, um zu füllen.

*colorStart*<br/>
[in] Die erste Farbe des Farbverlaufs entspricht.

*colorFinish*<br/>
[in] Die letzte Farbe des Farbverlaufs entspricht.

*nAngle*<br/>
[in] Eine ganze Zahl zwischen 0 und 360. Dieser Parameter gibt die Richtung des Farbverlaufs.

### <a name="remarks"></a>Hinweise

Verwendung *nAngle* die Richtung des Farbverlaufs an. Wenn Sie die Richtung des Farbverlaufs angeben, geben Sie auch der Farbverlauf beginnt. Der Wert 0 für *nAngle* gibt an, der Farbverlauf von der obersten Position des Rechtecks beginnt. Als *nAngle* zunimmt, die Startposition für der Farbverlauf in basierend auf den Winkel gegen den Uhrzeigersinn Richtung verschoben wird.

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie die `FillGradient2` Methode der `CDrawingManager` Klasse. Dieser Codeausschnitt ist Teil der [Beispiel neue Steuerelemente](../../overview/visual-cpp-samples.md).

[!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]

##  <a name="grayrect"></a>  CDrawingManager::GrayRect

Füllt ein Rechteck mit einer angegebenen graue Farbe an.

```
BOOL GrayRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    COLORREF clrDisabled = (COLORREF)-1);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[in] Der rechteckige Bereich, um zu füllen.

*nPercentage*<br/>
[in] Der Prozentsatz an, die Sie in das Rechteck möchten.

*clrTransparent*<br/>
[in] Die transparente Farbe.

*clrDisabled*<br/>
[in] Die Farbe, die diese Methode für die Deduplizierung Überlastung des Netzwerks verwendet, wenn *nPercentage* wird auf-1 festgelegt.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich war. andernfalls "false".

### <a name="remarks"></a>Hinweise

Für den Parameter *nPercentage*, ein niedrigerer Wert gibt eine dunklere Farbe.

Der maximale Wert für *nPercentage* ist 200. Ein Wert größer als 200 ändert nicht die Darstellung des Rechtecks. Wenn der Wert-1 ist, verwendet diese Methode *ClrDisabled* die Sättigung des Rechtecks zu beschränken.

##  <a name="highlightrect"></a>  CDrawingManager::HighlightRect

Hebt einen rechteckigen Bereich an.

```
BOOL HighlightRect(
    CRect rect,
    int nPercentage = -1,
    COLORREF clrTransparent = (COLORREF)-1,
    int nTolerance = 0,
    COLORREF clrBlend = (COLORREF)-1);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[in] Eine rechteckige Bereich markieren.

*nPercentage*<br/>
[in] Ein Prozentwert, der angibt, wie transparent die Hervorhebung werden soll.

*clrTransparent*<br/>
[in] Die transparente Farbe.

*nTolerance*<br/>
[in] Eine ganze Zahl zwischen 0 und 255, die die Toleranz Farbe angibt.

*clrBlend*<br/>
[in] Die Basis-Farbe für das füllen.

### <a name="return-value"></a>Rückgabewert

True, wenn die Methode erfolgreich ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn *nPercentage* liegt zwischen 0 und 99, `HighlightRect` das Alphablending-Algorithmus verwendet. Weitere Informationen zu den alpha-blending, finden Sie unter [Alpha-Blending-Linien und Füllungen](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills). Wenn *nPercentage* -1 ist, diese Methode verwendet die Standardebene für die Hervorhebung. Wenn *nPercentage* ist 100, wird diese Methode führt keine Aktion aus und gibt TRUE zurück.

Die Methode verwendet den Parameter *nTolerance* bestimmt, ob in den rechteckigen Bereich markieren. Um das Rechteck, unterscheiden sich die Hintergrundfarbe der Anwendung hervorzuheben und *ClrTransparent* muss weniger als *nTolerance* in jeder Komponente für Farbe (Rot, Grün und Blau).

##  <a name="hlstorgb_one"></a>  CDrawingManager::HLStoRGB_ONE

Konvertiert eine Farbe aus einer Darstellung HLS in eine RGB-Darstellung.

```
static COLORREF __stdcall HLStoRGB_ONE(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>Parameter

*H*<br/>
[in] Eine Zahl zwischen 0 und 1, die den Farbton für die Farbe darstellt.

*L*<br/>
[in] Eine Zahl zwischen 0 und 1, gibt die Helligkeit für die Farbe an.

*S*<br/>
[in] Eine Zahl zwischen 0 und 1, gibt die Sättigung für die Farbe an.

### <a name="return-value"></a>Rückgabewert

Die RGB-Darstellung der HLS-Farbe, die bereitgestellt werden soll.

### <a name="remarks"></a>Hinweise

Eine Farbe kann als HSV (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](/windows/desktop/uxguide/vis-color).

Diese Methode und die `CDrawingManager::HLStoRGB_TWO` Methode führen Sie den gleichen Vorgang, sondern erfordern andere Werte für die *H* Parameter. Bei dieser Methode *H* ist ein Prozentsatz des Kreises. In der `CDrawingManager::HLStoRGB_TWO` Methode *H* ist ein Grad an Wert zwischen 0 und 360 liegen, die beide Rot darstellen. Z. B. mit `HLStoRGB_ONE`, 0,25 für *H* entspricht der Wert 90 mit `HLStoRGB_TWO`.

##  <a name="hlstorgb_two"></a>  CDrawingManager::HLStoRGB_TWO

Konvertiert eine Farbe aus einer Darstellung HLS in eine RGB-Darstellung.

```
static COLORREF __stdcall HLStoRGB_TWO(
    double H,
    double L,
    double S);
```

### <a name="parameters"></a>Parameter

*H*<br/>
[in] Eine Zahl zwischen 0 und 360, die den Farbton für die Farbe darstellt.

*L*<br/>
[in] Eine Zahl zwischen 0 und 1, gibt die Helligkeit für die Farbe an.

*S*<br/>
[in] Eine Zahl zwischen 0 und 1, gibt die Sättigung für die Farbe an.

### <a name="return-value"></a>Rückgabewert

Die RGB-Darstellung der HLS-Farbe, die bereitgestellt werden soll.

### <a name="remarks"></a>Hinweise

Eine Farbe kann als HSV (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](/windows/desktop/uxguide/vis-color).

Diese Methode und die [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) Methode führen Sie den gleichen Vorgang, sondern erfordern andere Werte für die *H* Parameter. Bei dieser Methode *H* ist ein Grad an Wert zwischen 0 und 360 liegen, die beide Rot darstellen. In der [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) Methode *H* ist ein Prozentsatz des Kreises. Z. B. mit `HLStoRGB_ONE`, 0,25 für *H* entspricht der Wert 90 mit `HLStoRGB_TWO`.

##  <a name="hsvtorgb"></a>  CDrawingManager::HSVtoRGB

Konvertiert eine Farbe aus einer Darstellung HSV in eine RGB-Darstellung.

```
static COLORREF __stdcall HSVtoRGB(
    double H,
    double S,
    double V);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*H*|[in] Eine Zahl zwischen 0 und 360, die den Farbton für die Farbe angibt.|
|*S*|[in] Eine Zahl zwischen 0 und 1, gibt die Sättigung für die Farbe an.|
|*V*|[in] Eine Zahl zwischen 0 und 1, gibt der Wert für die Farbe an.|

### <a name="return-value"></a>Rückgabewert

Die RGB-Darstellung der Farbe HSV bereitgestellt werden soll.

### <a name="remarks"></a>Hinweise

Eine Farbe kann als HSV (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](/windows/desktop/uxguide/vis-color).

##  <a name="huetorgb"></a>  CDrawingManager::HuetoRGB

Konvertiert einen Hue-Wert in einer roten, grünen oder blauen Komponente.

```
static double __stdcall HuetoRGB(
    double m1,
    double m2,
    double h);

static BYTE __stdcall HueToRGB(
    float rm1,
    float rm2,
    float rh);
```

### <a name="parameters"></a>Parameter

*m1*<br/>
[in] Finden Sie unter "Hinweise".

*m2*<br/>
[in] Finden Sie unter "Hinweise".

*h*<br/>
[in] Finden Sie unter "Hinweise".

*rm1*<br/>
[in] Finden Sie unter "Hinweise".

*rm2*<br/>
[in] Finden Sie unter "Hinweise".

*rh*<br/>
[in] Finden Sie unter "Hinweise".

### <a name="return-value"></a>Rückgabewert

Die einzelnen roten, grünen oder blauen Komponente für die angegebene Farbton.

### <a name="remarks"></a>Hinweise

Diese Methode ist eine Hilfsmethode, die die `CDrawingManager` -Klasse verwendet, um die einzelnen Komponenten roten, grünen und blauen einer Farbe in eine HSV oder HSL-Darstellung zu berechnen. Diese Methode wird nicht direkt vom Programmierer aufgerufen werden soll. Die Eingabeparameter sind Werte, die von der Konvertierungsalgorithmus abhängen.

Um eine HSV oder HSL-Farbe in eine RGB-Darstellung zu konvertieren, rufen Sie eine der folgenden Methoden:

- [CDrawingManager::HSVtoRGB](#hsvtorgb)

- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)

- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)

##  <a name="mirrorrect"></a>  CDrawingManager::MirrorRect

Kippt ein rechteckiges Bereichs.

```
void MirrorRect(
    CRect rect,
    BOOL bHorz = TRUE);
```

### <a name="parameters"></a>Parameter

*rect*<br/>
[in] Das umschließende Rechteck des Bereichs gekippt werden soll.

*bHorz*<br/>
[in] Ein boolescher Parameter, der angibt, ob das Rechteck horizontal oder vertikal gekippt.

### <a name="remarks"></a>Hinweise

Diese Methode kann beliebiger Bereich mit den Gerätekontext, die im Besitz von spiegeln die `CDrawingManager` Klasse. Wenn *bHorz* ist auf "true" festgelegt, diese Methode den Bereich horizontal gekippt. Andernfalls Bereich vertikal gedreht.

##  <a name="pixelalpha"></a>  CDrawingManager::PixelAlpha

Berechnet die endgültige Farbe für ein halbtransparenten Pixel.

```
static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    int percent);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    double percentR,
    double percentG,
    double percentB);

static COLORREF __stdcall PixelAlpha(
    COLORREF srcPixel,
    COLORREF dstPixel,
    int percent);
```

### <a name="parameters"></a>Parameter

*srcPixel*<br/>
[in] Die erste Farbe des Pixels.

*percent*<br/>
[in] Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz darstellt. Ein Wert von 100 gibt an, dass die ursprüngliche Farbe völlig transparent ist.

*percentR*<br/>
[in] Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz für den Rot-darstellt.

*percentG*<br/>
[in] Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz für den Grünanteil darstellt.

*percentB*<br/>
[in] Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz für die blaue Komponente darstellt.

*dstPixel*<br/>
[in] Die Basis Farbe des Pixels.

### <a name="return-value"></a>Rückgabewert

Die endgültige Farbe für den halbtransparenten Pixel.

### <a name="remarks"></a>Hinweise

Dies ist eine Hilfsklasse zum farbigen anzeigen halb transparente Bitmaps und nicht direkt vom Programmierer aufgerufen werden soll.

Bei Verwendung der Version der Methode, die *DstPixel*, die endgültige Farbe ist eine Kombination von *DstPixel* und *SrcPixel*. Die *SrcPixel* entspricht der teilweise transparente Farbe für die Basisfarbe des *DstPixel*.

##  <a name="prepareshadowmask"></a>  CDrawingManager::PrepareShadowMask

Erstellt eine Bitmap, die als einen Schatten verwendet werden kann.

```
static HBITMAP __stdcall PrepareShadowMask (
    int nDepth,
    COLORREF clrBase,
    int iMinBrightness = 0,
    int iMaxBrightness = 100);
```

### <a name="parameters"></a>Parameter

*nDepth*<br/>
[in] Die Breite und Höhe des Schattens.

*clrBase*<br/>
[in] Die Farbe des Schattens.

*iMinBrightness*<br/>
[in] Die minimale Helligkeit des Schattens.

*iMaxBrightness*<br/>
[in] Die maximale Helligkeit des Schattens.

### <a name="return-value"></a>Rückgabewert

Ein Handle für die erstellte Bitmap, wenn diese Methode erfolgreich ist; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Wenn *nDepth* ist beim Wert 0 wird diese Methode beendet und gibt NULL zurück. Wenn *nDepth* kleiner als 3 ist, werden die Breite und Höhe des Schattens auf 3 Pixel festgelegt.

##  <a name="rgbtohsl"></a>  CDrawingManager::RGBtoHSL

Konvertiert eine Farbe aus einer Rot-, Grün- und Blau (RGB) Darstellung, ein Farbton, Sättigung und Helligkeit (HSL) Darstellung an.

```
static void __stdcall RGBtoHSL(
    COLORREF rgb,
    double* H,
    double* S,
    double* L);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*rgb*|[in] Die Farbe in RGB-Werte.|
|*H*|[out] Ein Zeiger auf einen Double-Wert, in dem den Farbton für die Farbe von die Methode speichert.|
|*S*|[out] Ein Zeiger auf einen Double-Wert, in dem die Methode für die Sättigung für die Farbe speichert.|
|*L*|[out] Ein Zeiger auf einen Double-Wert, in dem die Methode die Helligkeit für die Farbe speichert.|

### <a name="remarks"></a>Hinweise

Eine Farbe kann als HSV (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](/windows/desktop/uxguide/vis-color).

Der zurückgegebene Wert für *H* wird dargestellt, als Bruchzahl zwischen 0 und 1, wobei sowohl 0 und 1 rot darstellen. Die zurückgegebenen Werte für *S* und *L* sind Zahlen zwischen 0 und 1.

##  <a name="rgbtohsv"></a>  CDrawingManager::RGBtoHSV

Konvertiert eine Farbe aus einer RGB-Darstellung mit Ihrer Darstellung in einem HSV an.

```
static void __stdcall RGBtoHSV(
    COLORREF rgb,
    double* H,
    double* S,
    double* V);
```

### <a name="parameters"></a>Parameter

*rgb*<br/>
[in] Die Farbe, die in einer RGB-Darstellung zu konvertieren.

*H*<br/>
[out] Ein Zeiger auf einen Double-Wert, in dem diese Methode den resultierenden Farbton für die Farbe speichert.

*S*<br/>
[out] Ein Zeiger auf einen Double-Wert, in dem diese Methode den resultierenden Sättigung für die Farbe speichert.

*V*<br/>
[out] Ein Zeiger auf einen Double-Wert, in dem diese Methode für die Farbe den resultierenden Wert speichert.

### <a name="remarks"></a>Hinweise

Eine Farbe kann als HSV (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](/windows/desktop/uxguide/vis-color).

Der zurückgegebene Wert für *H* ist eine Zahl zwischen 0 und 360, in denen sowohl 0 und 360 Rot anzugeben. Die Rückgabe Werte für *S* und *V* sind Zahlen zwischen 0 und 1.

##  <a name="setalphapixel"></a>  CDrawingManager::SetAlphaPixel

Farben ein transparentes Pixels in einer Bitmap.

```
static void __stdcall SetAlphaPixel(
    COLORREF* pBits,
    CRect rect,
    int x,
    int y,
    int percent,
    int iShadowSize,
    COLORREF clrBase = (COLORREF)-1,
    BOOL bIsRight = TRUE);
```

### <a name="parameters"></a>Parameter

*pBits*<br/>
[in] Ein Zeiger auf die Bitwerte für die Bitmap.

*rect*<br/>
[in] Eine rechteckige Bereich in Ihrer Anwendung. Der Zeichnen-Manager zeichnet einen Schatten unterhalb und rechts neben diesem Bereich.

*w*<br/>
[in] Die horizontale Koordinate des Pixels Farbe.

*y*<br/>
[in] Die vertikale Koordinate des Pixels Farbe.

*percent*<br/>
[in] Der Prozentsatz der Transparenz.

*iShadowSize*<br/>
[in] Die Breite und Höhe des Schattens.

*clrBase*<br/>
[in] Die Farbe des Schattens.

*bIsRight*<br/>
[in] Ein boolescher Parameter, der die Pixel auf Farbe angibt. Weitere Informationen finden Sie im Abschnitt Hinweise.

### <a name="remarks"></a>Hinweise

Diese Methode ist eine Hilfsmethode, mit dem die [CDrawingManager::DrawShadow](#drawshadow) Methode. Es wird empfohlen, wenn Sie einen Schatten, zeichnen möchten Aufrufen `CDrawingManager::DrawShadow` stattdessen.

Wenn *bIsRight* ist auf "true" festgelegt, wird das Pixel Farbe gemessen *x* Pixel aus dem rechten Rand des *Rect*. Das Pixel Farbe wird gemessen, wenn es auf "false" ist, *x* Pixel vom linken Rand des *Rect*.

##  <a name="setpixel"></a>  CDrawingManager::SetPixel

Wird ein einzelnes Pixel in einer Bitmap in der angegebenen Farbe geändert.

```
static void __stdcall SetPixel(
    COLORREF* pBits,
    int cx,
    int cy,
    int x,
    int y,
    COLORREF color);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*pBits*|[in] Ein Zeiger auf die Bitwerte der Bitmap.|
|*cx*|[in] Die gesamte Breite der Bitmap.|
|*cy*|[in] Die gesamte Höhe der Bitmap.|
|*w*|[in] Die X-Koordinate des Pixels in der Bitmap ändern.|
|*y*|[in] Die y-Koordinate des Pixels in der Bitmap ändern.|
|*color*|[in] Die neue Farbe des Pixels, identifiziert durch den angegebenen Koordinaten.|

##  <a name="smartmixcolors"></a>  CDrawingManager::SmartMixColors

Kombiniert zwei Farben basierend auf einer gewichteten Verhältnis.

```
static COLORREF __stdcall SmartMixColors(
    COLORREF color1,
    COLORREF color2,
    double dblLumRatio = 1.,
    int k1 = 1,
    int k2 = 1);
```

### <a name="parameters"></a>Parameter

|||
|-|-|
|Parameter|Beschreibung|
|*color1*|[in] Die erste Farbe, zu kombinieren.|
|*color2*|[in] Die zweite Farbe, zu kombinieren.|
|*dblLumRatio*|[in] Das Verhältnis für die Helligkeit der neuen Farbe. `SmartMixColors` Multipliziert die Helligkeit der gemischten Farbe dieses Verhältnis bevor bestimmt wird, eine endgültige Farbe.|
|*k1*|[in] Die gewichtete Verhältnis für die erste Farbe.|
|*k2*|[in] Die gewichtete Verhältnis für die zweite Farbe.|

### <a name="return-value"></a>Rückgabewert

Eine Farbe, die eine gewichtete Kombination der angegebenen Farben darstellt.

### <a name="remarks"></a>Hinweise

Diese Methode schlägt fehl mit Fehler, wenn *k1* oder *K2* ist kleiner als 0 (null). Die Methode gibt zurück, wenn beide Parameter auf 0 festgelegt werden, `RGB(0, 0, 0)`.

Die gewichtete Verhältnis wird anhand der folgenden Formel berechnet: ("Farbe1" \* k1 + color2 \* K2) /(k1 + k2). Nach das gewichtete Verhältnis bestimmt wird, wird die Methode die Helligkeit für die gemischte Farbe berechnet. Dann multipliziert die Helligkeit durch *DblLumRatio*. Wenn der Wert größer als 1,0 ist, legt die Methode die Helligkeit für die Farbe von gemischten in den neuen Wert ein. Andernfalls wird die Helligkeit auf 1.0 festgelegt.

##  <a name="drawrotated"></a>  CDrawingManager::DrawRotated

Wird eine Quell-DC-Inhalt in das angegebene Rechteck um 90 Grad gedreht.

```
void DrawRotated(
    CRect rectDest,
    CDC& dcSrc,
    BOOL bClockWise);
```

### <a name="parameters"></a>Parameter

*rectDest*<br/>
Zielrechteck.

*dcSrc*<br/>
Der Source-Gerätekontext.

*bClockWise*<br/>
TRUE gibt an, drehen + 90 Grad; FALSE gibt an, drehen-90 Grad.

### <a name="remarks"></a>Hinweise

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)
