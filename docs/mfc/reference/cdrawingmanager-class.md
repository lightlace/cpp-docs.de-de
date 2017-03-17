---
title: Klasse CDrawingManager | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- CDrawingManager class
ms.assetid: 9e4775ca-101b-4aa9-a85a-4d047c701215
caps.latest.revision: 30
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 53929fff6df57b4e5fe00572f8a7cec8a218c638
ms.lasthandoff: 02/24/2017

---
# <a name="cdrawingmanager-class"></a>CDrawingManager-Klasse
Die `CDrawingManager` -Klasse implementiert komplexe zeichnen Algorithmen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDrawingManager : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDrawingManager::CDrawingManager](#cdrawingmanager)|Erstellt ein `CDrawingManager`-Objekt.|  
|`CDrawingManager::~CDrawingManager`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDrawingManager::CreateBitmap_32](#createbitmap_32)|Erstellt eine 32-Bit-geräteunabhängige Bitmap (DIB), der Anwendung direkt in schreiben können.|  
|[CDrawingManager::DrawAlpha](#drawalpha)|Zeigt die Bitmaps, die transparent oder halbtransparent Pixel haben.|  
|[CDrawingManager::DrawRotated](#drawrotated)|Ein Quell-DC-Inhalt in das angegebene Rechteck von +/-90 Grad gedreht|  
|[CDrawingManager::DrawEllipse](#drawellipse)|Zeichnet eine Ellipse mit den angegebenen Farben für Füllung und Rahmen.|  
|[CDrawingManager::DrawGradientRing](#drawgradientring)|Zeichnet einen Ring und füllt sie mit einem Farbverlauf.|  
|[CDrawingManager::DrawLine CDrawingManager::DrawLineA](#drawline_cdrawingmanager__drawlinea)|Zeichnet eine Linie.|  
|[CDrawingManager::DrawRect](#drawrect)|Zeichnet ein Rechteck mit den angegebenen Farben für Füllung und Rahmen.|  
|[CDrawingManager::DrawShadow](#drawshadow)|Zeichnet einen Schatten für einen rechteckigen Bereich.|  
|[CDrawingManager::Fill4ColorsGradient](#fill4colorsgradient)|Füllt einen rechteckigen Bereich mit zwei Farbverläufe aus.|  
|[CDrawingManager::FillGradient](#fillgradient)|Füllt ein Rechteck mit einem angegebenen Farbverlauf.|  
|[CDrawingManager::FillGradient2](#fillgradient2)|Füllt ein Rechteck mit einem angegebenen Farbverlauf. Die Richtung des Farbverlaufs Farbe ändern, wird ebenfalls angegeben.|  
|[CDrawingManager::GrayRect](#grayrect)|Füllt ein Rechteck mit einem angegebenen grau angezeigt.|  
|[CDrawingManager::HighlightRect](#highlightrect)|Markiert einen rechteckigen Bereich.|  
|[CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)|Konvertiert eine Farbe aus einer Darstellung HLS in eine RGB-Darstellung.|  
|[CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)|Konvertiert eine Farbe aus einer Darstellung HLS in eine RGB-Darstellung.|  
|[CDrawingManager::HSVtoRGB](#hsvtorgb)|Konvertiert eine Farbe aus einer Darstellung HSV in eine RGB-Darstellung.|  
|[CDrawingManager::HuetoRGB](#huetorgb)|Hilfsmethode, die einen Farbtonwert in eine Komponente Rot, Grün oder Blau konvertiert.|  
|[CDrawingManager::MirrorRect](#mirrorrect)|Kippt ein Rechteck.|  
|[CDrawingManager::PixelAlpha](#pixelalpha)|Hilfsmethode, die die endgültige Farbe für einen halbtransparenten Pixel bestimmt.|  
|[CDrawingManager::PrepareShadowMask](#prepareshadowmask)|Erstellt eine Bitmap, die als Schatten verwendet werden kann.|  
|[CDrawingManager::RGBtoHSL](#rgbtohsl)|Konvertiert eine Farbe aus einer RGB-Darstellung in eine HSL.|  
|[CDrawingManager::RGBtoHSV](#rgbtohsv)|Konvertiert eine Farbe aus einer RGB-Darstellung in eine HSV.|  
|[CDrawingManager::SetAlphaPixel](#setalphapixel)|Hilfsmethode, die Farben ein teilweise transparentes Pixels in einer Bitmap.|  
|[CDrawingManager::SetPixel](#setpixel)|Hilfsmethode, die ein einzelnes Pixel in einer Bitmap in der angegebenen Farbe ändert.|  
|[CDrawingManager::SmartMixColors](#smartmixcolors)|Kombiniert zwei Farben basierend auf einem gewichteten Verhältnis.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CDrawingManager` Klasse bietet Funktionen zum Zeichnen von Schatten, Farbverläufe und Rechtecke hervorgehoben. Er führt auch die Alpha-Blending überlagern. Sie können diese Klasse verwenden, auf um der Benutzeroberfläche der Anwendung direkt zu ändern.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
 `CDrawingManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdrawmanager.h  
  
##  <a name="cdrawingmanager"></a>CDrawingManager::CDrawingManager  
 Erstellt eine [CDrawingManager](../../mfc/reference/cdrawingmanager-class.md) Objekt.  
  
```  
CDrawingManager(CDC& dc);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dc`  
 Ein Verweis zu einem Gerätekontext. Die `CDrawingManager` dieser Kontext zum Zeichnen verwendet.  
  
##  <a name="createbitmap_32"></a>CDrawingManager::CreateBitmap_32  
 Erstellt eine 32-Bit-geräteunabhängige Bitmap (DIB), der Anwendung direkt in schreiben können.  
  
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
|[out] `pBits`|Ein Zeiger auf einen Datenzeiger, der den Speicherort der DIB empfängt bit-Werten.|  
|`bitmap`|Ein Handle zu der ursprünglichen bitmap|  
|`clrTransparent`|Transparente Farbe der ursprünglichen Bitmap angeben RGB-Wert.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für die neu erstellte DIB Bitmap aus, wenn diese Methode erfolgreich ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Erstellen einer Bitmap DIB finden Sie unter [CreateDIBSection](http://msdn.microsoft.com/library/windows/desktop/dd183491).  
  
##  <a name="drawalpha"></a>CDrawingManager::DrawAlpha  
 Zeigt die Bitmaps, die transparent oder halbtransparent Pixel haben.  
  
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
 Diese Methode führt Alpha-blending für zwei Bitmaps. Weitere Informationen zu Alpha-Blending überlagern, finden Sie unter [AlphaBlend](http://msdn.microsoft.com/library/windows/desktop/dd183351) im Windows SDK.  
  
##  <a name="drawellipse"></a>CDrawingManager::DrawEllipse  
 Zeichnet eine Ellipse mit den angegebenen Farben für Füllung und Rahmen.  
  
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
 Diese Methode wird ohne eine Ellipse zeichnen, wenn entweder Farbe auf-1 festgelegt ist. Es gibt auch ohne eine Ellipse zeichnen, wenn eine Dimension des umschließenden Rechtecks 0 ist.  
  
##  <a name="drawgradientring"></a>CDrawingManager::DrawGradientRing  
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
 Die erste Farbe für den Farbverlauf.  
  
 [in] `colorFinish`  
 Die letzte Farbe für den Farbverlauf.  
  
 [in] `colorBorder`  
 Die Farbe des Rahmens.  
  
 [in] `nAngle`  
 Ein Parameter, der den Anfangswinkel Farbverlauf zeichnen angibt. Dieser Wert muss zwischen 0 und 360.  
  
 [in] `nWidth`  
 Die Breite des Rahmens des Rings.  
  
 [in] `clrFace`  
 Die Farbe des inneren des Rings.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Durch definierten Rechtecks `rect` müssen mindestens 5 Pixel breit und 5 Pixel hoch sein.  
  
##  <a name="drawline_cdrawingmanager__drawlinea"></a>CDrawingManager::DrawLine CDrawingManager::DrawLineA  
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
|[in] `x1`|Die X-Koordinate, an der Zeile beginnt.|  
|[in] `y1`|Die y-Koordinate, an der Zeile beginnt.|  
|[in] `x2`|Die X-Koordinate, an dem die Zeile endet.|  
|[in] `y2`|Die y-Koordinate, an dem die Zeile endet.|  
|[in] `clrLine`|Die Farbe der Linie.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn `clrLine` gleich-1 ist.  
  
##  <a name="drawrect"></a>CDrawingManager::DrawRect  
 Zeichnet ein Rechteck mit den angegebenen Farben für Füllung und Rahmen.  
  
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
 Diese Methode wird von die Farbe für den Rahmen des Rechtecks verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt zurück, ohne ein Rechteck zeichnen, wenn entweder Farbe auf-1 festgelegt ist. Außerdem wird zurückgegeben, wenn eine Dimension des Rechtecks 0 ist.  
  
##  <a name="drawshadow"></a>CDrawingManager::DrawShadow  
 Zeichnet einen Schatten für einen rechteckigen Bereich.  
  
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
 Einen rechteckigen Bereich in der Anwendung. Die Zeichnung Manager zeichnet einen Schatten unterhalb dieser Bereich.  
  
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
 Ein boolescher Parameter, der angibt, wie der Schatten gezeichnet wird. Wenn `bRightShadow` ist `TRUE`, `DrawShadow` zeichnet einen Schatten auf der rechten Seite des Rechtecks.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Sie können zwei gültige Bitmaps für die unteren und rechten Schatten bereitstellen, mit den Parametern `pBmpSaveBottom` und `pBmpSaveRight`. Wenn diese [CBitmap](../../mfc/reference/cbitmap-class.md) Objekte verfügen über eine angefügte GDI-Objekt `DrawShadow` verwenden diese Bitmaps als Schatten. Wenn die `CBitmap` Parameter weisen eine angefügte GDI-Objekt nicht `DrawShadow` den Schatten gezeichnet und fügt die Bitmaps für die Parameter. In zukünftigen Aufrufen von `DrawShadow`, Sie können angeben, dass diese Bitmaps, um die Zeichnung zu beschleunigen. Weitere Informationen zu den `CBitmap` -Klasse und GDI-Objekte finden Sie unter [Grafikobjekte](../../mfc/graphic-objects.md).  
  
 Wenn dieser Parameter ist `NULL`, `DrawShadow` wird automatisch den Schatten gezeichnet.  
  
 Wenn Sie festlegen, `bRightShadow` , `FALSE`, unter und auf der linken Seite des rechteckigen Bereichs, der Schatten gezeichnet werden.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `DrawShadow` Methode der `CDrawingManager` Klasse. Dieser Codeausschnitt ist Teil der [Prop Blatt Demobeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_PropSheetDemo&#1;](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_1.cpp)]  
  
##  <a name="fill4colorsgradient"></a>CDrawingManager::Fill4ColorsGradient  
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
 Die endgültige Farbe für den ersten Farbverlauf.  
  
 [in] `colorStart2`  
 Die ursprüngliche Farbe für den zweiten Farbverlauf.  
  
 [in] `colorFinish2`  
 Die endgültige Farbe für den zweiten Farbverlauf.  
  
 [in] `bHorz`  
 Ein boolescher Parameter, der angibt, ob `Fill4ColorsGradient` Farben einen horizontalen oder vertikalen Farbverlauf. `TRUE`Gibt einen horizontalen Farbverlauf an.  
  
 [in] `nPercentage`  
 Eine ganze Zahl von 0 bis 100. Dieser Wert gibt den Prozentsatz des Rechtecks mit den ersten Farbverlauf füllen.  
  
### <a name="remarks"></a>Hinweise  
 Zwei Farbverläufe ein Rechteck enthält, sind sie entweder über zueinander befinden oder Weiter, abhängig vom Wert der `bHorz`. Jede Farbverlauf wird unabhängig berechnet, mit der Methode [CDrawingManager::FillGradient](#fillgradient).  
  
 Diese Methode generiert eine Assertionsfehler ausgelöst, wenn `nPercentage` kleiner als 0 oder größer als 100 ist.  
  
##  <a name="fillgradient"></a>CDrawingManager::FillGradient  
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
 Der rechteckige Bereich ausfüllen.  
  
 [in] `colorStart`  
 Die erste Farbe für den Farbverlauf.  
  
 [in] `colorFinish`  
 Die endgültige Farbe für den Farbverlauf.  
  
 [in] `bHorz`  
 Ein boolescher Parameter, der angibt, ob `FillGradient` einen horizontalen oder vertikalen Farbverlauf zeichnen soll.  
  
 [in] `nStartFlatPercentage`  
 Der Prozentsatz des Rechtecks, `FillGradient` füllt mit `colorStart` vor dem Beginn des Farbverlaufs.  
  
 [in] `nEndFlatPercentage`  
 Der Prozentsatz des Rechtecks, `FillGradient` füllt mit `colorFinish` nach Abschluss den Farbverlauf.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `FillGradient` Methode der `CDrawingManager` Klasse. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#12;](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_2.cpp)]  
  
##  <a name="fillgradient2"></a>CDrawingManager::FillGradient2  
 Füllt ein Rechteck mit einem angegebenen Farbverlauf.  
  
```  
void FillGradient2 (
    CRect rect,  
    COLORREF colorStart,  
    COLORREF colorFinish,  
    int nAngle = 0);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Der rechteckige Bereich ausfüllen.  
  
 [in] `colorStart`  
 Die erste Farbe des Farbverlaufs.  
  
 [in] `colorFinish`  
 Die letzte Farbe des Farbverlaufs.  
  
 [in] `nAngle`  
 Eine ganze Zahl zwischen 0 und 360. Dieser Parameter gibt die Richtung des Farbverlaufs an.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `nAngle` die Richtung des Farbverlaufs an. Wenn Sie die Richtung des Farbverlaufs anzugeben, geben Sie auch der Farbverlauf beginnt. Der Wert 0 für `nAngle` gibt an, der Farbverlauf beginnt am Anfang des Rechtecks. Als `nAngle` zunimmt, die Startposition für Farbverlauf in gegen den Uhrzeigersinn basierend auf dem Winkel bewegt.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `FillGradient2` Methode der `CDrawingManager` Klasse. Dieser Codeausschnitt ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#37;](../../mfc/reference/codesnippet/cpp/cdrawingmanager-class_3.cpp)]  
  
##  <a name="grayrect"></a>CDrawingManager::GrayRect  
 Füllt ein Rechteck mit einem angegebenen grau angezeigt.  
  
```  
BOOL GrayRect(
    CRect rect,  
    int nPercentage = -1,  
    COLORREF clrTransparent = (COLORREF)-1,  
    COLORREF clrDisabled = (COLORREF)-1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Der rechteckige Bereich ausfüllen.  
  
 [in] `nPercentage`  
 Der Prozentsatz der Grau in das Rechteck gewünschte.  
  
 [in] `clrTransparent`  
 Die transparente Farbe.  
  
 [in] `clrDisabled`  
 Die Farbe, die diese Methode für die Deduplizierung Sättigung verwendet, wenn `nPercentage` auf-1 festgelegt ist.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich war; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Für den Parameter `nPercentage`, ein niedrigerer Wert gibt eine dunklere Farbe.  
  
 Der maximale Wert für `nPercentage` ist 200. Ein Wert größer als 200 ändert nicht die Darstellung des Rechtecks. Diese Methode wird verwendet, wenn der Wert-1 ist, `clrDisabled` die Sättigung des Rechtecks zu beschränken.  
  
##  <a name="highlightrect"></a>CDrawingManager::HighlightRect  
 Markiert einen rechteckigen Bereich.  
  
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
 Eine rechteckige Bereich markieren.  
  
 [in] `nPercentage`  
 Ein Prozentwert, der angibt, wie transparent die Hervorhebung werden soll.  
  
 [in] `clrTransparent`  
 Die transparente Farbe.  
  
 [in] `nTolerance`  
 Eine ganze Zahl zwischen 0 und 255, gibt die Farbe.  
  
 [in] `clrBlend`  
 Die Basisfarbe für mischen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `nPercentage` liegt zwischen 0 und 99, `HighlightRect` das Alphablending-Algorithmus verwendet. Weitere Informationen zu alpha-blending, finden Sie unter [Alpha-Blending Linien und Füllungen](http://msdn.microsoft.com/library/5440f48c-3ac9-44c3-b170-c1c110bdbab8). Wenn `nPercentage`&1;, wird diese Methode verwendet die Markierung auf. Wenn `nPercentage` ist 100, diese Methode führt keine Aktion aus und gibt `TRUE`.  
  
 Die Methode verwendet den Parameter `nTolerance` zu bestimmen, ob den rechteckigen Bereich markieren. Markieren Sie das Rechteck, das die Differenz zwischen der Hintergrundfarbe der Anwendung und `clrTransparent` muss kleiner als `nTolerance` in jeder Farbkomponente (Rot, Grün und Blau).  
  
##  <a name="hlstorgb_one"></a>CDrawingManager::HLStoRGB_ONE  
 Konvertiert eine Farbe aus einer Darstellung HLS in eine RGB-Darstellung.  
  
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
 Eine Zahl zwischen 0 und 1, der die Sättigung der Farbe angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die RGB-Darstellung der bereitgestellten HLS-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Eine Farbe kann als FSH (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Diese Methode und die `CDrawingManager::HLStoRGB_TWO` Methode führen den gleichen Vorgang aus, sondern erfordern andere Werte für die `H` Parameter. Bei dieser Methode `H` ist ein Prozentsatz des Kreises. In der `CDrawingManager::HLStoRGB_TWO` -Methode `H` ein Wert zwischen 0 und 360 liegen, die rot dargestellt wird. Z. B. mit `HLStoRGB_ONE`, 0,25 für `H` entspricht dem Wert von 90 mit `HLStoRGB_TWO`.  
  
##  <a name="hlstorgb_two"></a>CDrawingManager::HLStoRGB_TWO  
 Konvertiert eine Farbe aus einer Darstellung HLS in eine RGB-Darstellung.  
  
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
 Eine Zahl zwischen 0 und 1, der die Sättigung der Farbe angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Die RGB-Darstellung der bereitgestellten HLS-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Eine Farbe kann als FSH (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Diese Methode und die [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) Methode führen den gleichen Vorgang aus, sondern erfordern andere Werte für die `H` Parameter. Bei dieser Methode `H` ein Wert zwischen 0 und 360 liegen, die rot dargestellt wird. In der [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one) -Methode `H` ist ein Prozentsatz des Kreises. Z. B. mit `HLStoRGB_ONE`, 0,25 für `H` entspricht dem Wert von 90 mit `HLStoRGB_TWO`.  
  
##  <a name="hsvtorgb"></a>CDrawingManager::HSVtoRGB  
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
|[in] `S`|Eine Zahl zwischen 0 und 1, der die Sättigung der Farbe angibt.|  
|[in] `V`|Eine Zahl zwischen 0 und 1, der den Wert für die Farbe angibt.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Darstellung der RGB-Farbe HSV bereitgestellt.  
  
### <a name="remarks"></a>Hinweise  
 Eine Farbe kann als FSH (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](http://go.microsoft.com/fwlink/linkid=119126).  
  
##  <a name="huetorgb"></a>CDrawingManager::HuetoRGB  
 Konvertiert einen Farbtonwert für eine Komponente Rot, Grün oder Blau.  
  
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
 Die einzelnen Rot, Grün oder Blau Komponente für den bereitgestellten Farbton.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ist eine Hilfsmethode, die die `CDrawingManager` -Klasse verwendet, um die einzelnen roten, grünen und blauen Komponenten einer Farbe in eine Darstellung HSV oder HSL zu berechnen. Diese Methode wird nicht direkt durch den Programmierer aufgerufen werden soll. Die Eingabeparameter sind Werte, die von der Konvertierungsalgorithmus abhängen.  
  
 Um eine HSV oder HSL-Farbe in eine RGB-Darstellung zu konvertieren, rufen Sie eine der folgenden Methoden:  
  
- [CDrawingManager::HSVtoRGB](#hsvtorgb)  
  
- [CDrawingManager::HLStoRGB_ONE](#hlstorgb_one)  
  
- [CDrawingManager::HLStoRGB_TWO](#hlstorgb_two)  
  
##  <a name="mirrorrect"></a>CDrawingManager::MirrorRect  
 Kippt ein Rechteck.  
  
```  
void MirrorRect(
    CRect rect,  
    BOOL bHorz = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rect`  
 Das umschließende Rechteck des Bereichs zu kippen.  
  
 [in] `bHorz`  
 Ein boolescher Parameter, der angibt, ob das Rechteck horizontal oder vertikal gekippt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode kann einen beliebigen Bereich auf den Gerätekontext, der im Besitz von spiegeln die `CDrawingManager` Klasse. Wenn `bHorz` Wert `TRUE`, diese Methode den Bereich horizontal gekippt. Andernfalls Bereich vertikal gedreht.  
  
##  <a name="pixelalpha"></a>CDrawingManager::PixelAlpha  
 Berechnet die endgültige Farbe für einen halbtransparenten Pixel.  
  
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
 Die ursprüngliche Farbe des Pixels.  
  
 [in] `percent`  
 Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz darstellt. Der Wert 100 gibt an, dass die ursprüngliche Farbe vollständig transparent ist.  
  
 [in] `percentR`  
 Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz für die red-Komponente darstellt.  
  
 [in] `percentG`  
 Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz für green-Komponente darstellt.  
  
 [in] `percentB`  
 Eine Zahl zwischen 0 und 100, die den Prozentsatz der Transparenz für die blaue Komponente darstellt.  
  
 [in] `dstPixel`  
 Die Grundfarbe des Pixels.  
  
### <a name="return-value"></a>Rückgabewert  
 Die endgültige Farbe für die halbtransparenten Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist eine Hilfsklasse zum Färben halb transparente Bitmaps und nicht direkt vom Programmierer aufgerufen werden soll.  
  
 Bei Verwendung der Version der Methode, die `dstPixel`, die endgültige Farbe ist eine Kombination aus `dstPixel` und `srcPixel`. Die `srcPixel` Farbe ist die teilweise transparente Farbe über die Basisfarbe des `dstPixel`.  
  
##  <a name="prepareshadowmask"></a>CDrawingManager::PrepareShadowMask  
 Erstellt eine Bitmap, die als Schatten verwendet werden kann.  
  
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
 Wenn `nDepth` ist auf 0 festgelegt, diese Methode beendet und kehrt zurück `NULL`. Wenn `nDepth` kleiner als 3 ist, werden die Breite und Höhe des Schattens auf 3 Pixel festgelegt.  
  
##  <a name="rgbtohsl"></a>CDrawingManager::RGBtoHSL  
 Konvertiert eine Farbe aus einer Darstellung des Rot-, Grün- und Blau (RGB), einem Farbton, Sättigung und Helligkeit (HSL) Darstellung.  
  
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
|[in] `rgb`|Die Farbe in RGB-Werte.|  
|[out] `H`|Ein Zeiger auf einen Double-Wert, in dem die Methode den Farbton für die Farbe speichert.|  
|[out] `S`|Ein Zeiger auf einen Double-Wert, in dem die Methode für die Sättigung der Farbe speichert.|  
|[out] `L`|Ein Zeiger auf einen Double-Wert, in dem die Methode für die Helligkeit für die Farbe speichert.|  
  
### <a name="remarks"></a>Hinweise  
 Eine Farbe kann als FSH (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Der zurückgegebene Wert für `H` wird dargestellt, als Bruchzahl zwischen 0 und 1, wobei 0 und 1 rot darstellen. Die zurückgegebenen Werte für `S` und `L` sind Zahlen zwischen 0 und 1.  
  
##  <a name="rgbtohsv"></a>CDrawingManager::RGBtoHSV  
 Konvertiert eine Farbe aus einer RGB-Darstellung in eine HSV.  
  
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
 Ein Zeiger auf einen Double-Wert, in dem diese Methode den resultierenden Farbton für die Farbe speichert.  
  
 [out] `S`  
 Ein Zeiger auf einen Double-Wert, in dem diese Methode die resultierende Sättigung für die Farbe speichert.  
  
 [out] `V`  
 Ein Zeiger auf einen Double-Wert, in dem diese Methode für die Farbe den resultierenden Wert speichert.  
  
### <a name="remarks"></a>Hinweise  
 Eine Farbe kann als FSH (Farbton, Sättigung und Wert), HSL (Farbton, Sättigung und Helligkeit) oder RGB (Rot, Grün und Blau) dargestellt werden. Weitere Informationen zu den verschiedenen Darstellungen der Farbe, finden Sie unter [Farbe](http://go.microsoft.com/fwlink/linkid=119126).  
  
 Der zurückgegebene Wert für `H` ist eine Zahl zwischen 0 und 360, in denen 0 und 360 Rot angeben. Das zurückgegebene Werte für `S` und `V` sind Zahlen zwischen 0 und 1.  
  
##  <a name="setalphapixel"></a>CDrawingManager::SetAlphaPixel  
 Farben eine transparente Pixel in einer Bitmap.  
  
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
 Einen rechteckigen Bereich in der Anwendung. Die Zeichnung Manager zeichnet einen Schatten unterhalb und rechts von diesem Bereich.  
  
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
 Diese Methode ist eine Hilfsmethode, mit der die [CDrawingManager::DrawShadow](#drawshadow) Methode. Es wird empfohlen, wenn Sie einen Schatten zeichnen möchten Aufrufen `CDrawingManager::DrawShadow` stattdessen.  
  
 Wenn `bIsRight` Wert `TRUE`, Pixels Farbe wird gemessen, `x` Pixel zwischen dem rechten Rand des `rect`. Ist dies `FALSE`, wird das Pixel Farbe gemessen `x` Pixel vom linken Rand des `rect`.  
  
##  <a name="setpixel"></a>CDrawingManager::SetPixel  
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
|[in] `cx`|Die gesamte Breite der Bitmap.|  
|[in] `cy`|Die gesamte Höhe der Bitmap.|  
|[in] `x`|Die X-Koordinate der Pixel in der Bitmap ändern.|  
|[in] `y`|Die y-Koordinate der Pixel in der Bitmap ändern.|  
|[in] `color`|Die neue Farbe des Pixels durch die angegebenen Koordinaten gekennzeichnet.|  
  
##  <a name="smartmixcolors"></a>CDrawingManager::SmartMixColors  
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
|[in] `color1`|Die erste Farbe zu mischen.|  
|[in] `color2`|Die zweite Farbe zu mischen.|  
|[in] `dblLumRatio`|Das Verhältnis für die neue Farbe Helligkeit. `SmartMixColors`Multipliziert die Helligkeit der gemischten Farbe dieses Verhältnis bevor eine endgültige Farbe bestimmt.|  
|[in] `k1`|Die gewichtete Verhältnis für die erste Farbe.|  
|[in] `k2`|Die gewichtete Verhältnis für die zweite Farbe.|  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Farbe, die eine gewichtete Mischung aus der angegebenen Farben darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode führt zu einem Fehler, wenn entweder `k1` oder `k2` ist kleiner als&0; (null). Wenn dieser Parameter auf 0 festgelegt sind, gibt die Methode `RGB(0, 0, 0)`.  
  
 Die gewichtete Verhältnis wird anhand der folgenden Formel berechnet: (color1 * k1 + color2 \* K2) /(k1 + k2). Nachdem die gewichtete Verhältnis bestimmt wurde, wird die Methode die Helligkeit für die Farbe von gemischten berechnet. Dann multipliziert es die Helligkeit durch `dblLumRatio`. Wenn der Wert größer als 1,0 ist, legt die-Methode die Helligkeit für die gemischte Farbe auf den neuen Wert. Andernfalls wird die Helligkeit auf 1.0 festgelegt.  
  
##  <a name="drawrotated"></a>CDrawingManager::DrawRotated  
 Wird ein Quell-DC-Inhalt in das angegebene Rechteck um 90 Grad gedreht.  
  
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
 Der Source-Gerätekontext.  
  
 `bClockWise`  
 `TRUE`Gibt die drehen +&90; Grad an. `FALSE` drehen-90 Grad angibt.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

