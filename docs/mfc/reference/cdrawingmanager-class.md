---
title: CDrawingManager Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b9a0255bae48ad61f140bdc8aa8a6091cf10bc77
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdrawingmanager-class"></a>CDrawingManager-Klasse
Die `CDrawingManager` Klasse implementiert komplexe zeichnen Algorithmen.  
  
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
|[CDrawingManager::DrawAlpha](#drawalpha)|Zeigt die Bitmaps, die transparent oder halbtransparenten Pixel haben.|  
|[CDrawingManager::DrawRotated](#drawrotated)|Ein Quell-DC-Inhalt in einem angegebenen Rechteck von +/-90 Grad gedreht|  
|[CDrawingManager::DrawEllipse](#drawellipse)|Zeichnet eine Ellipse, die mit den angegebenen ausfüllen und die Rahmenfarben.|  
|[CDrawingManager::DrawGradientRing](#drawgradientring)|Zeichnet einen Ring und füllt sie mit einem Farbverlauf.|  
|[CDrawingManager::DrawLine CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|Zeichnet eine verbindende Linie.|  
|[CDrawingManager::DrawRect](#drawrect)|Zeichnet ein Rechteck mit den angegebenen ausfüllen und die Rahmenfarben.|  
|[CDrawingManager::DrawShadow](#drawshadow)|Zeichnet einen Schatten für einen rechteckigen Bereich an.|  
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|Füllt einen rechteckigen Bereich mit zwei Farbverläufe aus.|  
|[CDrawingManager::FillGradient](#fillgradient)|Füllt einen rechteckigen Bereich mit einem angegebenen Farbverlauf.|  
|[CDrawingManager::FillGradient2](#fillgradient2)|Füllt einen rechteckigen Bereich mit einem angegebenen Farbverlauf. Die Richtung des Farbverlaufs Farbe ändern, wird ebenfalls angegeben.|  
|[CDrawingManager::GrayRect](#grayrect)|Füllt ein Rechteck mit einem angegebenen graue Farbe an.|  
|[CDrawingManager::HighlightRect](#highlightrect)|Markiert einen rechteckigen Bereich an.|  
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|Konvertiert eine Farbe aus einer HLS-Darstellung in eine RGB-Darstellung.|  
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|Konvertiert eine Farbe aus einer HLS-Darstellung in eine RGB-Darstellung.|  
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|Konvertiert eine Farbe aus einer Darstellung HSV in eine RGB-Darstellung.|  
|[CDrawingManager::HuetoRGB](#huetorgb)|Hilfsmethode, die einen Farbtonwert in einer roten, grünen oder blauen Komponente konvertiert.|  
|[CDrawingManager::MirrorRect](#mirrorrect)|Kippt ein rechteckiges Bereichs an.|  
|[CDrawingManager::PixelAlpha](#pixelalpha)|Hilfsmethode, die die letzte Farbe ein halbtransparenten Pixel bestimmt.|  
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|Erstellt eine Bitmap, die als einen Schatten verwendet werden kann.|  
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|Konvertiert eine Farbe aus einer RGB-Darstellung in eine HSL-Darstellung.|  
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|Konvertiert eine Farbe aus einer RGB-Darstellung in eine HSV-Darstellung.|  
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|Hilfsmethode, die eine teilweise transparente Pixel in einer Bitmap Farben.|  
|[CDrawingManager::SetPixel](#setpixel)|Hilfsmethode, die ein einzelnes Pixel in einer Bitmap in der angegebenen Farbe ändert.|  
|[CDrawingManager::SmartMixColors](#smartmixcolors)|Kombiniert zwei Farben basierend auf einem gewichteten Verhältnis.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CDrawingManager` Klasse bietet Funktionen zum Zeichnen von Schatten, Farbverläufe und hervorgehobenen Rechtecken. Er führt außerdem Alphablending. Diese Klasse können Sie die Benutzeroberfläche Ihrer Anwendung nicht direkt ändern.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
 `CDrawingManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdrawmanager.h  
  
##  <a name="cdrawingmanager"></a>  CDrawingManager::CDrawingManager  
 Erstellt eine [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) Objekt.  
  
```  
CDrawingManager(CDC& dc);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dc`  
 Ein Verweis zu einem Gerätekontext. Die `CDrawingManager` dieser Kontext zum Zeichnen verwendet.  
  
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
|[in] `size`|Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Parameter, der die Größe der Bitmap angibt.|  
|[out] `pBits`|Ein Zeiger in einen Datenzeiger, der den Speicherort der der DIB empfängt Bitwerte.|  
|`bitmap`|Ein Handle für die ursprüngliche bitmap|  
|`clrTransparent`|Transparente Farbe des ursprünglichen Bitmap angeben RGB-Wert.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die neu erstellte DIB Bitmap aus, wenn diese Methode erfolgreich ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Erstellen einer Bitmap DIB finden Sie unter [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183491).  
  
##  <a name="drawalpha"></a>  CDrawingManager::DrawAlpha  
 Zeigt die Bitmaps, die transparent oder halbtransparenten Pixel haben.  
  
```  
void DrawAlpha(
    CDC* pDstDC,  
    const CRect& rectDst,  
    CDC* pSrcDC,  
    const CRect& rectSrc);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDstDC`  
 Ein Zeiger auf den Gerätekontext für das Ziel.  
  
 [in] `rectDst`  
 Das Zielrechteck.  
  
 [in] `pSrcDC`  
 Ein Zeiger auf den Gerätekontext für die Quelle.  
  
 [in] `rectSrc`  
 Das Quellrechteck.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt Alphablending für zwei Bitmaps. Weitere Informationen zu Alphablending, finden Sie unter [AlphaBlend](http://msdn.microsoft.com/library/windows/desktop/dd183351) im Windows SDK.  
  
##  <a name="drawellipse"></a>  CDrawingManager::DrawEllipse  
 Zeichnet eine Ellipse, die mit den angegebenen ausfüllen und die Rahmenfarben.  
  
```  
void DrawEllipse(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Das umschließende Rechteck für die Ellipse.  
  
 [in] `clrFill`  
 Die Farbe, die diese Methode verwendet, um die Ellipse zu füllen.  
  
 [in] `clrLine`  
 Die Farbe verwendet diese Methode als Rahmen der Ellipse.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt zurück, ohne eine Ellipse zeichnen, wenn entweder Farbe auf-1 festgelegt ist. Es gibt auch ohne das Zeichnen einer Ellipse ist entweder Dimension des umschließenden Rechtecks 0 zurück.  
  
##  <a name="drawgradientring"></a>  CDrawingManager::DrawGradientRing  
 Zeichnet einen Ring und füllt sie mit einem Farbverlauf.  
  
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
 [in] `rect`  
 Ein [CRect](../../atl-mfc-shared/reference/crect-class.md) Parameter, der die Grenze für den Farbverlauf Ring angibt.  
  
 [in] `colorStart`  
 Der ersten Farbe für den Farbverlauf.  
  
 [in] `colorFinish`  
 Die letzte Farbe für den Farbverlauf.  
  
 [in] `colorBorder`  
 Die Farbe des Rahmens.  
  
 [in] `nAngle`  
 Ein Parameter, der angibt, die anfängliche Winkel der Verlaufsfläche zeichnen. Dieser Wert muss zwischen 0 und 360 liegen.  
  
 [in] `nWidth`  
 Die Breite des Rahmens für den Ring.  
  
 [in] `clrFace`  
 Die Farbe des inneren des Rings.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Die definierten Rechtecks `rect` müssen mindestens 5 Pixel breit und 5 Pixel sein.  
  
##  <a name="drawline_cdrawingmanager__drawlinea"></a>  CDrawingManager::DrawLine CDrawingManager::DrawLineA  
 Zeichnet eine verbindende Linie.  
  
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
|[in] `x1`|Die X-Koordinate, in die Zeile beginnt.|  
|[in] `y1`|Die y-Koordinate, in die Zeile beginnt.|  
|[in] `x2`|Die X-Koordinate, in die Zeile endet.|  
|[in] `y2`|Die y-Koordinate, in die Zeile endet.|  
|[in] `clrLine`|Die Farbe der Linie.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn `clrLine` gleich -1.  
  
##  <a name="drawrect"></a>  CDrawingManager::DrawRect  
 Zeichnet ein Rechteck mit den angegebenen ausfüllen und die Rahmenfarben.  
  
```  
void DrawRect(
    const CRect& rect,  
    COLORREF clrFill,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Die Grenzen für das Rechteck.  
  
 [in] `clrFill`  
 Die Farbe, die diese Methode verwendet, um das Rechteck zu füllen.  
  
 [in] `clrLine`  
 Diese Methode wird von der Farbe für den Rahmen des Rechtecks verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt zurück, ohne ein Rechteck zeichnen, wenn entweder Farbe auf-1 festgelegt ist. Es gibt auch auf, wenn entweder Dimension des Rechtecks 0 ist.  
  
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
 [in] `rect`  
 Eine rechteckige Bereich, in der Anwendung. Der Zeichnen-Manager wird unter diesem Bereich einen Schatten gezeichnet.  
  
 [in] `nDepth`  
 Die Breite und Höhe des Schattens.  
  
 [in] `iMinBrightness`  
 Die minimale Helligkeit des Schattens.  
  
 [in] `iMaxBrightness`  
 Die maximale Helligkeit des Schattens.  
  
 [in] `pBmpSaveBottom`  
 Ein Zeiger auf eine Bitmap, die das Bild für den unteren Teil des Schattens enthält.  
  
 [in] `pBmpSaveRight`  
 Ein Zeiger auf eine Bitmap, die das Bild für den Schatten enthält, die auf der rechten Seite des Rechtecks gezeichnet wird.  
  
 [in] `clrBase`  
 Die Farbe des Schattens.  
  
 [in] `bRightShadow`  
 Ein boolescher Parameter, der angibt, wie der Schatten gezeichnet wird. Wenn `bRightShadow` ist `TRUE`, `DrawShadow` einen Schatten auf der rechten Seite des Rechtecks zeichnet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie können zwei gültige Bitmaps für die unteren und rechten Schatten bereitstellen, indem Sie mit den Parametern `pBmpSaveBottom` und `pBmpSaveRight`. Wenn diese [CBitmap](../../mfc/reference/cbitmap-class.md) Objekte verfügen über eine angefügte GDI-Objekt `DrawShadow` verwendet diese Bitmaps als Schatten. Wenn die `CBitmap` Parameter weisen eine angefügte GDI-Objekt nicht `DrawShadow` den Schatten gezeichnet und fügt die Bitmaps für die Parameter. In Zukunft Aufrufe `DrawShadow`, Sie können diese musterbitmaps so, dass das Zeichnen beschleunigen bereitstellen. Weitere Informationen zu den `CBitmap` Klasse und GDI-Objekte, finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
 Wenn dieser Parameter ist `NULL`, `DrawShadow` wird automatisch den Schatten gezeichnet.  
  
 Wenn Sie festlegen, `bRightShadow` zu `FALSE`, darunter und auf der linken Seite des rechteckigen Bereichs der Schatten gezeichnet werden.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `DrawShadow` Methode der `CDrawingManager` Klasse. Dieser Codeausschnitt ist Teil der [Prop Blatt Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_PropSheetDemo#1](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]  
  
##  <a name="fill4colorsgradient"></a>  CDrawingManager::Fill4ColorsGradient  
 Füllt einen rechteckigen Bereich mit zwei Farbverläufe aus.  
  
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
 [in] `rect`  
 Die zu füllenden Rechtecks.  
  
 [in] `colorStart1`  
 Die ursprüngliche Farbe für den ersten Farbverlauf.  
  
 [in] `colorFinish1`  
 Die letzte Farbe für den ersten Farbverlauf.  
  
 [in] `colorStart2`  
 Die ursprüngliche Farbe für den zweiten Farbverlauf.  
  
 [in] `colorFinish2`  
 Die letzte Farbe für den zweiten Farbverlauf.  
  
 [in] `bHorz`  
 Ein boolescher Parameter, der angibt, ob `Fill4ColorsGradient` einen horizontalen oder vertikalen Farbverlauf der Farben. `TRUE` Gibt einen horizontalen Farbverlauf an.  
  
 [in] `nPercentage`  
 Eine ganze Zahl von 0 bis 100. Dieser Wert gibt den Prozentsatz der zu mit den ersten Farbverlauf zu füllenden Rechtecks.  
  
### <a name="remarks"></a>Hinweise  
 Ein Rechteck mit zwei Farbverläufe gefüllt ist, sind sie entweder über miteinander befindet oder weiter zu "other" je nach dem Wert des `bHorz`. Jede Farbverlauf wird unabhängig voneinander berechnet, mit der Methode [CDrawingManager::FillGradient](#fillgradient).  
  
 Diese Methode generiert ein Assertionsfehler ausgelöst, wenn `nPercentage` kleiner als 0 oder mehr als 100 ist.  
  
##  <a name="fillgradient"></a>  CDrawingManager::FillGradient  
 Füllt einen rechteckigen Bereich mit den angegebenen Farbverlauf aus.  
  
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
 [in] `rect`  
 Der rechteckige Bereich zu füllen.  
  
 [in] `colorStart`  
 Der ersten Farbe für den Farbverlauf.  
  
 [in] `colorFinish`  
 Die letzte Farbe für den Farbverlauf.  
  
 [in] `bHorz`  
 Ein boolescher Parameter, der angibt, ob `FillGradient` einen horizontalen oder vertikalen Farbverlauf zeichnen soll.  
  
 [in] `nStartFlatPercentage`  
 Der Prozentsatz des Rechtecks, `FillGradient` füllt mit `colorStart` vor dem Beginn des Farbverlaufs.  
  
 [in] `nEndFlatPercentage`  
 Der Prozentsatz des Rechtecks, `FillGradient` füllt mit `colorFinish` nach Abschluss der Farbverlauf.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `FillGradient` Methode der `CDrawingManager` Klasse. Dieser Codeausschnitt ist Teil der [MS Office 2007 Demobeispiel für](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#12](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]  
  
##  <a name="fillgradient2"></a>  CDrawingManager::FillGradient2  
 Füllt einen rechteckigen Bereich mit einem angegebenen Farbverlauf.  
  
```  
void FillGradient2 (
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    int nAngle = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Der rechteckige Bereich zu füllen.  
  
 [in] `colorStart`  
 Der ersten Farbe des Farbverlaufs.  
  
 [in] `colorFinish`  
 Die letzte Farbe des Farbverlaufs.  
  
 [in] `nAngle`  
 Eine ganze Zahl zwischen 0 und 360. Dieser Parameter gibt die Richtung der Farbverlauf.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `nAngle` um die Richtung der Farbverlauf anzugeben. Wenn Sie die Richtung der Farbverlauf angeben, geben Sie auch der Farbverlauf beginnt. Der Wert 0 für `nAngle` gibt an, der Verlauf von der obersten Position des Rechtecks beginnt. Als `nAngle` zunimmt, die Startposition für Farbverlauf in basierend auf der Winkel gegen den Uhrzeigersinn Richtung bewegt.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `FillGradient2` Methode der `CDrawingManager` Klasse. Dieser Codeausschnitt ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#37](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]  
  
##  <a name="grayrect"></a>  CDrawingManager::GrayRect  
 Füllt ein Rechteck mit einem angegebenen graue Farbe an.  
  
```  
BOOL GrayRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    COLORREF clrDisabled = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Der rechteckige Bereich zu füllen.  
  
 [in] `nPercentage`  
 Der Prozentsatz der Grau in das Rechteck gewünschte.  
  
 [in] `clrTransparent`  
 Die transparente Farbe.  
  
 [in] `clrDisabled`  
 Die Farbe, die diese Methode für die Deduplizierung Sättigung verwendet, wenn `nPercentage` auf-1 festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Methode erfolgreich ausgeführt wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Für den Parameter `nPercentage`, ein niedrigerer Wert gibt eine dunklere Farbe.  
  
 Der Höchstwert für `nPercentage` liegt bei 200. Ein Wert größer als 200 ändert sich nicht auf die Darstellung des Rechtecks aus. Diese Methode wird verwendet, wenn der Wert-1 ist, `clrDisabled` beschränken die Sättigung des Rechtecks.  
  
##  <a name="highlightrect"></a>  CDrawingManager::HighlightRect  
 Markiert einen rechteckigen Bereich an.  
  
```  
BOOL HighlightRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    int nTolerance = 0,  
    COLORREF clrBlend = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Eine rechteckige Bereich zu markieren.  
  
 [in] `nPercentage`  
 Ein Prozentwert, der angibt, wie transparent die Hervorhebung werden soll.  
  
 [in] `clrTransparent`  
 Die transparente Farbe.  
  
 [in] `nTolerance`  
 Eine ganze Zahl zwischen 0 und 255, die die Toleranz Farbe angibt.  
  
 [in] `clrBlend`  
 Die Basisfarbe für das füllen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nPercentage` liegt zwischen 0 und 99, `HighlightRect` der Alphablending-Algorithmus verwendet. Weitere Informationen zu Alphablending, finden Sie unter [Alpha Mischen von Linien und Füllungen](/dotnet/framework/winforms/advanced/alpha-blending-lines-and-fills). Wenn `nPercentage` -1 ist, wird diese Methode verwendet die Standardebene der Markierung. Wenn `nPercentage` ist 100, wird diese Methode führt keine Aktion aus und gibt `TRUE`.  
  
 Die Methode verwendet den Parameter `nTolerance` bestimmt, ob den rechteckigen Bereich zu markieren. Markieren Sie das Rechteck, unterscheiden sich die Hintergrundfarbe der Anwendung und `clrTransparent` muss kleiner als `nTolerance` in jeder Farbe-Komponente (Rot, Grün und Blau).  
  
##  <a name="hlstorgb_one"></a>  CDrawingManager::HLStoRGB_ONE  
 Konvertiert eine Farbe aus einer HLS-Darstellung in eine RGB-Darstellung.  
  
```  
static COLORREF __stdcall HLStoRGB_ONE(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `H`  
 Eine Zahl zwischen 0 und 1, die den Farbton für die Farbe darstellt.  
  
 [in] `L`  
 Eine Zahl zwischen 0 und 1, der die Helligkeit für die Farbe angibt.  
  
 [in] `S`  
 Eine Zahl zwischen 0 und 1, gibt die Sättigung für die Farbe an.  
  
### <a name="return-value"></a>Rückgabewert  
 Die RGB-Darstellung der bereitgestellten HLS-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Eine Farbe kann als HSV (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Diese Methode und die `CDrawingManager::HLStoRGB_TWO` -Methode der gleichen Vorgang ausgeführt, aber erfordern andere Werte für die `H` Parameter. Bei dieser Methode `H` ist ein Prozentsatz des Kreises. In der `CDrawingManager::HLStoRGB_TWO` Methode `H` ein Wert zwischen 0 und 360 liegen, die rot dargestellt wird. Z. B. mit `HLStoRGB_ONE`, 0,25 für `H` entspricht der Wert 90 mit `HLStoRGB_TWO`.  
  
##  <a name="hlstorgb_two"></a>  CDrawingManager::HLStoRGB_TWO  
 Konvertiert eine Farbe aus einer HLS-Darstellung in eine RGB-Darstellung.  
  
```  
static COLORREF __stdcall HLStoRGB_TWO(
    double H,  
    double L,  
    double S);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `H`  
 Eine Zahl zwischen 0 und 360, die den Farbton für die Farbe darstellt.  
  
 [in] `L`  
 Eine Zahl zwischen 0 und 1, der die Helligkeit für die Farbe angibt.  
  
 [in] `S`  
 Eine Zahl zwischen 0 und 1, gibt die Sättigung für die Farbe an.  
  
### <a name="return-value"></a>Rückgabewert  
 Die RGB-Darstellung der bereitgestellten HLS-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Eine Farbe kann als HSV (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Diese Methode und die [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) -Methode der gleichen Vorgang ausgeführt, aber erfordern andere Werte für die `H` Parameter. Bei dieser Methode `H` ein Wert zwischen 0 und 360 liegen, die rot dargestellt wird. In der [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) Methode `H` ist ein Prozentsatz des Kreises. Z. B. mit `HLStoRGB_ONE`, 0,25 für `H` entspricht der Wert 90 mit `HLStoRGB_TWO`.  
  
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
|[in] `H`|Eine Zahl zwischen 0 und 360, die den Farbton für die Farbe angibt.|  
|[in] `S`|Eine Zahl zwischen 0 und 1, gibt die Sättigung für die Farbe an.|  
|[in] `V`|Eine Zahl zwischen 0 und 1, der den Wert für die Farbe angibt.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die RGB-Darstellung der HSV Farbe bereitgestellt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Eine Farbe kann als HSV (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
##  <a name="huetorgb"></a>  CDrawingManager::HuetoRGB  
 Konvertiert einen Farbtonwert in eine Komponente für Rot, Grün oder Blau.  
  
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
 [in] `m1`  
 Siehe Hinweise.  
  
 [in] `m2`  
 Siehe Hinweise.  
  
 [in] `h`  
 Siehe Hinweise.  
  
 [in] `rm1`  
 Siehe Hinweise.  
  
 [in] `rm2`  
 Siehe Hinweise.  
  
 [in] `rh`  
 Siehe Hinweise.  
  
### <a name="return-value"></a>Rückgabewert  
 Die einzelnen roten, grünen oder blauen Komponente für den bereitgestellten Farbton.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist eine Hilfsmethode, die die `CDrawingManager` -Klasse verwendet, um die einzelnen Rot-, Grün- und blauen-Komponenten einer Farbe in eine HSV oder HSL-Darstellung zu berechnen. Diese Methode wird nicht direkt vom Programmierer aufgerufen werden soll. Die Eingabeparameter sind Werte, die von der Konvertierungsalgorithmus abhängen.  
  
 Rufen Sie eine der folgenden Methoden an, um eine HSV oder HSL-Farbe in eine RGB-Darstellung zu konvertieren:  
  
- [CDrawingManager::HSVtoRGB](#hsvtorgb)  
  
- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)  
  
- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)  
  
##  <a name="mirrorrect"></a>  CDrawingManager::MirrorRect  
 Kippt ein rechteckiges Bereichs an.  
  
```  
void MirrorRect(
    CRect rect,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Das umschließende Rechteck des Bereichs blättern.  
  
 [in] `bHorz`  
 Ein boolescher Parameter, der angibt, ob das Rechteck horizontal oder vertikal gekippt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann einen beliebigen Bereich auf den Gerätekontext, der im Besitz von spiegeln die `CDrawingManager` Klasse. Wenn `bHorz` festgelegt ist, um `TRUE`, diese Methode wird den Bereich horizontal gekippt. Andernfalls, sie den Bereich vertikal gekippt.  
  
##  <a name="pixelalpha"></a>  CDrawingManager::PixelAlpha  
 Berechnet die endgültige Farbe ein halbtransparenten Pixel.  
  
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
 [in] `srcPixel`  
 Die erste Farbe des Pixels.  
  
 [in] `percent`  
 Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz darstellt. Ein Wert von 100 gibt an, dass die Ausgangsfarbe vollständig transparent ist.  
  
 [in] `percentR`  
 Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz für die red-Komponente darstellt.  
  
 [in] `percentG`  
 Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz für die grünen Komponente darstellt.  
  
 [in] `percentB`  
 Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz für die blaue Komponente darstellt.  
  
 [in] `dstPixel`  
 Die Basisfarbe des Pixels.  
  
### <a name="return-value"></a>Rückgabewert  
 Die letzte Farbe für das halbtransparenten Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine Hilfsklasse zum Farbgebung halb transparente Bitmaps und nicht direkt vom Programmierer aufgerufen werden soll.  
  
 Bei Verwendung die Version der Methode, die hat `dstPixel`, endgültige Farbe ist eine Kombination von `dstPixel` und `srcPixel`. Die `srcPixel` entspricht der Farbe teilweise transparent über die Basisfarbe des `dstPixel`.  
  
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
 [in] `nDepth`  
 Die Breite und Höhe des Schattens.  
  
 [in] `clrBase`  
 Die Farbe des Schattens.  
  
 [in] `iMinBrightness`  
 Die minimale Helligkeit des Schattens.  
  
 [in] `iMaxBrightness`  
 Die maximale Helligkeit des Schattens.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die erstellte Bitmap, wenn diese Methode erfolgreich ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nDepth` ist auf 0 festgelegt, diese Methode beendet und gibt `NULL`. Wenn `nDepth` kleiner als 3 ist, werden die Breite und Höhe des Schattens auf 3 Pixel festgelegt.  
  
##  <a name="rgbtohsl"></a>  CDrawingManager::RGBtoHSL  
 Konvertiert eine Farbe aus einer Rot-, Grün- und Blau (RGB) Darstellung auf eine Farbton, Sättigung und Helligkeit (HSL) Darstellung.  
  
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
|[in] `rgb`|Die Farbe im RGB-Werte.|  
|[out] `H`|Ein Zeiger auf ein Double-Wert, in dem die Methode den Farbton für die Farbe speichert.|  
|[out] `S`|Ein Zeiger auf ein Double-Wert, in dem die Methode für die Sättigung für die Farbe speichert.|  
|[out] `L`|Ein Zeiger auf ein Double-Wert, in dem die Methode für die Helligkeit für die Farbe speichert.|  
  
### <a name="remarks"></a>Hinweise  
 Eine Farbe kann als HSV (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Der zurückgegebene Wert für `H` wird dargestellt, als Bruchzahl zwischen 0 und 1, wobei 0 und 1 rot darstellen. Die zurückgegebenen Werte für `S` und `L` sind Zahlen zwischen 0 und 1.  
  
##  <a name="rgbtohsv"></a>  CDrawingManager::RGBtoHSV  
 Konvertiert eine Farbe aus einer RGB-Darstellung in eine HSV-Darstellung.  
  
```  
static void __stdcall RGBtoHSV(
    COLORREF rgb,  
    double* H,  
    double* S,  
    double* V);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rgb`  
 Die Farbe für die Konvertierung in eine RGB-Darstellung.  
  
 [out] `H`  
 Ein Zeiger auf ein Double-Wert, in dem diese Methode den resultierenden Farbton für die Farbe speichert.  
  
 [out] `S`  
 Ein Zeiger auf ein Double-Wert, in dem diese Methode die resultierende Sättigung für die Farbe speichert.  
  
 [out] `V`  
 Ein Zeiger auf ein Double-Wert, in dem diese Methode für die Farbe den resultierenden Wert speichert.  
  
### <a name="remarks"></a>Hinweise  
 Eine Farbe kann als HSV (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](http://go.microsoft.com/fwlink/p/?linkid=119126).  
  
 Der zurückgegebene Wert für `H` ist eine Zahl zwischen 0 und 360, in denen 0 und 360 Rot anzugeben. Das zurückgegebene Werte für `S` und `V` sind Zahlen zwischen 0 und 1.  
  
##  <a name="setalphapixel"></a>  CDrawingManager::SetAlphaPixel  
 Farben in eine Bitmap eine transparente Pixel.  
  
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
 [in] `pBits`  
 Ein Zeiger auf die Bitwerte für die Bitmap.  
  
 [in] `rect`  
 Eine rechteckige Bereich, in der Anwendung. Die Zeichnung Manager zeichnet einen Schatten unter und rechts von diesem Bereich.  
  
 [in] `x`  
 Die horizontale Koordinate des Pixels Farbe.  
  
 [in] `y`  
 Die vertikale Koordinate des Pixels Farbe.  
  
 [in] `percent`  
 Der Prozentsatz der Transparenz.  
  
 [in] `iShadowSize`  
 Die Breite und Höhe des Schattens.  
  
 [in] `clrBase`  
 Die Farbe des Schattens.  
  
 [in] `bIsRight`  
 Ein boolescher Parameter, der die Pixel Farbe angibt. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist eine Hilfsmethode, die von verwendet wird, die [CDrawingManager::DrawShadow](#drawshadow) Methode. Es wird empfohlen, wenn Sie, um einen Schatten zeichnen möchten Aufrufen `CDrawingManager::DrawShadow` stattdessen.  
  
 Wenn `bIsRight` festgelegt ist, um `TRUE`, wird das Pixel Farbe gemessen `x` Pixel aus dem rechten Rand des `rect`. Ist er `FALSE`, wird das Pixel Farbe gemessen `x` Pixel vom linken Rand des `rect`.  
  
##  <a name="setpixel"></a>  CDrawingManager::SetPixel  
 Ein einzelnes Pixel in einer Bitmap in der angegebenen Farbe geändert.  
  
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
|[in] `pBits`|Ein Zeiger auf die Bitwerte der Bitmap.|  
|[in] `cx`|Die Gesamtbreite der Bitmap.|  
|[in] `cy`|Die gesamte Höhe der Bitmap.|  
|[in] `x`|Die X-Koordinate des Pixels in der Bitmap zu ändern.|  
|[in] `y`|Die y-Koordinate des Pixels in der Bitmap zu ändern.|  
|[in] `color`|Die neu ausgewählte Farbe des Pixels identifiziert durch den angegebenen Koordinaten.|  
  
##  <a name="smartmixcolors"></a>  CDrawingManager::SmartMixColors  
 Kombiniert zwei Farben basierend auf einem gewichteten Verhältnis.  
  
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
|[in] `color1`|Der ersten Farbe mischen.|  
|[in] `color2`|Der zweiten Farbe mischen.|  
|[in] `dblLumRatio`|Das Verhältnis für die neu ausgewählte Farbe Brillanz. `SmartMixColors` Multipliziert die Helligkeit der gemischten Farbe dieses Verhältnis vor eine endgültige Farbe zu bestimmen.|  
|[in] `k1`|Die gewichtete Verhältnis für die erste Farbe.|  
|[in] `k2`|Die gewichtete Verhältnis für die zweite Farbe.|  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Farbe, die eine gewichtete Mischung angegebenen Farben darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl mit Fehler, wenn `k1` oder `k2` ist kleiner als 0 (null). Wenn beide Parameter auf 0 festgelegt sind, gibt die Methode `RGB(0, 0, 0)`.  
  
 Die gewichtete Verhältnis wird anhand der folgenden Formel berechnet: (color1 * k1 + color2 \* K2) /(k1 + k2). Nachdem die gewichtete Verhältnis bestimmt ist, wird die Methode die Helligkeit für die Farbe von gemischten berechnet. Dann multipliziert die Helligkeit durch `dblLumRatio`. Wenn der Wert größer als 1,0 ist, legt die Methode die Helligkeit für die gemischte Farbe auf den neuen Wert fest. Andernfalls wird die Brillanz auf 1.0 festgelegt.  
  
##  <a name="drawrotated"></a>  CDrawingManager::DrawRotated  
 Dreht ein Quell-DC-Inhalt in einem angegebenen Rechteck 90 Grad.  
  
```  
void DrawRotated(
    CRect rectDest,  
    CDC& dcSrc,  
    BOOL bClockWise);
```  
  
### <a name="parameters"></a>Parameter  
 `rectDest`  
 Zielrechtecks.  
  
 `dcSrc`  
 Dem Quellgerätekontext.  
  
 `bClockWise`  
 `TRUE` Gibt an, drehen bis + 90 Grad. `FALSE` drehen-90 Grad angibt.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
