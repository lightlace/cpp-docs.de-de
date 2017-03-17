---
title: CRenderTarget-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRenderTarget
- AFXRENDERTARGET/CRenderTarget
- AFXRENDERTARGET/CRenderTarget::CRenderTarget
- AFXRENDERTARGET/CRenderTarget::Attach
- AFXRENDERTARGET/CRenderTarget::BeginDraw
- AFXRENDERTARGET/CRenderTarget::Clear
- AFXRENDERTARGET/CRenderTarget::COLORREF_TO_D2DCOLOR
- AFXRENDERTARGET/CRenderTarget::CreateCompatibleRenderTarget
- AFXRENDERTARGET/CRenderTarget::Destroy
- AFXRENDERTARGET/CRenderTarget::Detach
- AFXRENDERTARGET/CRenderTarget::DrawBitmap
- AFXRENDERTARGET/CRenderTarget::DrawEllipse
- AFXRENDERTARGET/CRenderTarget::DrawGeometry
- AFXRENDERTARGET/CRenderTarget::DrawGlyphRun
- AFXRENDERTARGET/CRenderTarget::DrawLine
- AFXRENDERTARGET/CRenderTarget::DrawRectangle
- AFXRENDERTARGET/CRenderTarget::DrawRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::DrawText
- AFXRENDERTARGET/CRenderTarget::DrawTextLayout
- AFXRENDERTARGET/CRenderTarget::EndDraw
- AFXRENDERTARGET/CRenderTarget::FillEllipse
- AFXRENDERTARGET/CRenderTarget::FillGeometry
- AFXRENDERTARGET/CRenderTarget::FillMesh
- AFXRENDERTARGET/CRenderTarget::FillOpacityMask
- AFXRENDERTARGET/CRenderTarget::FillRectangle
- AFXRENDERTARGET/CRenderTarget::FillRoundedRectangle
- AFXRENDERTARGET/CRenderTarget::Flush
- AFXRENDERTARGET/CRenderTarget::GetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetDpi
- AFXRENDERTARGET/CRenderTarget::GetMaximumBitmapSize
- AFXRENDERTARGET/CRenderTarget::GetPixelFormat
- AFXRENDERTARGET/CRenderTarget::GetPixelSize
- AFXRENDERTARGET/CRenderTarget::GetRenderTarget
- AFXRENDERTARGET/CRenderTarget::GetSize
- AFXRENDERTARGET/CRenderTarget::GetTags
- AFXRENDERTARGET/CRenderTarget::GetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::GetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::GetTransform
- AFXRENDERTARGET/CRenderTarget::IsSupported
- AFXRENDERTARGET/CRenderTarget::IsValid
- AFXRENDERTARGET/CRenderTarget::PopAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PopLayer
- AFXRENDERTARGET/CRenderTarget::PushAxisAlignedClip
- AFXRENDERTARGET/CRenderTarget::PushLayer
- AFXRENDERTARGET/CRenderTarget::RestoreDrawingState
- AFXRENDERTARGET/CRenderTarget::SaveDrawingState
- AFXRENDERTARGET/CRenderTarget::SetAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetDpi
- AFXRENDERTARGET/CRenderTarget::SetTags
- AFXRENDERTARGET/CRenderTarget::SetTextAntialiasMode
- AFXRENDERTARGET/CRenderTarget::SetTextRenderingParams
- AFXRENDERTARGET/CRenderTarget::SetTransform
- AFXRENDERTARGET/CRenderTarget::VerifyResource
- AFXRENDERTARGET/CRenderTarget::m_lstResources
- AFXRENDERTARGET/CRenderTarget::m_pRenderTarget
- AFXRENDERTARGET/CRenderTarget::m_pTextFormatDefault
dev_langs:
- C++
helpviewer_keywords:
- CRenderTarget class
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
caps.latest.revision: 17
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6f77d482e7ee3bf0798ad488067893b3712aac62
ms.lasthandoff: 02/24/2017

