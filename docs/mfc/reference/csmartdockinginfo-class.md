---
title: CSmartDockingInfo-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: 653be2fb1847403436bccb86807da382ef09cc25
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018209"
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
|[CSmartDockingInfo::CopyTo](#copyto)|Kopiert die aktuellen smart docking-Info-Parameter in die bereitgestellte [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) Objekt.|  
  
### <a name="data-members"></a>Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|Gibt an, ob das aktuelle Farbdesign verwendet wird, wenn das Framework intelligente andockmarker angezeigt wird.|  
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|Gibt die Basis Hintergrundfarbe von intelligenten andockmarkern.|  
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|Gibt die Farbe, die ersetzt `m_clrToneSrc` in smart Andocken Marker-Bitmaps.|  
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|Gibt die Farbe von intelligenten Andocken Marker-Bitmaps.|  
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|Gibt die Farbe des smart Andocken Marker Bitmaps, wenn sie transparent sind.|  
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|Gibt den Offset der zentrale Gruppe von intelligenten andockmarkern über die Grenzen des Rechtecks zentrale Gruppe.|  
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|Gibt die Gesamtgröße aller intelligente andockmarker in einer Gruppe an.|  
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Definiert die Ressourcen-IDs der Bitmaps, die das Framework für intelligente andockmarker verwendet wird, die nicht hervorgehoben werden.|  
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Definiert die Ressourcen-IDs der Bitmaps, die das Framework für intelligente andockmarker verwendet wird, die hervorgehoben werden.|  
  
## <a name="remarks"></a>Hinweise  
 Das Framework behandelt den intelligenten andockmarkern intern. Die folgende Abbildung zeigt die standardmäßige intelligente andockmarker:  
  
 ![Standardmarker für intelligentes Andocken](../../mfc/reference/media/nextsdmarkers.png "Nextsdmarkers")  
  
 In dieser Abbildung zeigt das Bild auf der linken Seite einen zentrale Gruppe intelligente Andocken Marker, der keinen Andocken zu einer Registerkarte aktiviert. Das Bild in der Mitte zeigt einen rechten Rand intelligente docking-Marker. Das Bild auf der rechten Seite zeigt einen zentrale Gruppe intelligente Andocken Marker, der besitzt Andocken zu einer Registerkarte aktiviert. Der zentrale Gruppe-smart-docking-Marker ist einer wichtigsten Bitmap und fünf intelligente Andocken Marker-Bitmaps.  
  
 Sie können die folgenden Parameter von intelligenten andockmarkern anpassen:  
  
-   Farbe Beispielsweise können Sie die blaue Farbe der Marker in der Abbildung durch eine beliebige benutzerdefinierte Farbe ersetzen.  
  
-   Der Transparenzfarbe.  
  
-   Offset der eine intelligente docking-Marker in der die zentrale Gruppe dem linken Rand des umschließenden Rechtecks.  
  
-   Die main-Bitmap, die die zentrale Gruppe darstellt.  
  
-   Die Bitmaps, die den regulären und hervorgehoben, intelligente andockmarker darstellt.  
  
 Die folgende Abbildung zeigt ein Beispiel von intelligenten andockmarkern, die angepasst wurden:  
  
 ![Benutzerdefinierte Marker für intelligentes Andocken](../../mfc/reference/media/nextsdmarkerscustom.png "Nextsdmarkerscustom")  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDockingManager.h  
  
##  <a name="copyto"></a>  CSmartDockingInfo::CopyTo  
 Kopiert die aktuellen smart-docking-Parameter in die bereitgestellte [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) Objekt.  
  
```  
void CopyTo(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Parameter  
*params*<br/>
[out] Ein Objekt des Typs `CSmartDockingInfo` , die mit den aktuellen smart-docking-Parametern aufgefüllt wird.  
  
##  <a name="m_busethemecolorinshading"></a>  CSmartDockingInfo::m_bUseThemeColorInShading  
 Gibt an, ob das aktuelle Farbdesign verwendet wird, wenn das Framework intelligente andockmarker angezeigt wird.  
  
```  
BOOL m_bUseThemeColorInShading;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn "true", die Marker mit der aktuellen Designfarbe gezeichnet werden; Andernfalls werden die Marker mit blauen helle Farbe gezeichnet.  
  
 Der Standardwert ist "false".  
  
##  <a name="m_clrbasebackground"></a>  CSmartDockingInfo::m_clrBaseBackground  
 Gibt die Basis Hintergrundfarbe von intelligenten andockmarkern.  
  
```  
COLORREF m_clrBaseBackground;  
```  
  
##  <a name="m_clrtonedest"></a>  CSmartDockingInfo::m_clrToneDest  
 Gibt die Farbe, die ersetzt `m_clrToneSrc` in smart Andocken Marker-Bitmaps.  
  
```  
COLORREF m_clrToneDest;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert, der die Farbe der Marker Bitmaps programmgesteuert zu ändern. Z. B. Wenn Sie die Farbe der Marker aus mit dem Framework bereitgestellten standard ändern möchten, legen Sie diesen Wert auf die gewünschte Farbe. In der Standardeinstellung [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) auf RGB ("61", "123", "241") festgelegt ist (eine bläuliches Farbe).  
  
 Um die Farbe des benutzerdefinierten Marker zu ändern, müssen Sie angeben, beide `m_clrToneDest` und `m_clrToneSrc`.  
  
##  <a name="m_clrtonesrc"></a>  CSmartDockingInfo::m_clrToneSrc  
 Gibt die Farbe von intelligenten Andocken Marker-Bitmaps.  
  
```  
COLORREF m_clrToneSrc;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert nur, wenn Sie die Farbe der eine benutzerdefinierte Bitmap mit einer anderen Farbe ersetzen möchten. Sie müssen keine dieser Wert festgelegt, wenn Sie die Farbe der Standard (Framework bereitgestellten) ändern Marker.  
  
 Verwendung `(COLORREF)-1` , ein Mitglied der Gruppe "smart andocken" leer lassen.  
  
##  <a name="m_clrtransparent"></a>  CSmartDockingInfo::m_clrTransparent  
 Gibt die Farbe des smart Andocken Marker Bitmaps, wenn sie transparent sind.  
  
```  
COLORREF m_clrTransparent;  
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen diesen Wert festlegen, wenn Sie benutzerdefinierte Markierungen und benutzerdefinierte Bitmaps in der Andock-Gruppe anzeigen.  
  
##  <a name="m_ncentralgroupoffset"></a>  CSmartDockingInfo::m_nCentralGroupOffset  
 Gibt den Offset zwischen der zentrale Gruppe von intelligenten andockmarkern und die Grenzen des Rechtecks zentrale Gruppe.  
  
```  
int m_nCentralGroupOffset;  
```  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie diesen Wert, wenn Sie den Standardoffset zwischen benutzerdefinierten Marker und die Grenzen der zentrale Gruppe von intelligenten andockmarkern ändern möchten. Der Standardwert beträgt 5 Pixel.  
  
##  <a name="m_sizetotal"></a>  CSmartDockingInfo::m_sizeTotal  
 Gibt die Gesamtgröße der ein umschließendes Rechteck, das Sie in der zentralen Gruppe alle intelligente andockmarkern enthält.  
  
```  
CSize m_sizeTotal;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie `m_sizeTotal` auf die Größe des umschließenden Rechtecks des Markers zentrale Gruppe. Sie müssen diesen Wert angeben, wenn Sie benutzerdefinierte Bitmaps für Marker verwenden.  
  
##  <a name="m_uimarkerbmpresid"></a>  CSmartDockingInfo::m_uiMarkerBmpResID  
 Definiert die Ressourcen-IDs der Bitmaps, die für die nicht hervorgehobenen benutzerdefinierte intelligente andockmarker verwendet werden.  
  
```  
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Hinweise  
 Füllen Sie dieses Array ab, mit der Ressourcen-IDs der Bitmaps, die die intelligenten andockmarkern darstellt. AFX_SD_MARKERS_NUM ist derzeit 5 definiert. Sie füllen das Array wie folgt aus:  
  
```cpp
params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;
params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;
params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;
params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;
params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;
```
  
##  <a name="m_uimarkerlightbmpresid"></a>  CSmartDockingInfo::m_uiMarkerLightBmpResID  
 Definiert die Ressourcen-IDs der Bitmaps, die für hervorgehobene benutzerdefinierte intelligente andockmarker verwendet werden.  
  
```  
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Hinweise  
 Füllen Sie dieses Array ab, mit der Ressourcen-IDs der Bitmaps, die das hervorgehobene intelligente andockmarker darstellt. AFX_SD_MARKERS_NUM ist derzeit 5 definiert. Sie füllen das Array wie folgt aus:  
  
```cpp
params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;
params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;
params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;
params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;
params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;
```
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)
