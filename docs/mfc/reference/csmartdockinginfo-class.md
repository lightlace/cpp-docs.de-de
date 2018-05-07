---
title: CSmartDockingInfo Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo
- AFXDOCKINGMANAGER/CSmartDockingInfo::CopyTo
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_bUseThemeColorInShading
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrBaseBackground
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneDest
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrToneSrc
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_clrTransparent
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_nCentralGroupOffset
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_sizeTotal
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerBmpResID
- AFXDOCKINGMANAGER/CSmartDockingInfo::m_uiMarkerLightBmpResID
dev_langs:
- C++
helpviewer_keywords:
- CSmartDockingInfo [MFC], CopyTo
- CSmartDockingInfo [MFC], m_bUseThemeColorInShading
- CSmartDockingInfo [MFC], m_clrBaseBackground
- CSmartDockingInfo [MFC], m_clrToneDest
- CSmartDockingInfo [MFC], m_clrToneSrc
- CSmartDockingInfo [MFC], m_clrTransparent
- CSmartDockingInfo [MFC], m_nCentralGroupOffset
- CSmartDockingInfo [MFC], m_sizeTotal
- CSmartDockingInfo [MFC], m_uiMarkerBmpResID
- CSmartDockingInfo [MFC], m_uiMarkerLightBmpResID
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3328eacb9789b892a271208193e82546eb73f7e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="csmartdockinginfo-class"></a>CSmartDockingInfo-Klasse
Definiert die Darstellung von intelligenten Andockmarkern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CSmartDockingInfo::CSmartDockingInfo`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSmartDockingInfo::CopyTo](#copyto)|Kopiert die aktuellen smart Andock-Info-Parameter in der bereitgestellten [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) Objekt.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|Gibt an, ob der aktuelle Farbdesign verwenden, wenn vom Framework intelligente andockmarkern angezeigt wird.|  
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|Gibt die Basis Hintergrundfarbe von intelligenten andockmarkern.|  
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|Gibt die Farbe, die ersetzt `m_clrToneSrc` in intelligenten andockbaren Marker-Bitmaps.|  
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|Gibt die Farbe des intelligenten andockbaren Marker Bitmaps.|  
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|Gibt die Farbe des intelligenten andockbaren Marker Bitmaps, werden transparent.|  
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|Gibt den Offset der zentralen Gruppe von intelligenten andockmarkern aus den Grenzen des Rechtecks zentrale-Gruppe.|  
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|Gibt die Gesamtgröße aller intelligenten andockmarkern in einer Gruppe an.|  
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Definiert die Ressourcen-IDs für die Bitmap, die das Framework für den intelligenten andockmarkern verwendet, die nicht hervorgehoben sind.|  
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Definiert die Ressourcen-IDs für die Bitmap, die das Framework für den intelligenten andockmarkern verwendet, die hervorgehoben werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die Framework-Handles für intelligente andockmarkern intern. Die folgende Abbildung zeigt die standardmäßigen intelligenten andockmarkern:  
  
 ![Standardmarker für intelligentes Andocken](../../mfc/reference/media/nextsdmarkers.png "Nextsdmarkers")  
  
 In dieser Abbildung zeigt das Bild auf der linken Seite einen zentrale Gruppe intelligenten andockbaren Marker, der keine Zuordnung zu einer Registerkarte aktiviert. Das Bild in der Mitte zeigt einen rechten Rand intelligenten Andock-Marker. Das Bild auf der rechten Seite zeigt einen zentrale Gruppe intelligenten andockbaren Marker, der zu einer Registerkarte aktiviert Andocken verfügt. Zentrale Gruppe intelligenten andockbaren Marker hat eine main Bitmap und fünf smart-docking Marker Bitmaps.  
  
 Sie können die folgenden Parameter von intelligenten andockmarkern anpassen:  
  
-   Farbe Beispielsweise können Sie die blaue Farbe der Marker in der Abbildung durch jede benutzerdefinierte Farbe ersetzen.  
  
-   Der Transparenzfarbe.  
  
-   Offset der eine intelligente andockbaren Marker in der zentrale Gruppe über den Rahmen des umschließenden Rechtecks.  
  
-   Die wichtigsten Bitmap, die die zentralen Gruppe darstellt.  
  
-   Die Bitmaps, die den regulären und hervorgehobenen intelligenten andockmarkern darstellt.  
  
 Die folgende Abbildung zeigt ein Beispiel von intelligenten andockmarkern, die angepasst wurden:  
  
 ![Benutzerdefinierte Marker für intelligentes Andocken](../../mfc/reference/media/nextsdmarkerscustom.png "Nextsdmarkerscustom")  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDockingManager.h  
  
##  <a name="copyto"></a>  CSmartDockingInfo::CopyTo  
 Kopiert die aktuellen smart-docking-Parameter in der bereitgestellten [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) Objekt.  
  
```  
void CopyTo(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `params`  
 Ein Objekt des Typs `CSmartDockingInfo` , die mit den aktuellen smart andockbaren Parametern aufgefüllt wird.  
  
##  <a name="m_busethemecolorinshading"></a>  CSmartDockingInfo::m_bUseThemeColorInShading  
 Gibt an, ob der aktuelle Farbdesign verwenden, wenn vom Framework intelligente andockmarkern angezeigt wird.  
  
```  
BOOL m_bUseThemeColorInShading;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, Marker im aktuellen Farbdesign gezeichnet werden; andernfalls werden die Marker mit einem hellblau gezeichnet.  
  
 Der Standardwert ist `FALSE`.  
  
##  <a name="m_clrbasebackground"></a>  CSmartDockingInfo::m_clrBaseBackground  
 Gibt die Basis Hintergrundfarbe von intelligenten andockmarkern.  
  
```  
COLORREF m_clrBaseBackground;  
```  
  
##  <a name="m_clrtonedest"></a>  CSmartDockingInfo::m_clrToneDest  
 Gibt die Farbe, die ersetzt werden `m_clrToneSrc` in intelligenten andockbaren Marker-Bitmaps.  
  
```  
COLORREF m_clrToneDest;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert, um die Farbe der Marker Quellbitmaps programmgesteuert zu ändern. Wenn Sie die Farbe der Marker aus mit dem Framework bereitgestellten standard ändern möchten, legen Sie diesen Wert auf die gewünschte Farbe fest. Standardmäßig [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) auf RGB (61, 123, 241) festgelegt ist (eine bläuliches Farbe).  
  
 Um die Farbe des benutzerdefinierten Marker zu ändern, müssen Sie beide angeben `m_clrToneDest` und `m_clrToneSrc`.  
  
##  <a name="m_clrtonesrc"></a>  CSmartDockingInfo::m_clrToneSrc  
 Gibt die Farbe des intelligenten andockbaren Marker Bitmaps.  
  
```  
COLORREF m_clrToneSrc;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert nur, wenn Sie die Farbe einer benutzerdefinierten Bitmap durch eine andere Farbe ersetzen möchten. Sie müssen nicht dieser Wert festgelegt, wenn Sie die Farbe eines Standards (Framework bereitgestellten) ändern Marker.  
  
 Verwendung `(COLORREF)-1` , um ein Mitglied der Gruppe "intelligentes Andocken" leer lassen.  
  
##  <a name="m_clrtransparent"></a>  CSmartDockingInfo::m_clrTransparent  
 Gibt die Farbe des intelligenten andockbaren Marker Bitmaps, werden transparent.  
  
```  
COLORREF m_clrTransparent;  
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen diesen Wert festlegen, wenn Sie benutzerdefinierte Marker und benutzerdefinierte Bitmaps in der Gruppe "andocken" anzeigen.  
  
##  <a name="m_ncentralgroupoffset"></a>  CSmartDockingInfo::m_nCentralGroupOffset  
 Gibt den Offset zwischen der zentrale Gruppe von intelligenten andockmarkern und die Grenzen des Rechtecks zentrale-Gruppe.  
  
```  
int m_nCentralGroupOffset;  
```  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie diesen Wert, wenn Sie den Standardoffset zwischen benutzerdefinierten Marker und die Grenzen der zentralen Gruppe von intelligenten andockmarkern ändern möchten. Der Standardwert beträgt 5 Pixel.  
  
##  <a name="m_sizetotal"></a>  CSmartDockingInfo::m_sizeTotal  
 Gibt die Gesamtgröße der eine umschließende Rechteck zurück alle intelligente andockmarkern in der zentrale Gruppe an.  
  
```  
CSize m_sizeTotal;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie `m_sizeTotal` auf die Größe des umschließenden Rechtecks des Markers zentrale-Gruppe. Sie müssen diesen Wert angeben, bei Verwendung von benutzerdefinierten Bitmaps für Marker.  
  
##  <a name="m_uimarkerbmpresid"></a>  CSmartDockingInfo::m_uiMarkerBmpResID  
 Definiert die Ressourcen-IDs für die Bitmap, die für nicht hervorgehoben benutzerdefinierte intelligenten andockmarkern verwendet werden.  
  
```  
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Hinweise  
 Füllen Sie dieses Array mit den Ressourcen-IDs für die Bitmap, die die intelligenten andockmarkern darstellt. `AFX_SD_MARKERS_NUM` als 5 ist derzeit definiert werden. Sie Füllen des Arrays wie folgt aus:  
  
 `params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;`  
  
 `params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;`  
  
 `params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;`  
  
 `params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;`  
  
 `params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;`  
  
##  <a name="m_uimarkerlightbmpresid"></a>  CSmartDockingInfo::m_uiMarkerLightBmpResID  
 Definiert die Ressourcen-IDs für die Bitmap, die für hervorgehobene benutzerdefinierte intelligenten andockmarkern verwendet werden.  
  
```  
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Hinweise  
 Füllen Sie dieses Array mit den Ressourcen-IDs für die Bitmap, die das hervorgehobenen intelligenten andockmarkern darstellt. `AFX_SD_MARKERS_NUM` als 5 ist derzeit definiert werden. Sie Füllen des Arrays wie folgt aus:  
  
 `params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;`  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)