---
# <a name="crendertarget-class"></a>CRenderTarget-Klasse
Ein Wrapper für ID2D1RenderTarget.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRenderTarget : public CObject;  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRenderTarget::CRenderTarget](#crendertarget)|Erstellt ein CRenderTarget-Objekt.|  
|[CRenderTarget:: ~ CRenderTarget](#crendertarget__~crendertarget)|Der Destruktor. Wird aufgerufen, wenn ein Renderingzielobjekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRenderTarget::Attach](#attach)|Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern|  
|[CRenderTarget::BeginDraw](#begindraw)|Initiiert das Zeichnen auf diesem Renderingziel.|  
|[CRenderTarget::Clear](#clear)|Löscht den Zeichnungsbereich auf die angegebene Farbe an.|  
|[CRenderTarget::COLORREF_TO_D2DCOLOR](#colorref_to_d2dcolor)|Konvertiert GDI-Farbe und Alpha-Werte in das D2D1_COLOR_F-Objekt.|  
|[CRenderTarget::CreateCompatibleRenderTarget](#createcompatiblerendertarget)|Erstellt eine neue Bitmap Renderziel für die Verwendung während der intermediate Zeichnung, die mit dem aktuellen Renderziel kompatibel ist.|  
|[CRenderTarget::Destroy](#destroy)|Löscht eine oder mehrere Ressourcen|  
|[CRenderTarget::Detach](#detach)|Trennt die Renderingzielschnittstelle vom Objekt|  
|[CRenderTarget::DrawBitmap](#drawbitmap)|Zeichnet die vom angegebenen IDWriteTextLayout-Objekt beschriebenen formatierten Text.|  
|[CRenderTarget::DrawEllipse](#drawellipse)|Zeichnet die Konturen der angegebenen Ellipse mit dem angegebenen Strichformat.|  
|[CRenderTarget::DrawGeometry](#drawgeometry)|Zeichnet die Konturen der angegebenen Geometrie mit dem angegebenen Strichformat.|  
|[CRenderTarget::DrawGlyphRun](#drawglyphrun)|Zeichnet die angegebenen Symbole.|  
|[CRenderTarget::DrawLine](#drawline)|Zeichnet eine verbindende Linie zwischen den angegebenen Punkten, die mit dem angegebenen Strichformat.|  
|[CRenderTarget::DrawRectangle](#drawrectangle)|Zeichnet die Konturen eines Rechtecks, das die angegebenen Dimensionen und Strichformat hat.|  
|[CRenderTarget::DrawRoundedRectangle](#drawroundedrectangle)|Zeichnet die Konturen des angegebenen abgerundeten Rechtecks mit dem angegebenen Strichformat.|  
|[CRenderTarget::DrawText](#drawtext)|Zeichnet den angegebenen Text unter Verwendung der von einem IDWriteTextFormat-Objekt bereitgestellte Formatinformationen.|  
|[CRenderTarget::DrawTextLayout](#drawtextlayout)|Zeichnet die vom angegebenen IDWriteTextLayout-Objekt beschriebenen formatierten Text.|  
|[CRenderTarget::EndDraw](#enddraw)|Beendet Zeichenvorgänge für das Renderingziel und gibt den aktuellen Fehlerstatus und die zugeordneten Tags.|  
|[CRenderTarget::FillEllipse](#fillellipse)|Zeichnet das Innere der angegebenen Ellipse.|  
|[CRenderTarget::FillGeometry](#fillgeometry)|Zeichnet das Innere der angegebenen Geometrie.|  
|[CRenderTarget::FillMesh](#fillmesh)|Zeichnet das Innere des angegebenen Gitter.|  
|[CRenderTarget::FillOpacityMask](#fillopacitymask)|Wendet die Deckkraftmaske, die durch die angegebene Bitmap in einen Pinsel beschrieben wird, und verwendet diesen Pinsel, um einen Bereich des Renderingziels zu zeichnen.|  
|[CRenderTarget::FillRectangle](#fillrectangle)|Zeichnet das Innere des angegebenen Rechtecks.|  
|[CRenderTarget::FillRoundedRectangle](#fillroundedrectangle)|Zeichnet das Innere des angegebenen abgerundeten Rechtecks.|  
|[CRenderTarget::Flush](#flush)|Führt alle ausstehenden Zeichenbefehle.|  
|[CRenderTarget::GetAntialiasMode](#getantialiasmode)|Ruft den aktuellen Antialiasingmodus für Nichttext-Zeichenvorgänge ab.|  
|[CRenderTarget::GetDpi](#getdpi)|Gibt das Rendern des Ziels Punkte pro Zoll (DPI)|  
|[CRenderTarget::GetMaximumBitmapSize](#getmaximumbitmapsize)|Ruft die maximale Größe in geräteabhängigen Einheiten (Pixel), einer vom Renderingziel unterstützt eine Bitmap-Dimension|  
|[CRenderTarget::GetPixelFormat](#getpixelformat)|Ruft das Pixelformat und den Alphamodus des Renderingziels ab|  
|[CRenderTarget::GetPixelSize](#getpixelsize)|Gibt die Größe des Renderingziels in Gerätepixel|  
|[CRenderTarget::GetRenderTarget](#getrendertarget)|Gibt die ID2D1RenderTarget-Schnittstelle|  
|[CRenderTarget::GetSize](#getsize)|Gibt die Größe des Renderingziels in geräteunabhängigen Pixel|  
|[CRenderTarget::GetTags](#gettags)|Ruft die Bezeichnung für nachfolgende Zeichenvorgänge ab.|  
|[CRenderTarget::GetTextAntialiasMode](#gettextantialiasmode)|Ruft den aktuellen Antialiasingmodus für Text und Symbol Zeichenvorgänge ab.|  
|[CRenderTarget::GetTextRenderingParams](#gettextrenderingparams)|Ruft die aktuellen Textrenderingoptionen des Renderingziels ab.|  
|[CRenderTarget::GetTransform](#gettransform)|Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation. Alle nachfolgenden Zeichenvorgänge treten im transformierten Raum.|  
|[CRenderTarget::IsSupported](#issupported)|Gibt an, ob das Renderingziel die angegebenen Eigenschaften unterstützt.|  
|[CRenderTarget::IsValid](#isvalid)|Die Ressource Gültigkeit überprüft|  
|[CRenderTarget::PopAxisAlignedClip](#popaxisalignedclip)|Entfernt die letzten Achse ausgerichteten Clip aus dem Renderingziel. Nachdem diese Methode aufgerufen wird, wird der Clip nicht mehr auf nachfolgende Zeichenvorgänge angewendet.|  
|[CRenderTarget::PopLayer](#poplayer)|Rufen Sie beendet die Umleitung Zeichenvorgänge auf die Ebene, die vom letzten PushLayer angegeben ist.|  
|[CRenderTarget::PushAxisAlignedClip](#pushaxisalignedclip)|Entfernt die letzten Achse ausgerichteten Clip aus dem Renderingziel. Nachdem diese Methode aufgerufen wird, wird der Clip nicht mehr auf nachfolgende Zeichenvorgänge angewendet.|  
|[CRenderTarget::PushLayer](#pushlayer)|Fügt die angegebene Ebene auf das Renderingziel so, dass er alle nachfolgenden Zeichenvorgänge empfängt, bis PopLayer aufgerufen wird.|  
|[CRenderTarget::RestoreDrawingState](#restoredrawingstate)|Legt das Renderziel zeichnen Zustand, der dem angegebenen ID2D1DrawingStateBlock fest.|  
|[CRenderTarget::SaveDrawingState](#savedrawingstate)|Speichert den aktuellen Zeichnung Zustand der angegebenen ID2D1DrawingStateBlock.|  
|[CRenderTarget::SetAntialiasMode](#setantialiasmode)|Legt die Antialiasingmodus des Renderingziels fest. Die Antialiasingmodus gilt für alle nachfolgenden Zeichenvorgänge, ohne Text und Symbol Zeichenvorgänge.|  
|[CRenderTarget::SetDpi](#setdpi)|Legt die Punkte pro Zoll (DPI) des Renderingziels fest.|  
|[CRenderTarget::SetTags](#settags)|Gibt eine Bezeichnung für nachfolgende Zeichenvorgänge.|  
|[CRenderTarget::SetTextAntialiasMode](#settextantialiasmode)|Gibt den Antialiasingmodus nachfolgenden Text und Symbol Zeichenoperationen verwenden.|  
|[CRenderTarget::SetTextRenderingParams](#settextrenderingparams)|Gibt Optionen für Text-Rendering auf allen nachfolgenden Text und Symbolzeichenvorgänge angewendet werden.|  
|[CRenderTarget::SetTransform](#settransform)|Überladen. Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation. Alle nachfolgenden Zeichenvorgänge treten im transformierten Raum.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRenderTarget::VerifyResource](#verifyresource)|Überprüft die Gültigkeit der CD2DResource-Objekt. erstellt das Objekt, wenn es noch nicht vorhanden ist.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRenderTarget::operator ID2D1RenderTarget *](#operator_id2d1rendertarget_star)|Gibt die ID2D1RenderTarget-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRenderTarget::m_lstResources](#m_lstresources)|Eine Liste von Zeigern auf CD2DResource-Objekte.|  
|[CRenderTarget::m_pRenderTarget](#m_prendertarget)|Ein Zeiger auf ein ID2D1RenderTarget-Objekt.|  
|[CRenderTarget::m_pTextFormatDefault](#m_ptextformatdefault)|Ein Zeiger auf CD2DTextFormat-Objekt, das eine Standard-Text-Format enthält.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcrendertarget"></a>CRenderTarget:: ~ CRenderTarget  
 Der Destruktor. Wird aufgerufen, wenn ein Renderingzielobjekt zerstört wird.  
  
```  
virtual ~CRenderTarget();
```  
  
##  <a name="attach"></a>CRenderTarget::Attach  
 Hängt die vorhandene Ziel-Schnittstelle für das Objekt zu rendern  
  
```  
void Attach(ID2D1RenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pRenderTarget`  
 Vorhandene Renderingzielschnittstelle. NULL darf nicht sein  
  
##  <a name="begindraw"></a>CRenderTarget::BeginDraw  
 Initiiert das Zeichnen auf diesem Renderingziel.  
  
```  
void BeginDraw();
```  
  
##  <a name="clear"></a>CRenderTarget::Clear  
 Löscht den Zeichnungsbereich auf die angegebene Farbe an.  
  
```  
void Clear(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Die Farbe, die auf die Zeichenfläche deaktiviert ist.  
  
##  <a name="colorref_to_d2dcolor"></a>CRenderTarget::COLORREF_TO_D2DCOLOR  
 Konvertiert GDI-Farbe und Alpha-Werte in das D2D1_COLOR_F-Objekt.  
  
```  
static D2D1_COLOR_F COLORREF_TO_D2DCOLOR(
    COLORREF color,  
    int nAlpha = 255);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 RGB-Wert.  
  
 `nAlpha`  
  
### <a name="return-value"></a>Rückgabewert  
 D2D1_COLOR_F-Wert.  
  
##  <a name="createcompatiblerendertarget"></a>CRenderTarget::CreateCompatibleRenderTarget  
 Erstellt eine neue Bitmap Renderziel für die Verwendung während der intermediate Zeichnung, die mit dem aktuellen Renderziel kompatibel ist.  
  
```  
BOOL CreateCompatibleRenderTarget(
    CBitmapRenderTarget& bitmapTarget,  
    CD2DSizeF sizeDesired = CD2DSizeF(0., 0.), 
    CD2DSizeU sizePixelDesired = CD2DSizeU(0, 0), 
    D2D1_PIXEL_FORMAT* desiredFormat = NULL,  
    D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS options = D2D1_COMPATIBLE_RENDER_TARGET_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>Parameter  
 `bitmapTarget`  
 Wenn diese Methode zurückgibt, enthält die Adresse eines Zeigers auf eine neue Bitmap-Renderziel. Dieser Parameter wird nicht initialisiert übergeben.  
  
 `sizeDesired`  
 Die gewünschte Größe des neuen Renderingziels in geräteunabhängigen Pixel, wenn es sich vom Original Renderingziel oder NULL. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 `sizePixelDesired`  
 Die gewünschte Größe des neuen Renderingziels in Pixel, wenn es sich vom Original Renderingziel oder NULL. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 `desiredFormat`  
 Das gewünschte Pixelformat und den Alphamodus des neuen Renderingziels oder NULL. Wenn das Pixelformat auf DXGI_FORMAT_UNKNOWN festgelegt ist, oder wenn dieser Parameter null ist, verwendet das neue Renderingziel das gleiche Pixelformat wie das ursprüngliche Renderingziel. Wenn der Alphamodus D2D1_ALPHA_MODE_UNKNOWN oder dieser Parameter NULL ist, standardmäßig der Alphamodus des neuen Renderingziels D2D1_ALPHA_MODE_PREMULTIPLIED. Informationen zu unterstützten Pixelformate finden Sie unter Unterstützte Pixelformate und Alpha-Modi.  
  
 `options`  
 Ein Wert, der angibt, ob das neue Renderingziel mit GDI kompatibel sein muss.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben.  
  
##  <a name="crendertarget"></a>CRenderTarget::CRenderTarget  
 Erstellt ein CRenderTarget-Objekt.  
  
```  
CRenderTarget();
```  
  
##  <a name="destroy"></a>CRenderTarget::Destroy  
 Löscht eine oder mehrere Ressourcen  
  
```  
BOOL Destroy(BOOL bDeleteResources = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bDeleteResources`  
 Wenn bDeleteResources TRUE ist, werden alle Ressourcen in m_lstResources befinden, automatisch zerstört.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird TRUE zurückgegeben. Andernfalls wird FALSE zurückgegeben  
  
##  <a name="detach"></a>CRenderTarget::Detach  
 Trennt die Renderingzielschnittstelle vom Objekt  
  
```  
ID2D1RenderTarget* Detach ();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennte Renderingzielschnittstelle.  
  
##  <a name="drawbitmap"></a>CRenderTarget::DrawBitmap  
 Zeichnet die vom angegebenen IDWriteTextLayout-Objekt beschriebenen formatierten Text.  
  
```  
void DrawBitmap(
    CD2DBitmap* pBitmap,  
    const CD2DRectF& rectDest,  
    float fOpacity = 1.0,  
    D2D1_BITMAP_INTERPOLATION_MODE interpolationMode = D2D1_BITMAP_INTERPOLATION_MODE_LINEAR,  
    const CD2DRectF* pRectSrc = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pBitmap`  
 Die Bitmap gerendert werden soll.  
  
 `rectDest`  
 Die Größe und Position in geräteunabhängigen Pixel im Koordinatenraum des Renderingziels, Bereich, dem die Bitmap gezeichnet wird. Wenn das Rechteck nicht gut sortierte ist, wird nichts gezeichnet, aber das Renderziel gibt einen Fehlerzustand nicht ein.  
  
 `fOpacity`  
 Ein Wert zwischen 0, 0f und 1. 0f liegen, gibt an, dass Deckkraftwert für die Bitmap angewendet werden; Dieser Wert wird mit den Alphawerten des Bitmap-Inhalts multipliziert.  
  
 `interpolationMode`  
 Der Interpolationsmodus verwenden, wenn die Bitmap skaliert oder um den Vorgang rotiert.  
  
 `pRectSrc`  
 Die Größe und Position in geräteunabhängigen Pixel im Koordinatenraum der Bitmap, der Bereich innerhalb der Bitmap gezeichnet werden soll.  
  
##  <a name="drawellipse"></a>CRenderTarget::DrawEllipse  
 Zeichnet die Konturen der angegebenen Ellipse mit dem angegebenen Strichformat.  
  
```  
void DrawEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `ellipse`  
 Die Position und der Radius der Ellipse in geräteunabhängigen Pixeln gezeichnet werden soll.  
  
 `pBrush`  
 Der Pinsel verwendet, um die Konturen der Ellipse zu zeichnen.  
  
 `fStrokeWidth`  
 Die Stärke des Strichs der Ellipse. Der Strich wird auf die Konturen der Ellipse zentriert.  
  
 `strokeStyle`  
 Das Format des Strichs, angewendet werden, das die Ellipse Gliederung oder NULL, um einen ausgefüllten Strich zu zeichnen.  
  
##  <a name="drawgeometry"></a>CRenderTarget::DrawGeometry  
 Zeichnet die Konturen der angegebenen Geometrie mit dem angegebenen Strichformat.  
  
```  
void DrawGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pGeometry`  
 Die Geometrie gezeichnet werden soll.  
  
 `pBrush`  
 Der Pinsel, der zum Zeichnen des Strichs der Geometrie verwendet wird.  
  
 `fStrokeWidth`  
 Die Stärke des Strichs der Geometrie. Der Strich wird auf die Konturen der Geometrie zentriert.  
  
 `strokeStyle`  
 Das Format des Strichs, gelten für der Geometrie Gliederung oder NULL, um einen ausgefüllten Strich zu zeichnen.  
  
##  <a name="drawglyphrun"></a>CRenderTarget::DrawGlyphRun  
 Zeichnet die angegebenen Symbole.  
  
```  
void DrawGlyphRun(
    const CD2DPointF& ptBaseLineOrigin,  
    const DWRITE_GLYPH_RUN& glyphRun,  
    CD2DBrush* pForegroundBrush,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>Parameter  
 `ptBaseLineOrigin`  
 Der Ursprung in geräteunabhängigen Pixeln, von der Baseline der Symbole.  
  
 `glyphRun`  
 Die zu rendernden Symbole.  
  
 `pForegroundBrush`  
 Der Pinsel verwendet, um die angegebenen Symbole zu zeichnen.  
  
 `measuringMode`  
 Ein Wert, der angibt, wie Symbol Metriken verwendet werden, um Text zu messen, wenn es formatiert wird. Der Standardwert ist DWRITE_MEASURING_MODE_NATURAL.  
  
##  <a name="drawline"></a>CRenderTarget::DrawLine  
 Zeichnet eine verbindende Linie zwischen den angegebenen Punkten, die mit dem angegebenen Strichformat.  
  
```  
void DrawLine(
    const CD2DPointF& ptFrom,  
    const CD2DPointF& ptTo,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `ptFrom`  
 Der Anfangspunkt der Linie in geräteunabhängige Pixel.  
  
 `ptTo`  
 Der Endpunkt der Linie in geräteunabhängige Pixel.  
  
 `pBrush`  
 Der Pinsel verwendet, um den Strich der Linie zu zeichnen.  
  
 `fStrokeWidth`  
 Ein Wert größer als oder gleich 0, 0F, der die Breite des Strichs angibt. Wenn dieser Parameter nicht angegeben ist, wird standardmäßig auf 1. 0f. Der Strich wird in der Zeile zentriert.  
  
 `strokeStyle`  
 Die Art des zu zeichnenden Strichs, oder NULL, um eine durchgehende Linie zu zeichnen.  
  
##  <a name="drawrectangle"></a>CRenderTarget::DrawRectangle  
 Zeichnet die Konturen eines Rechtecks, das die angegebenen Dimensionen und Strichformat hat.  
  
```  
void DrawRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Die Dimensionen des Rechtecks, in geräteunabhängigen Pixel zeichnen  
  
 `pBrush`  
 Der Pinsel, den Strich des Rechtecks zu zeichnen.  
  
 `fStrokeWidth`  
 Ein Wert größer als oder gleich 0, 0F, der die Breite eines Strichs für das Rechteck angibt. Der Strich wird auf die Konturen des Rechtecks zentriert.  
  
 `strokeStyle`  
 Die Art des zu zeichnenden Strichs, oder NULL, um einen ausgefüllten Strich zu zeichnen.  
  
##  <a name="drawroundedrectangle"></a>CRenderTarget::DrawRoundedRectangle  
 Zeichnet die Konturen des angegebenen abgerundeten Rechtecks mit dem angegebenen Strichformat.  
  
```  
void DrawRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `rectRounded`  
 Die Dimensionen des abgerundeten Rechtecks, in geräteunabhängigen Pixeln gezeichnet werden soll.  
  
 `pBrush`  
 Der Pinsel, der zum Zeichnen von Konturen des abgerundeten Rechtecks verwendet wird.  
  
 `fStrokeWidth`  
 Die Breite der Strich des abgerundeten Rechtecks. Der Strich wird auf die Konturen des abgerundeten Rechtecks zentriert. Der Standardwert ist 1. 0f.  
  
 `strokeStyle`  
 Das Format des abgerundeten Rechtecks Kontur oder NULL, um einen ausgefüllten Strich zu zeichnen. Der Standardwert ist NULL.  
  
##  <a name="drawtext"></a>CRenderTarget::DrawText  
 Zeichnet den angegebenen Text unter Verwendung der von einem IDWriteTextFormat-Objekt bereitgestellte Formatinformationen.  
  
```  
void DrawText(
    const CString& strText,  
    const CD2DRectF& rect,  
    CD2DBrush* pForegroundBrush,  
    CD2DTextFormat* textFormat = NULL,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE,  
    DWRITE_MEASURING_MODE measuringMode = DWRITE_MEASURING_MODE_NATURAL);
```  
  
### <a name="parameters"></a>Parameter  
 `strText`  
 Ein Zeiger auf ein Array von Unicode-Zeichen zu zeichnen.  
  
 `rect`  
 Die Größe und Position des Bereichs, in dem der Text gezeichnet wird.  
  
 `pForegroundBrush`  
 Der Pinsel, der zum Zeichnen des Texts verwendet wird.  
  
 `textFormat`  
 Ein Objekt beschreibt, die Details des Texts zu zeichnen, z. B. die Schriftart, Schriftgrad und Textfluss formatieren.  
  
 `options`  
 Ein Wert, der angibt, ob der Text an den Pixelgrenzen ausgerichtet werden und gibt an, ob der Text auf das Layoutrechteck zugeschnitten werden soll. Der Standardwert ist D2D1_DRAW_TEXT_OPTIONS_NONE, der angibt, dass Text Pixelgrenzen ausgerichtet sein sollte und nicht auf das Layoutrechteck abgeschnitten werden sollte.  
  
 `measuringMode`  
 Ein Wert, der angibt, wie Symbol Metriken verwendet werden, um Text zu messen, wenn es formatiert wird. Der Standardwert ist DWRITE_MEASURING_MODE_NATURAL.  
  
##  <a name="drawtextlayout"></a>CRenderTarget::DrawTextLayout  
 Zeichnet die vom angegebenen IDWriteTextLayout-Objekt beschriebenen formatierten Text.  
  
```  
void DrawTextLayout(
    const CD2DPointF& ptOrigin,  
    CD2DTextLayout* textLayout,  
    CD2DBrush* pBrushForeground,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>Parameter  
 `ptOrigin`  
 Der Punkt in geräteunabhängigen Pixeln, in denen der linke obere Ecke des durch TextLayout beschriebenen Texts gezeichnet wird.  
  
 `textLayout`  
 Der formatierte Text gezeichnet werden soll. Alle Zeichnungseffekte, die nicht von ID2D1Resource erben, werden ignoriert. Zeichnungseffekte, die von ID2D1Resource erben, die keine Pinsel sind hingegen diese Methode schlägt fehl, und das Renderziel in einem Fehlerzustand abgelegt wird.  
  
 `pBrushForeground`  
 Der Pinsel, um Texte in TextLayout zu zeichnen, die nicht bereits einen Pinsel als Zeichnungseffekt (angegeben durch die IDWriteTextLayout:: SetDrawingEffect-Methode) zugeordnet werden soll.  
  
 `options`  
 Ein Wert, der angibt, ob der Text an den Pixelgrenzen ausgerichtet werden und gibt an, ob der Text auf das Layoutrechteck zugeschnitten werden soll. Der Standardwert ist D2D1_DRAW_TEXT_OPTIONS_NONE, der angibt, dass Text Pixelgrenzen ausgerichtet sein sollte und nicht auf das Layoutrechteck abgeschnitten werden sollte.  
  
##  <a name="enddraw"></a>CRenderTarget::EndDraw  
 Beendet Zeichenvorgänge für das Renderingziel und gibt den aktuellen Fehlerstatus und die zugeordneten Tags.  
  
```  
HRESULT EndDraw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="fillellipse"></a>CRenderTarget::FillEllipse  
 Zeichnet das Innere der angegebenen Ellipse.  
  
```  
void FillEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `ellipse`  
 Die Position und der Radius, in geräteunabhängigen Pixel der Ellipse zu zeichnen.  
  
 `pBrush`  
 Der Pinsel verwendet, um das Innere der Ellipse zu zeichnen.  
  
##  <a name="fillgeometry"></a>CRenderTarget::FillGeometry  
 Zeichnet das Innere der angegebenen Geometrie.  
  
```  
void FillGeometry(
    CD2DGeometry* pGeometry,  
    CD2DBrush* pBrush,  
    CD2DBrush* pOpacityBrush = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pGeometry`  
 Die Geometrie gezeichnet werden soll.  
  
 `pBrush`  
 Der Pinsel, zeichnen die Geometrie des inneren.  
  
 `pOpacityBrush`  
 Die Deckkraftmaske auf die Geometrie anwenden; NULL für keine Deckkraftmaske. Wenn eine Deckkraftmaske (der OpacityBrush-Parameter) angegeben wird, muss Pinsel ein ID2D1BitmapBrush sein, dessen x und y erweitern Modi D2D1_EXTEND_MODE_CLAMP festgelegt. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
##  <a name="fillmesh"></a>CRenderTarget::FillMesh  
 Zeichnet das Innere des angegebenen Gitter.  
  
```  
void FillMesh(
    CD2DMesh* pMesh,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `pMesh`  
 Das zu zeichnende Gitter.  
  
 `pBrush`  
 Der Pinsel, der zum Zeichnen des Netzes verwendet wird.  
  
##  <a name="fillopacitymask"></a>CRenderTarget::FillOpacityMask  
 Wendet die Deckkraftmaske, die durch die angegebene Bitmap in einen Pinsel beschrieben wird, und verwendet diesen Pinsel, um einen Bereich des Renderingziels zu zeichnen.  
  
```  
void FillOpacityMask(
    CD2DBitmap* pOpacityMask,  
    CD2DBrush* pBrush,  
    D2D1_OPACITY_MASK_CONTENT content,  
    const CD2DRectF& rectDest,  
    const CD2DRectF& rectSrc);
```  
  
### <a name="parameters"></a>Parameter  
 `pOpacityMask`  
 Die Position und der Radius, in geräteunabhängigen Pixel der Ellipse zu zeichnen.  
  
 `pBrush`  
 Der Pinsel verwendet, um den Bereich des von DestinationRectangle angegebenen Renderingziels zu zeichnen.  
  
 `content`  
 Der Typ des Inhalts die Deckkraftmaske enthält. Der Wert wird verwendet, um den Farbraum zu bestimmen, in dem die Deckkraftmaske gemischt wird.  
  
 `rectDest`  
 Der Bereich des Renderingziels in geräteunabhängigen Pixeln gezeichnet werden soll.  
  
 `rectSrc`  
 Der Bereich der Bitmap, die als Deckkraftmaske, in geräteunabhängigen Pixeln verwendet.  
  
##  <a name="fillrectangle"></a>CRenderTarget::FillRectangle  
 Zeichnet das Innere des angegebenen Rechtecks.  
  
```  
void FillRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Die Dimension des Rechtecks, in geräteunabhängigen Pixeln gezeichnet werden soll.  
  
 `pBrush`  
 Der Pinsel zum Zeichnen des Rechtecks des inneren.  
  
##  <a name="fillroundedrectangle"></a>CRenderTarget::FillRoundedRectangle  
 Zeichnet das Innere des angegebenen abgerundeten Rechtecks.  
  
```  
void FillRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `rectRounded`  
 Die Dimensionen des abgerundeten Rechtecks, in geräteunabhängigen Pixeln gezeichnet werden soll.  
  
 `pBrush`  
 Der Pinsel verwendet, um das Innere des abgerundeten Rechtecks zu zeichnen.  
  
##  <a name="flush"></a>CRenderTarget::Flush  
 Führt alle ausstehenden Zeichenbefehle.  
  
```  
void Flush(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `tag1`  
 Enthält das Tag für Zeichenvorgänge, die Fehler oder 0 verursacht werden, wenn keine Fehler aufgetreten. Dieser Parameter wird nicht initialisiert übergeben.  
  
 `tag2`  
 Enthält das Tag für Zeichenvorgänge, die Fehler oder 0 verursacht werden, wenn keine Fehler aufgetreten. Dieser Parameter wird nicht initialisiert übergeben.  
  
##  <a name="getantialiasmode"></a>CRenderTarget::GetAntialiasMode  
 Ruft den aktuellen Antialiasingmodus für Nichttext-Zeichenvorgänge ab.  
  
```  
D2D1_ANTIALIAS_MODE GetAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktueller Antialiasingmodus für Nichttext-Zeichenvorgänge.  
  
##  <a name="getdpi"></a>CRenderTarget::GetDpi  
 Gibt das Rendern des Ziels Punkte pro Zoll (DPI)  
  
```  
CD2DSizeF GetDpi() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Renderziel Punkte pro Zoll (DPI).  
  
##  <a name="getmaximumbitmapsize"></a>CRenderTarget::GetMaximumBitmapSize  
 Ruft die maximale Größe in geräteabhängigen Einheiten (Pixel), einer vom Renderingziel unterstützt eine Bitmap-Dimension  
  
```  
UINT32 GetMaximumBitmapSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Größe in Pixel einer beliebigen vom Renderingziel unterstützt eine Bitmap-dimension  
  
##  <a name="getpixelformat"></a>CRenderTarget::GetPixelFormat  
 Ruft das Pixelformat und den Alphamodus des Renderingziels ab  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Pixel-Modus und den Alphamodus des Renderingziels  
  
##  <a name="getpixelsize"></a>CRenderTarget::GetPixelSize  
 Gibt die Größe des Renderingziels in Gerätepixel  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Renderingziels in Gerätepixel  
  
##  <a name="getrendertarget"></a>CRenderTarget::GetRenderTarget  
 Gibt die ID2D1RenderTarget-Schnittstelle  
  
```  
ID2D1RenderTarget* GetRenderTarget();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1RenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getsize"></a>CRenderTarget::GetSize  
 Gibt die Größe des Renderingziels in geräteunabhängigen Pixel  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Größe des Renderingziels in geräteunabhängigen Pixel  
  
##  <a name="gettags"></a>CRenderTarget::GetTags  
 Ruft die Bezeichnung für nachfolgende Zeichenvorgänge ab.  
  
```  
void GetTags(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `tag1`  
 Enthält die erste Bezeichnung für nachfolgende Zeichenvorgänge. Dieser Parameter wird nicht initialisiert übergeben. Wenn NULL angegeben ist, wird kein Wert für diesen Parameter abgerufen.  
  
 `tag2`  
 Enthält die zweite Bezeichnung für nachfolgende Zeichenvorgänge. Dieser Parameter wird nicht initialisiert übergeben. Wenn NULL angegeben ist, wird kein Wert für diesen Parameter abgerufen.  
  
##  <a name="gettextantialiasmode"></a>CRenderTarget::GetTextAntialiasMode  
 Ruft den aktuellen Antialiasingmodus für Text und Symbol Zeichenvorgänge ab.  
  
```  
D2D1_TEXT_ANTIALIAS_MODE GetTextAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Aktuelle Antialiasingmodus für Text und Symbol Zeichenvorgänge.  
  
##  <a name="gettextrenderingparams"></a>CRenderTarget::GetTextRenderingParams  
 Ruft die aktuellen Textrenderingoptionen des Renderingziels ab.  
  
```  
void GetTextRenderingParams(IDWriteRenderingParams** textRenderingParams);
```  
  
### <a name="parameters"></a>Parameter  
 `textRenderingParams`  
 Wenn diese Methode zurückgibt, enthält die Adresse eines Zeigers auf das Renderingziel textRenderingParams die aktuelle Text-Rendering-Optionen.  
  
##  <a name="gettransform"></a>CRenderTarget::GetTransform  
 Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation. Alle nachfolgenden Zeichenvorgänge treten im transformierten Raum.  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Parameter  
 `transform`  
 Die Transformation auf das Renderingziel angewendet werden soll.  
  
##  <a name="issupported"></a>CRenderTarget::IsSupported  
 Gibt an, ob das Renderingziel die angegebenen Eigenschaften unterstützt.  
  
```  
BOOL IsSupported(const D2D1_RENDER_TARGET_PROPERTIES& renderTargetProperties) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `renderTargetProperties`  
 Die Render-Zieleigenschaften testen  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die angegebenen Renderingzieleigenschaften von diesem Renderingziel unterstützt werden. andernfalls "false"  
  
##  <a name="isvalid"></a>CRenderTarget::IsValid  
 Die Ressource Gültigkeit überprüft  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Ressource gültig ist. andernfalls FALSE.  
  
##  <a name="m_lstresources"></a>CRenderTarget::m_lstResources  
 Eine Liste von Zeigern auf CD2DResource-Objekte.  
  
```  
CObList m_lstResources;  
```  
  
##  <a name="m_prendertarget"></a>CRenderTarget::m_pRenderTarget  
 Ein Zeiger auf ein ID2D1RenderTarget-Objekt.  
  
```  
ID2D1RenderTarget* m_pRenderTarget;  
```  
  
##  <a name="m_ptextformatdefault"></a>CRenderTarget::m_pTextFormatDefault  
 Ein Zeiger auf CD2DTextFormat-Objekt, das eine Standard-Text-Format enthält.  
  
```  
CD2DTextFormat* m_pTextFormatDefault;  
```  
  
##  <a name="operator_id2d1rendertarget_star"></a>CRenderTarget::operator ID2D1RenderTarget *  
 Gibt die ID2D1RenderTarget-Schnittstelle  
  
```  
operator ID2D1RenderTarget*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine ID2D1RenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="popaxisalignedclip"></a>CRenderTarget::PopAxisAlignedClip  
 Entfernt die letzten Achse ausgerichteten Clip aus dem Renderingziel. Nachdem diese Methode aufgerufen wird, wird der Clip nicht mehr auf nachfolgende Zeichenvorgänge angewendet.  
  
```  
void PopAxisAlignedClip();
```  
  
##  <a name="poplayer"></a>CRenderTarget::PopLayer  
 Rufen Sie beendet die Umleitung Zeichenvorgänge auf die Ebene, die vom letzten PushLayer angegeben ist.  
  
```  
void PopLayer();
```  
  
##  <a name="pushaxisalignedclip"></a>CRenderTarget::PushAxisAlignedClip  
 Entfernt die letzten Achse ausgerichteten Clip aus dem Renderingziel. Nachdem diese Methode aufgerufen wird, wird der Clip nicht mehr auf nachfolgende Zeichenvorgänge angewendet.  
  
```  
void PushAxisAlignedClip(
    const CD2DRectF& rectClip,  
    D2D1_ANTIALIAS_MODE mode = D2D1_ANTIALIAS_MODE_PER_PRIMITIVE);
```  
  
### <a name="parameters"></a>Parameter  
 `rectClip`  
 Die Größe und Position des Clippingbereichs, in geräteunabhängigen Pixeln.  
  
 `mode`  
 Die Antialiasingmodus, der die Ränder von Clip Rects zu zeichnen, die Subpixelgrenzen haben, und klicken Sie auf den Clip mit dem Szeneninhalt in blend verwendet wird. Das blending wird einmal Wenn PopAxisAlignedClip-Methode aufgerufen wird, und nicht für alle Primitive innerhalb der Ebene gilt ausgeführt.  
  
##  <a name="pushlayer"></a>CRenderTarget::PushLayer  
 Fügt die angegebene Ebene auf das Renderingziel so, dass er alle nachfolgenden Zeichenvorgänge empfängt, bis PopLayer aufgerufen wird.  
  
```  
void PushLayer(
    const D2D1_LAYER_PARAMETERS& layerParameters,  
    CD2DLayer& layer);
```  
  
### <a name="parameters"></a>Parameter  
 `layerParameters`  
 Die Inhaltsgrenzen, geometrische Maske, Deckkraft, Deckkraftmaske und Antialiasingoptionen für die Ebene.  
  
 `layer`  
 Die Ebene, die nachfolgende Zeichenvorgänge empfängt.  
  
##  <a name="restoredrawingstate"></a>CRenderTarget::RestoreDrawingState  
 Legt das Renderziel zeichnen Zustand, der dem angegebenen ID2D1DrawingStateBlock fest.  
  
```  
void RestoreDrawingState(ID2D1DrawingStateBlock& drawingStateBlock);
```  
  
### <a name="parameters"></a>Parameter  
 `drawingStateBlock`  
 Der neue Zeichnung Status des Renderingziels.  
  
##  <a name="savedrawingstate"></a>CRenderTarget::SaveDrawingState  
 Speichert den aktuellen Zeichnung Zustand der angegebenen ID2D1DrawingStateBlock.  
  
```  
void SaveDrawingState(ID2D1DrawingStateBlock& drawingStateBlock) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `drawingStateBlock`  
 Bei der Rückgabe dieser Methode enthält den aktuellen Zeichnungszustand des Renderingziels. Dieser Parameter muss initialisiert werden, bevor er an die Methode übergeben wird.  
  
##  <a name="setantialiasmode"></a>CRenderTarget::SetAntialiasMode  
 Legt die Antialiasingmodus des Renderingziels fest. Die Antialiasingmodus gilt für alle nachfolgenden Zeichenvorgänge, ohne Text und Symbol Zeichenvorgänge.  
  
```  
void SetAntialiasMode(D2D1_ANTIALIAS_MODE antialiasMode);
```  
  
### <a name="parameters"></a>Parameter  
 `antialiasMode`  
 Für zukünftige Zeichenvorgänge Antialiasing-Modus.  
  
##  <a name="setdpi"></a>CRenderTarget::SetDpi  
 Legt die Punkte pro Zoll (DPI) des Renderingziels fest.  
  
```  
void SetDpi(const CD2DSizeF& sizeDPI);
```  
  
### <a name="parameters"></a>Parameter  
 `sizeDPI`  
 Ein Wert größer als oder gleich&0; (null), der die horizontale/VerticalDPI des Renderingziels angibt.  
  
##  <a name="settags"></a>CRenderTarget::SetTags  
 Gibt eine Bezeichnung für nachfolgende Zeichenvorgänge.  
  
```  
void SetTags(
    D2D1_TAG tag1,  
    D2D1_TAG tag2);
```  
  
### <a name="parameters"></a>Parameter  
 `tag1`  
 Eine Bezeichnung auf nachfolgende Zeichenvorgänge angewendet werden soll.  
  
 `tag2`  
 Eine Bezeichnung auf nachfolgende Zeichenvorgänge angewendet werden soll.  
  
##  <a name="settextantialiasmode"></a>CRenderTarget::SetTextAntialiasMode  
 Gibt den Antialiasingmodus nachfolgenden Text und Symbol Zeichenoperationen verwenden.  
  
```  
void SetTextAntialiasMode(D2D1_TEXT_ANTIALIAS_MODE textAntialiasMode);
```  
  
### <a name="parameters"></a>Parameter  
 `textAntialiasMode`  
 Die Antialiasingmodus für nachfolgende Text und Symbol Zeichenvorgänge verwenden.  
  
##  <a name="settextrenderingparams"></a>CRenderTarget::SetTextRenderingParams  
 Gibt Optionen für Text-Rendering auf allen nachfolgenden Text und Symbolzeichenvorgänge angewendet werden.  
  
```  
void SetTextRenderingParams(IDWriteRenderingParams* textRenderingParams = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `textRenderingParams`  
 Die Optionen für Wiedergabe auf allen nachfolgenden Text und Symbolzeichenvorgänge angewendet werden; NULL, um den aktuellen Text Renderingoptionen deaktivieren.  
  
##  <a name="settransform"></a>CRenderTarget::SetTransform  
 Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation. Alle nachfolgenden Zeichenvorgänge treten im transformierten Raum.  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);  
void SetTransform(const D2D1_MATRIX_3X2_F& transform);
```  
  
### <a name="parameters"></a>Parameter  
 `transform`  
 Die Transformation auf das Renderingziel angewendet werden soll.  
  
##  <a name="verifyresource"></a>CRenderTarget::VerifyResource  
 Überprüft die Gültigkeit der CD2DResource-Objekt. erstellt das Objekt, wenn es noch nicht vorhanden ist.  
  
```  
BOOL VerifyResource(CD2DResource* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Zeiger auf CD2DResource-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 TRUE ist wenn das Objekt gültig. andernfalls FALSE.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)

