---
title: CRenderTarget-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CRenderTarget [MFC], CRenderTarget
- CRenderTarget [MFC], Attach
- CRenderTarget [MFC], BeginDraw
- CRenderTarget [MFC], Clear
- CRenderTarget [MFC], COLORREF_TO_D2DCOLOR
- CRenderTarget [MFC], CreateCompatibleRenderTarget
- CRenderTarget [MFC], Destroy
- CRenderTarget [MFC], Detach
- CRenderTarget [MFC], DrawBitmap
- CRenderTarget [MFC], DrawEllipse
- CRenderTarget [MFC], DrawGeometry
- CRenderTarget [MFC], DrawGlyphRun
- CRenderTarget [MFC], DrawLine
- CRenderTarget [MFC], DrawRectangle
- CRenderTarget [MFC], DrawRoundedRectangle
- CRenderTarget [MFC], DrawText
- CRenderTarget [MFC], DrawTextLayout
- CRenderTarget [MFC], EndDraw
- CRenderTarget [MFC], FillEllipse
- CRenderTarget [MFC], FillGeometry
- CRenderTarget [MFC], FillMesh
- CRenderTarget [MFC], FillOpacityMask
- CRenderTarget [MFC], FillRectangle
- CRenderTarget [MFC], FillRoundedRectangle
- CRenderTarget [MFC], Flush
- CRenderTarget [MFC], GetAntialiasMode
- CRenderTarget [MFC], GetDpi
- CRenderTarget [MFC], GetMaximumBitmapSize
- CRenderTarget [MFC], GetPixelFormat
- CRenderTarget [MFC], GetPixelSize
- CRenderTarget [MFC], GetRenderTarget
- CRenderTarget [MFC], GetSize
- CRenderTarget [MFC], GetTags
- CRenderTarget [MFC], GetTextAntialiasMode
- CRenderTarget [MFC], GetTextRenderingParams
- CRenderTarget [MFC], GetTransform
- CRenderTarget [MFC], IsSupported
- CRenderTarget [MFC], IsValid
- CRenderTarget [MFC], PopAxisAlignedClip
- CRenderTarget [MFC], PopLayer
- CRenderTarget [MFC], PushAxisAlignedClip
- CRenderTarget [MFC], PushLayer
- CRenderTarget [MFC], RestoreDrawingState
- CRenderTarget [MFC], SaveDrawingState
- CRenderTarget [MFC], SetAntialiasMode
- CRenderTarget [MFC], SetDpi
- CRenderTarget [MFC], SetTags
- CRenderTarget [MFC], SetTextAntialiasMode
- CRenderTarget [MFC], SetTextRenderingParams
- CRenderTarget [MFC], SetTransform
- CRenderTarget [MFC], VerifyResource
- CRenderTarget [MFC], m_lstResources
- CRenderTarget [MFC], m_pRenderTarget
- CRenderTarget [MFC], m_pTextFormatDefault
ms.assetid: 30d1607d-68d3-4d14-ac36-fdbd0ef903a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c7550e3e3d8bf7e49f9f93ea6e9a931d6567ef0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="crendertarget-class"></a>CRenderTarget-Klasse
Ein Wrapper für ID2D1RenderTarget.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRenderTarget : public CObject;  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRenderTarget::CRenderTarget](#crendertarget)|Erstellt ein CRenderTarget-Objekt.|  
|[CRenderTarget:: ~ CRenderTarget](#crendertarget__~crendertarget)|Der Destruktor. Wird aufgerufen, wenn ein Renderingzielobjekt zerstört wird.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRenderTarget::Attach](#attach)|Hängt die vorhandene Ziel-Schnittstelle, um das Objekt zu rendern|  
|[CRenderTarget::BeginDraw](#begindraw)|Initiiert, die auf diese Renderziel gezeichnet werden.|  
|[CRenderTarget::Clear](#clear)|Löscht den Zeichenbereich der angegebenen Farbe.|  
|[CRenderTarget::COLORREF_TO_D2DCOLOR](#colorref_to_d2dcolor)|Konvertiert GDI-Farbe und Alpha-Werte in das D2D1_COLOR_F-Objekt.|  
|[CRenderTarget::CreateCompatibleRenderTarget](#createcompatiblerendertarget)|Erstellt eine neue Bitmap-Renderziel für die Verwendung während der intermediate Zeichnung, die mit dem aktuellen Renderziel kompatibel ist.|  
|[CRenderTarget::Destroy](#destroy)|Löscht eine oder mehrere Ressourcen|  
|[CRenderTarget::Detach](#detach)|Trennt die Render-Ziel-Schnittstelle aus dem Objekt|  
|[CRenderTarget::DrawBitmap](#drawbitmap)|Zeichnet den formatierten Text, der durch das angegebene IDWriteTextLayout-Objekt beschrieben wird.|  
|[CRenderTarget::DrawEllipse](#drawellipse)|Zeichnet die Kontur der angegebenen Ellipse mit dem angegebenen Strichformat.|  
|[CRenderTarget::DrawGeometry](#drawgeometry)|Zeichnet den Überblick über die angegebene Geometrie, die mit dem angegebenen Strichformat.|  
|[CRenderTarget::DrawGlyphRun](#drawglyphrun)|Zeichnet die angegebenen Symbole.|  
|[CRenderTarget::DrawLine](#drawline)|Zeichnet eine verbindende Linie zwischen den angegebenen Punkten, die mit dem angegebenen Strichformat.|  
|[CRenderTarget::DrawRectangle](#drawrectangle)|Zeichnet den Umriss eines Rechtecks, das die angegebenen Dimensionen und Strichformat hat.|  
|[CRenderTarget::DrawRoundedRectangle](#drawroundedrectangle)|Zeichnet den Umriss des angegebenen abgerundeten Rechtecks mit dem angegebenen Strichformat.|  
|[CRenderTarget::DrawText](#drawtext)|Zeichnet den angegebenen Text unter Verwendung der Formatinformationen bereitgestellt, die von einem IDWriteTextFormat-Objekt.|  
|[CRenderTarget::DrawTextLayout](#drawtextlayout)|Zeichnet den formatierten Text, der durch das angegebene IDWriteTextLayout-Objekt beschrieben wird.|  
|[CRenderTarget::EndDraw](#enddraw)|Zeichenvorgänge auf das Renderziel endet, und gibt an, der aktuelle Status "Fehler" und den zugeordneten Tags.|  
|[CRenderTarget::FillEllipse](#fillellipse)|Zeichnet das Innere der angegebenen Ellipse.|  
|[CRenderTarget::FillGeometry](#fillgeometry)|Zeichnet das Innere der angegebenen Geometry-Instanz.|  
|[CRenderTarget::FillMesh](#fillmesh)|Zeichnet das Innere des angegebenen Netzes.|  
|[CRenderTarget::FillOpacityMask](#fillopacitymask)|Wendet die Deckkraftmaske, die durch die angegebene Bitmap in einen Pinsel beschrieben, und verwendet diesen Pinsel, um einen Bereich des Renderziels zeichnen.|  
|[CRenderTarget::FillRectangle](#fillrectangle)|Zeichnet das Innere des angegebenen Rechtecks.|  
|[CRenderTarget::FillRoundedRectangle](#fillroundedrectangle)|Zeichnet das Innere des angegebenen abgerundeten Rechtecks.|  
|[CRenderTarget::Flush](#flush)|Führt alle ausstehenden zeichnen-Befehle.|  
|[CRenderTarget::GetAntialiasMode](#getantialiasmode)|Ruft den aktuellen Antialiasingmodus für Nichttext Zeichenvorgänge ab.|  
|[CRenderTarget::GetDpi](#getdpi)|Gibt das Rendern des Ziels Punkte pro Zoll (DPI)|  
|[CRenderTarget::GetMaximumBitmapSize](#getmaximumbitmapsize)|Ruft die maximale Größe in geräteabhängige Einheiten (in Pixel), einer durch das Renderziel unterstützt eine Bitmap-Dimension|  
|[CRenderTarget::GetPixelFormat](#getpixelformat)|Ruft das Pixelformat Format und Alpha des Renderziels ab|  
|[CRenderTarget::GetPixelSize](#getpixelsize)|Gibt die Größe des Renderziels in Pixeln|  
|[CRenderTarget::GetRenderTarget](#getrendertarget)|Gibt die ID2D1RenderTarget-Schnittstelle|  
|[CRenderTarget::GetSize](#getsize)|Gibt die Größe des Renderingziels in geräteunabhängigen Pixeln|  
|[CRenderTarget::GetTags](#gettags)|Ruft die Bezeichnung für nachfolgende Zeichenvorgänge ab.|  
|[CRenderTarget::GetTextAntialiasMode](#gettextantialiasmode)|Ruft den aktuellen Antialiasingmodus für Text und Symbol Zeichenvorgänge ab.|  
|[CRenderTarget::GetTextRenderingParams](#gettextrenderingparams)|Ruft das Renderziel aktuellen Text-Rendering-Optionen ab.|  
|[CRenderTarget::GetTransform](#gettransform)|Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation an. Alle nachfolgenden Zeichenvorgänge treten in den transformierten Speicherplatz.|  
|[CRenderTarget::IsSupported](#issupported)|Gibt an, ob das Renderziel die angegebenen Eigenschaften unterstützt.|  
|[CRenderTarget::IsValid](#isvalid)|Die Ressource Gültigkeit überprüft|  
|[CRenderTarget::PopAxisAlignedClip](#popaxisalignedclip)|Entfernt die letzten Achsen ausgerichtete Clip aus das Renderziel. Nachdem diese Methode aufgerufen wird, wird der Clip nicht mehr auf nachfolgende Zeichenvorgänge angewendet.|  
|[CRenderTarget::PopLayer](#poplayer)|Rufen Sie beendet die Umleitung der Zeichenvorgänge auf die Ebene, die vom letzten PushLayer angegeben ist.|  
|[CRenderTarget::PushAxisAlignedClip](#pushaxisalignedclip)|Entfernt die letzten Achsen ausgerichtete Clip aus das Renderziel. Nachdem diese Methode aufgerufen wird, wird der Clip nicht mehr auf nachfolgende Zeichenvorgänge angewendet.|  
|[CRenderTarget::PushLayer](#pushlayer)|Fügt die angegebene Ebene im Renderziel, so, dass er alle nachfolgenden Zeichenvorgänge erhält, bis PopLayer aufgerufen wird.|  
|[CRenderTarget::RestoreDrawingState](#restoredrawingstate)|Legt das Renderziel zeichnen-Status auf, die von der angegebenen ID2D1DrawingStateBlock fest.|  
|[CRenderTarget::SaveDrawingState](#savedrawingstate)|Speichert den aktuellen Status des zeichnen an angegebenen ID2D1DrawingStateBlock.|  
|[CRenderTarget::SetAntialiasMode](#setantialiasmode)|Legt die Antialiasingmodus des Renderziels fest. Die Antialiasingmodus gilt für alle nachfolgenden Zeichenvorgänge, Text und Symbol Zeichenvorgänge ausschließen.|  
|[CRenderTarget::SetDpi](#setdpi)|Legt die Punkte pro Zoll (DPI) des Renderziels fest.|  
|[CRenderTarget::SetTags](#settags)|Gibt eine Bezeichnung für nachfolgende Zeichenvorgänge.|  
|[CRenderTarget::SetTextAntialiasMode](#settextantialiasmode)|Gibt den Antialiasingmodus für nachfolgende Text und Symbol Zeichenvorgänge verwendet.|  
|[CRenderTarget::SetTextRenderingParams](#settextrenderingparams)|Gibt Textrenderingoptionen auf alle nachfolgenden Text und Symbol Zeichenvorgänge angewendet werden soll.|  
|[CRenderTarget::SetTransform](#settransform)|Überladen. Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation an. Alle nachfolgenden Zeichenvorgänge treten in den transformierten Speicherplatz.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRenderTarget::VerifyResource](#verifyresource)|Überprüft die Gültigkeit der CD2DResource-Objekt. das Objekt erstellt, wenn er noch nicht vorhanden ist.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRenderTarget::operator ID2D1RenderTarget *](#operator_id2d1rendertarget_star)|Gibt die ID2D1RenderTarget-Schnittstelle|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CRenderTarget::m_lstResources](#m_lstresources)|Eine Liste von Zeigern auf CD2DResource-Objekte.|  
|[CRenderTarget::m_pRenderTarget](#m_prendertarget)|Ein Zeiger auf ein ID2D1RenderTarget-Objekt.|  
|[CRenderTarget::m_pTextFormatDefault](#m_ptextformatdefault)|Ein Zeiger auf CD2DTextFormat-Objekt, das Standardformat Text enthält.|  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CRenderTarget](../../mfc/reference/crendertarget-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxrendertarget.h  
  
##  <a name="_dtorcrendertarget"></a>  CRenderTarget:: ~ CRenderTarget  
 Der Destruktor. Wird aufgerufen, wenn ein Renderingzielobjekt zerstört wird.  
  
```  
virtual ~CRenderTarget();
```  
  
##  <a name="attach"></a>  CRenderTarget::Attach  
 Hängt die vorhandene Ziel-Schnittstelle, um das Objekt zu rendern  
  
```  
void Attach(ID2D1RenderTarget* pRenderTarget);
```  
  
### <a name="parameters"></a>Parameter  
 `pRenderTarget`  
 Vorhandene Render-Ziel-Schnittstelle. NULL darf nicht sein  
  
##  <a name="begindraw"></a>  CRenderTarget::BeginDraw  
 Initiiert, die auf diese Renderziel gezeichnet werden.  
  
```  
void BeginDraw();
```  
  
##  <a name="clear"></a>  CRenderTarget::Clear  
 Löscht den Zeichenbereich der angegebenen Farbe.  
  
```  
void Clear(D2D1_COLOR_F color);
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Die Farbe, die der Zeichnungsbereich deaktiviert ist.  
  
##  <a name="colorref_to_d2dcolor"></a>  CRenderTarget::COLORREF_TO_D2DCOLOR  
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
  
##  <a name="createcompatiblerendertarget"></a>  CRenderTarget::CreateCompatibleRenderTarget  
 Erstellt eine neue Bitmap-Renderziel für die Verwendung während der intermediate Zeichnung, die mit dem aktuellen Renderziel kompatibel ist.  
  
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
 Bei der Rückgabe dieser Methode enthält die Adresse eines Zeigers auf ein neues Bitmap-Renderziel. Dieser Parameter wird nicht initialisiert übergeben.  
  
 `sizeDesired`  
 Die gewünschte Größe des neuen Renderingziels in geräteunabhängigen Pixeln, wenn sie sich vom Original unterscheiden, sollten Renderziel oder NULL. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 `sizePixelDesired`  
 Die gewünschte Größe des neuen Renderingziels in Pixel, wenn sie sich vom Original unterscheiden, sollten Renderziel oder NULL. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 `desiredFormat`  
 Die gewünschte Pixelformat und alpha-Modus des neuen Renderziel oder NULL. Wenn das Pixelformat auf DXGI_FORMAT_UNKNOWN festgelegt ist, oder wenn dieser Parameter null ist, verwendet das neue Renderziel das gleiche Pixelformat wie das ursprüngliche Renderingziel. Wenn der alpha Modus D2D1_ALPHA_MODE_UNKNOWN oder dieser Parameter NULL ist, standardmäßig den alpha-Modus des neuen Renderziels D2D1_ALPHA_MODE_PREMULTIPLIED. Informationen zu unterstützter Pixelformate finden Sie unter Alpha-Modi "und" Pixelformate unterstützt.  
  
 `options`  
 Ein Wert, der angibt, ob das neue Renderziel mit GDI kompatibel sein muss.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben.  
  
##  <a name="crendertarget"></a>  CRenderTarget::CRenderTarget  
 Erstellt ein CRenderTarget-Objekt.  
  
```  
CRenderTarget();
```  
  
##  <a name="destroy"></a>  CRenderTarget::Destroy  
 Löscht eine oder mehrere Ressourcen  
  
```  
BOOL Destroy(BOOL bDeleteResources = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `bDeleteResources`  
 Wenn bDeleteResources "true" ist, werden alle Ressourcen in m_lstResources befinden automatisch zerstört werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird "Wahr" zurückgegeben. Andernfalls wird "false" zurückgegeben  
  
##  <a name="detach"></a>  CRenderTarget::Detach  
 Trennt die Render-Ziel-Schnittstelle aus dem Objekt  
  
```  
ID2D1RenderTarget* Detach ();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf getrennten Rendern Ziel-Schnittstelle.  
  
##  <a name="drawbitmap"></a>  CRenderTarget::DrawBitmap  
 Zeichnet den formatierten Text, der durch das angegebene IDWriteTextLayout-Objekt beschrieben wird.  
  
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
 Das Bitmuster zu rendern.  
  
 `rectDest`  
 Die Größe und Position in geräteunabhängigen Pixeln in das Renderziel Koordinatenbereich des Bereichs, der die Bitmap gezeichnet wird. Wenn das Rechteck nicht klar geordnete ist, nichts wird gezeichnet, aber das Renderziel wird keinen Status "Fehler" eingeben.  
  
 `fOpacity`  
 Ein Wert zwischen 0, 0f und 1. 0f liegen, gibt an, dass ein Wert für die Durchlässigkeit für die Bitmap angewendet werden; Dieser Wert wird mit den Alphawerten des Inhalts der Bitmap multipliziert.  
  
 `interpolationMode`  
 Der Interpolationsmodus verwenden, wenn die Bitmap skaliert oder wird durch den Vorgang gedreht.  
  
 `pRectSrc`  
 Die Größe und Position in geräteunabhängigen Pixeln die Bitmap Koordinatenbereich des Bereichs innerhalb der Bitmap gezeichnet werden soll.  
  
##  <a name="drawellipse"></a>  CRenderTarget::DrawEllipse  
 Zeichnet die Kontur der angegebenen Ellipse mit dem angegebenen Strichformat.  
  
```  
void DrawEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `ellipse`  
 Die Position und -Achsenradius der Ellipse, in geräteunabhängigen Pixeln gezeichnet werden soll.  
  
 `pBrush`  
 Der Pinsel, der zum Zeichnen von Konturen der Ellipse verwendet wird.  
  
 `fStrokeWidth`  
 Die Stärke des Strichs der Ellipse. Der Strich wird auf die Ellipse Gliederung zentriert.  
  
 `strokeStyle`  
 Das Format des Strichs an, das die Ellipse Gliederung oder NULL, um eine Volltonfarbe Strich gezeichnet werden soll.  
  
##  <a name="drawgeometry"></a>  CRenderTarget::DrawGeometry  
 Zeichnet den Überblick über die angegebene Geometrie, die mit dem angegebenen Strichformat.  
  
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
 Die Stärke des Strichs der Geometrie. Der Strich wird auf die Geometrie Gliederung zentriert.  
  
 `strokeStyle`  
 Der Stil der Kontur für der Geometrie Kontur, oder NULL, um eine Volltonfarbe Kontur zeichnen.  
  
##  <a name="drawglyphrun"></a>  CRenderTarget::DrawGlyphRun  
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
 Der Pinsel, der zum Zeichnen der angegebenen Symbole verwendet.  
  
 `measuringMode`  
 Ein Wert, der angibt, wie Glyphe Metriken verwendet werden, um Text zu messen, wenn die Formatierung. Der Standardwert ist DWRITE_MEASURING_MODE_NATURAL.  
  
##  <a name="drawline"></a>  CRenderTarget::DrawLine  
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
 Den Ausgangspunkt der Zeile, in geräteunabhängigen Pixeln.  
  
 `ptTo`  
 Der Endpunkt, der die Zeilen in geräteunabhängigen Pixeln.  
  
 `pBrush`  
 Der Pinsel, der zum Zeichnen der Kontur der Zeile verwendet wird.  
  
 `fStrokeWidth`  
 Ein Wert größer als oder gleich 0, 0F, der die Breite der Kontur angibt. Wenn dieser Parameter nicht angegeben ist, wird standardmäßig auf 1. 0f. Der Strich wird in der Zeile zentriert.  
  
 `strokeStyle`  
 Die Art des zu zeichnenden Strichs, oder NULL, um eine durchgehende Linie zu zeichnen.  
  
##  <a name="drawrectangle"></a>  CRenderTarget::DrawRectangle  
 Zeichnet den Umriss eines Rechtecks, das die angegebenen Dimensionen und Strichformat hat.  
  
```  
void DrawRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Die Dimensionen des zu zeichnenden in geräteunabhängigen Pixeln Rechtecks  
  
 `pBrush`  
 Der Pinsel, der das Rechteck Kontur zeichnen  
  
 `fStrokeWidth`  
 Ein Wert größer als oder gleich 0, 0F, der die Breite des Rechtecks Strichbreite angibt. Der Strich wird auf das Rechteck Gliederung zentriert.  
  
 `strokeStyle`  
 Die Art des zu zeichnenden Strichs, oder NULL, um eine Volltonfarbe Kontur zeichnen.  
  
##  <a name="drawroundedrectangle"></a>  CRenderTarget::DrawRoundedRectangle  
 Zeichnet den Umriss des angegebenen abgerundeten Rechtecks mit dem angegebenen Strichformat.  
  
```  
void DrawRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush,  
    FLOAT fStrokeWidth = 1.0,  
    ID2D1StrokeStyle* strokeStyle = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `rectRounded`  
 Die Dimensionen des abgerundeten Rechtecks Zeichnen in geräteunabhängigen Pixeln.  
  
 `pBrush`  
 Der Pinsel, der zum Zeichnen der Kontur des abgerundeten Rechtecks verwendet wird.  
  
 `fStrokeWidth`  
 Die Breite der Kontur des abgerundeten Rechtecks. Der Strich wird auf Gliederung des abgerundeten Rechtecks zentriert. Der Standardwert ist 1. 0f.  
  
 `strokeStyle`  
 Die Art des abgerundeten Rechtecks Strich oder NULL, um eine Volltonfarbe Kontur zeichnen. Der Standardwert ist NULL.  
  
##  <a name="drawtext"></a>  CRenderTarget::DrawText  
 Zeichnet den angegebenen Text unter Verwendung der Formatinformationen bereitgestellt, die von einem IDWriteTextFormat-Objekt.  
  
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
 Ein Zeiger auf ein Array von Unicode-Zeichen gezeichnet werden soll.  
  
 `rect`  
 Die Größe und Position des Bereichs, in dem der Text gezeichnet wird.  
  
 `pForegroundBrush`  
 Der Pinsel, der zum Zeichnen von Text verwendet wird.  
  
 `textFormat`  
 Ein Objekt beschreibt, formatieren die Details der zu zeichnende Text, z. B. die Schriftart, Schriftgrad und flussrichtung angeordnet.  
  
 `options`  
 Ein Wert, der angibt, ob der Text Pixel-Grenzen ausgerichtet werden, und gibt an, ob der Text, die das Layoutrechteck zugeschnitten werden soll. Der Standardwert ist D2D1_DRAW_TEXT_OPTIONS_NONE, der angibt, dass der Text sollte Pixelgrenzen ausgerichtet sein und sollte nicht auf die das Layoutrechteck abgeschnitten werden.  
  
 `measuringMode`  
 Ein Wert, der angibt, wie Glyphe Metriken verwendet werden, um Text zu messen, wenn die Formatierung. Der Standardwert ist DWRITE_MEASURING_MODE_NATURAL.  
  
##  <a name="drawtextlayout"></a>  CRenderTarget::DrawTextLayout  
 Zeichnet den formatierten Text, der durch das angegebene IDWriteTextLayout-Objekt beschrieben wird.  
  
```  
void DrawTextLayout(
    const CD2DPointF& ptOrigin,  
    CD2DTextLayout* textLayout,  
    CD2DBrush* pBrushForeground,  
    D2D1_DRAW_TEXT_OPTIONS options = D2D1_DRAW_TEXT_OPTIONS_NONE);
```  
  
### <a name="parameters"></a>Parameter  
 `ptOrigin`  
 Der Punkt in geräteunabhängigen Pixeln, an denen die linken oberen Ecke des Texts durch TextLayout beschrieben gezeichnet wird.  
  
 `textLayout`  
 Der zu zeichnende formatierte Text. Alle, die nicht von ID2D1Resource erben Zeichnungseffekte werden ignoriert. Treten Zeichnungseffekte, die von ID2D1Resource erben, die Pinsel nicht sind, wird diese Methode schlägt fehl, und das Renderziel in den Status "Fehler" versetzt wird.  
  
 `pBrushForeground`  
 Der Pinsel verwendet, um einen beliebigen Text in TextLayout zu zeichnen, die nicht bereits einen Pinsel als einen Zeichnungseffekt (angegeben durch die IDWriteTextLayout:: SetDrawingEffect-Methode) zugeordnet.  
  
 `options`  
 Ein Wert, der angibt, ob der Text Pixel-Grenzen ausgerichtet werden, und gibt an, ob der Text, die das Layoutrechteck zugeschnitten werden soll. Der Standardwert ist D2D1_DRAW_TEXT_OPTIONS_NONE, der angibt, dass der Text sollte Pixelgrenzen ausgerichtet sein und sollte nicht auf die das Layoutrechteck abgeschnitten werden.  
  
##  <a name="enddraw"></a>  CRenderTarget::EndDraw  
 Zeichenvorgänge auf das Renderziel endet, und gibt an, der aktuelle Status "Fehler" und den zugeordneten Tags.  
  
```  
HRESULT EndDraw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Methode erfolgreich ist, wird S_OK zurückgegeben. Andernfalls wird einen HRESULT-Fehlercode zurückgegeben.  
  
##  <a name="fillellipse"></a>  CRenderTarget::FillEllipse  
 Zeichnet das Innere der angegebenen Ellipse.  
  
```  
void FillEllipse(
    const CD2DEllipse& ellipse,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `ellipse`  
 Die Position und die Radius in geräteunabhängige Pixel, der zu zeichnenden Ellipse.  
  
 `pBrush`  
 Der Pinsel verwendet, um das Innere der Ellipse gezeichnet wird.  
  
##  <a name="fillgeometry"></a>  CRenderTarget::FillGeometry  
 Zeichnet das Innere der angegebenen Geometry-Instanz.  
  
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
 Der Pinsel, zeichnen Sie die Geometrie des inneren.  
  
 `pOpacityBrush`  
 Die anzuwendende der Geometrie Deckkraftmaske; NULL für keine Deckkraftmaske. Wenn eine Deckkraftmaske (der OpacityBrush-Parameter) angegeben wird, muss Pinsel ein ID2D1BitmapBrush, die ihren x- und y-erweitern Modi D2D1_EXTEND_MODE_CLAMP festgelegt wurde. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
##  <a name="fillmesh"></a>  CRenderTarget::FillMesh  
 Zeichnet das Innere des angegebenen Netzes.  
  
```  
void FillMesh(
    CD2DMesh* pMesh,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `pMesh`  
 Das Netz Paint-Ereignis.  
  
 `pBrush`  
 Der Pinsel, der zum Zeichnen des Netzes verwendet wird.  
  
##  <a name="fillopacitymask"></a>  CRenderTarget::FillOpacityMask  
 Wendet die Deckkraftmaske, die durch die angegebene Bitmap in einen Pinsel beschrieben, und verwendet diesen Pinsel, um einen Bereich des Renderziels zeichnen.  
  
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
 Die Position und die Radius in geräteunabhängige Pixel, der zu zeichnenden Ellipse.  
  
 `pBrush`  
 Der Pinsel, der zum Zeichnen der Region des Renderziels von DestinationRectangle angegebenen verwendet wird.  
  
 `content`  
 Der Typ des Inhalts der Deckkraftmaske enthält. Der Wert wird verwendet, um den Farbraum zu bestimmen, in dem die Deckkraftmaske gemischt wird.  
  
 `rectDest`  
 Die Region, der das Renderziel in geräteunabhängigen Pixeln gezeichnet werden soll.  
  
 `rectSrc`  
 Der Bereich der Bitmap für die Verwendung als Deckkraftmaske in geräteunabhängigen Pixeln.  
  
##  <a name="fillrectangle"></a>  CRenderTarget::FillRectangle  
 Zeichnet das Innere des angegebenen Rechtecks.  
  
```  
void FillRectangle(
    const CD2DRectF& rect,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `rect`  
 Die Dimension des Rechtecks in geräteunabhängigen Pixeln gezeichnet werden soll.  
  
 `pBrush`  
 Der Pinsel, der zum Zeichnen des Rechtecks verwendet wird, das Innere des.  
  
##  <a name="fillroundedrectangle"></a>  CRenderTarget::FillRoundedRectangle  
 Zeichnet das Innere des angegebenen abgerundeten Rechtecks.  
  
```  
void FillRoundedRectangle(
    const CD2DRoundedRect& rectRounded,  
    CD2DBrush* pBrush);
```  
  
### <a name="parameters"></a>Parameter  
 `rectRounded`  
 Die Dimensionen des abgerundeten Rechtecks Zeichnen in geräteunabhängigen Pixeln.  
  
 `pBrush`  
 Der Pinsel, der zum Zeichnen des Innere des abgerundeten Rechtecks verwendet wird.  
  
##  <a name="flush"></a>  CRenderTarget::Flush  
 Führt alle ausstehenden zeichnen-Befehle.  
  
```  
void Flush(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `tag1`  
 Enthält das Tag für das Zeichnen von Vorgängen, die Fehler oder 0 verursacht werden, wenn keine Fehler auftraten. Dieser Parameter wird nicht initialisiert übergeben.  
  
 `tag2`  
 Enthält das Tag für das Zeichnen von Vorgängen, die Fehler oder 0 verursacht werden, wenn keine Fehler auftraten. Dieser Parameter wird nicht initialisiert übergeben.  
  
##  <a name="getantialiasmode"></a>  CRenderTarget::GetAntialiasMode  
 Ruft den aktuellen Antialiasingmodus für Nichttext Zeichenvorgänge ab.  
  
```  
D2D1_ANTIALIAS_MODE GetAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Antialiasingmodus für Nichttext-Zeichenvorgänge.  
  
##  <a name="getdpi"></a>  CRenderTarget::GetDpi  
 Gibt das Rendern des Ziels Punkte pro Zoll (DPI)  
  
```  
CD2DSizeF GetDpi() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Renderziel Punkte pro Zoll (DPI).  
  
##  <a name="getmaximumbitmapsize"></a>  CRenderTarget::GetMaximumBitmapSize  
 Ruft die maximale Größe in geräteabhängige Einheiten (in Pixel), einer durch das Renderziel unterstützt eine Bitmap-Dimension  
  
```  
UINT32 GetMaximumBitmapSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Größe in Pixel, einer durch das Renderziel unterstützt eine Bitmap-Dimension  
  
##  <a name="getpixelformat"></a>  CRenderTarget::GetPixelFormat  
 Ruft das Pixelformat Format und Alpha des Renderziels ab  
  
```  
D2D1_PIXEL_FORMAT GetPixelFormat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Pixel-Format und Alpha-Modus des Renderziels  
  
##  <a name="getpixelsize"></a>  CRenderTarget::GetPixelSize  
 Gibt die Größe des Renderziels in Pixeln  
  
```  
CD2DSizeU GetPixelSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Renderziels in Pixeln  
  
##  <a name="getrendertarget"></a>  CRenderTarget::GetRenderTarget  
 Gibt die ID2D1RenderTarget-Schnittstelle  
  
```  
ID2D1RenderTarget* GetRenderTarget();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1RenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="getsize"></a>  CRenderTarget::GetSize  
 Gibt die Größe des Renderingziels in geräteunabhängigen Pixeln  
  
```  
CD2DSizeF GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Größe des Renderingziels in geräteunabhängigen Pixeln  
  
##  <a name="gettags"></a>  CRenderTarget::GetTags  
 Ruft die Bezeichnung für nachfolgende Zeichenvorgänge ab.  
  
```  
void GetTags(
    D2D1_TAG* tag1 = NULL,  
    D2D1_TAG* tag2 = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `tag1`  
 Enthält die erste Bezeichnung für nachfolgende Zeichenvorgänge an. Dieser Parameter wird nicht initialisiert übergeben. Wenn NULL angegeben ist, wird kein Wert für diesen Parameter abgerufen werden.  
  
 `tag2`  
 Enthält die zweite Bezeichnung für nachfolgende Zeichenvorgänge. Dieser Parameter wird nicht initialisiert übergeben. Wenn NULL angegeben ist, wird kein Wert für diesen Parameter abgerufen werden.  
  
##  <a name="gettextantialiasmode"></a>  CRenderTarget::GetTextAntialiasMode  
 Ruft den aktuellen Antialiasingmodus für Text und Symbol Zeichenvorgänge ab.  
  
```  
D2D1_TEXT_ANTIALIAS_MODE GetTextAntialiasMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Antialiasingmodus für Text und Symbol Zeichenvorgänge.  
  
##  <a name="gettextrenderingparams"></a>  CRenderTarget::GetTextRenderingParams  
 Ruft das Renderziel aktuellen Text-Rendering-Optionen ab.  
  
```  
void GetTextRenderingParams(IDWriteRenderingParams** textRenderingParams);
```  
  
### <a name="parameters"></a>Parameter  
 `textRenderingParams`  
 Wenn diese Methode zurückgibt, enthält die Adresse eines Zeigers auf das Renderziel textRenderingParams die aktuelle Textrenderingoptionen.  
  
##  <a name="gettransform"></a>  CRenderTarget::GetTransform  
 Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation an. Alle nachfolgenden Zeichenvorgänge treten in den transformierten Speicherplatz.  
  
```  
void GetTransform(D2D1_MATRIX_3X2_F* transform);
```  
  
### <a name="parameters"></a>Parameter  
 `transform`  
 Die Transformation für das Renderziel gelten.  
  
##  <a name="issupported"></a>  CRenderTarget::IsSupported  
 Gibt an, ob das Renderziel die angegebenen Eigenschaften unterstützt.  
  
```  
BOOL IsSupported(const D2D1_RENDER_TARGET_PROPERTIES& renderTargetProperties) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `renderTargetProperties`  
 So testen Sie die Render-Zieleigenschaften  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Zieleigenschaften für den angegebenen Rendern von diesem Renderziel unterstützt werden. andernfalls "false"  
  
##  <a name="isvalid"></a>  CRenderTarget::IsValid  
 Die Ressource Gültigkeit überprüft  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 True, wenn die Ressource gültig ist. andernfalls "false".  
  
##  <a name="m_lstresources"></a>  CRenderTarget::m_lstResources  
 Eine Liste von Zeigern auf CD2DResource-Objekte.  
  
```  
CObList m_lstResources;  
```  
  
##  <a name="m_prendertarget"></a>  CRenderTarget::m_pRenderTarget  
 Ein Zeiger auf ein ID2D1RenderTarget-Objekt.  
  
```  
ID2D1RenderTarget* m_pRenderTarget;  
```  
  
##  <a name="m_ptextformatdefault"></a>  CRenderTarget::m_pTextFormatDefault  
 Ein Zeiger auf CD2DTextFormat-Objekt, das Standardformat Text enthält.  
  
```  
CD2DTextFormat* m_pTextFormatDefault;  
```  
  
##  <a name="operator_id2d1rendertarget_star"></a>  CRenderTarget::operator ID2D1RenderTarget *  
 Gibt die ID2D1RenderTarget-Schnittstelle  
  
```  
operator ID2D1RenderTarget*();
```   
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine ID2D1RenderTarget-Schnittstelle oder NULL, wenn das Objekt noch nicht initialisiert ist.  
  
##  <a name="popaxisalignedclip"></a>  CRenderTarget::PopAxisAlignedClip  
 Entfernt die letzten Achsen ausgerichtete Clip aus das Renderziel. Nachdem diese Methode aufgerufen wird, wird der Clip nicht mehr auf nachfolgende Zeichenvorgänge angewendet.  
  
```  
void PopAxisAlignedClip();
```  
  
##  <a name="poplayer"></a>  CRenderTarget::PopLayer  
 Rufen Sie beendet die Umleitung der Zeichenvorgänge auf die Ebene, die vom letzten PushLayer angegeben ist.  
  
```  
void PopLayer();
```  
  
##  <a name="pushaxisalignedclip"></a>  CRenderTarget::PushAxisAlignedClip  
 Entfernt die letzten Achsen ausgerichtete Clip aus das Renderziel. Nachdem diese Methode aufgerufen wird, wird der Clip nicht mehr auf nachfolgende Zeichenvorgänge angewendet.  
  
```  
void PushAxisAlignedClip(
    const CD2DRectF& rectClip,  
    D2D1_ANTIALIAS_MODE mode = D2D1_ANTIALIAS_MODE_PER_PRIMITIVE);
```  
  
### <a name="parameters"></a>Parameter  
 `rectClip`  
 Die Größe und Position des Clippingbereichs, in geräteunabhängigen Pixeln.  
  
 `mode`  
 Die Antialiasingmodus, der verwendet wird, um die Ränder von Clip Rects zu zeichnen, die über Subpixelgrenzen verfügen und Clip mit dem Szeneninhalt blend. Die Mischung wird ausgeführt, sobald bei die PopAxisAlignedClip-Methode wird aufgerufen, und nicht für jeden Primitiv innerhalb der Schicht gilt.  
  
##  <a name="pushlayer"></a>  CRenderTarget::PushLayer  
 Fügt die angegebene Ebene im Renderziel, so, dass er alle nachfolgenden Zeichenvorgänge erhält, bis PopLayer aufgerufen wird.  
  
```  
void PushLayer(
    const D2D1_LAYER_PARAMETERS& layerParameters,  
    CD2DLayer& layer);
```  
  
### <a name="parameters"></a>Parameter  
 `layerParameters`  
 Der Inhalt Grenzen, geometrische Maske Deckkraft, Deckkraftmaske und Antialiasingoptionen für die Ebene.  
  
 `layer`  
 Die Ebene, die nachfolgende Zeichenvorgänge empfängt.  
  
##  <a name="restoredrawingstate"></a>  CRenderTarget::RestoreDrawingState  
 Legt das Renderziel zeichnen-Status auf, die von der angegebenen ID2D1DrawingStateBlock fest.  
  
```  
void RestoreDrawingState(ID2D1DrawingStateBlock& drawingStateBlock);
```  
  
### <a name="parameters"></a>Parameter  
 `drawingStateBlock`  
 Der neue zeichnen Zustand des Renderziels.  
  
##  <a name="savedrawingstate"></a>  CRenderTarget::SaveDrawingState  
 Speichert den aktuellen Status des zeichnen an angegebenen ID2D1DrawingStateBlock.  
  
```  
void SaveDrawingState(ID2D1DrawingStateBlock& drawingStateBlock) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `drawingStateBlock`  
 Bei der Rückgabe dieser Methode enthält die aktuellen zeichnen Zustand des Renderziels. Dieser Parameter muss vor der Übergabe an die Methode initialisiert werden.  
  
##  <a name="setantialiasmode"></a>  CRenderTarget::SetAntialiasMode  
 Legt die Antialiasingmodus des Renderziels fest. Die Antialiasingmodus gilt für alle nachfolgenden Zeichenvorgänge, Text und Symbol Zeichenvorgänge ausschließen.  
  
```  
void SetAntialiasMode(D2D1_ANTIALIAS_MODE antialiasMode);
```  
  
### <a name="parameters"></a>Parameter  
 `antialiasMode`  
 Für zukünftige Zeichenvorgänge Antialiasingmodus.  
  
##  <a name="setdpi"></a>  CRenderTarget::SetDpi  
 Legt die Punkte pro Zoll (DPI) des Renderziels fest.  
  
```  
void SetDpi(const CD2DSizeF& sizeDPI);
```  
  
### <a name="parameters"></a>Parameter  
 `sizeDPI`  
 Ein Wert größer als oder gleich 0 (null), der die horizontale/VerticalDPI des Renderziels angibt.  
  
##  <a name="settags"></a>  CRenderTarget::SetTags  
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
  
##  <a name="settextantialiasmode"></a>  CRenderTarget::SetTextAntialiasMode  
 Gibt den Antialiasingmodus für nachfolgende Text und Symbol Zeichenvorgänge verwendet.  
  
```  
void SetTextAntialiasMode(D2D1_TEXT_ANTIALIAS_MODE textAntialiasMode);
```  
  
### <a name="parameters"></a>Parameter  
 `textAntialiasMode`  
 Die Antialiasingmodus für nachfolgende Text und Symbol Zeichenvorgänge verwendet.  
  
##  <a name="settextrenderingparams"></a>  CRenderTarget::SetTextRenderingParams  
 Gibt Textrenderingoptionen auf alle nachfolgenden Text und Symbol Zeichenvorgänge angewendet werden soll.  
  
```  
void SetTextRenderingParams(IDWriteRenderingParams* textRenderingParams = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `textRenderingParams`  
 Die Text-Rendering-Optionen auf alle nachfolgenden Text und Symbol Zeichenvorgänge angewendet werden soll; NULL, um die aktuellen Textrenderingoptionen deaktivieren.  
  
##  <a name="settransform"></a>  CRenderTarget::SetTransform  
 Wendet die angegebene Transformation auf das Renderingziel ersetzt die vorhandene Transformation an. Alle nachfolgenden Zeichenvorgänge treten in den transformierten Speicherplatz.  
  
```  
void SetTransform(const D2D1_MATRIX_3X2_F* transform);  
void SetTransform(const D2D1_MATRIX_3X2_F& transform);
```  
  
### <a name="parameters"></a>Parameter  
 `transform`  
 Die Transformation für das Renderziel gelten.  
  
##  <a name="verifyresource"></a>  CRenderTarget::VerifyResource  
 Überprüft die Gültigkeit der CD2DResource-Objekt. das Objekt erstellt, wenn er noch nicht vorhanden ist.  
  
```  
BOOL VerifyResource(CD2DResource* pResource);
```  
  
### <a name="parameters"></a>Parameter  
 `pResource`  
 Zeiger auf CD2DResource-Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 "True" ist Objekt, sofern diese gültig ist. andernfalls "false".  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)
