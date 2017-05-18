---
title: Klasse CSmartDockingInfo | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CSmartDockingInfo class
ms.assetid: cab04f38-4bc1-4378-9337-c56fc87fbd68
caps.latest.revision: 27
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 9ae735b202299d26b98ec763f65c3f8772d9b914
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="csmartdockinginfo-class"></a>CSmartDockingInfo-Klasse
Definiert die Darstellung von intelligenten Andockmarkern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CSmartDockingInfo : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CSmartDockingInfo::CSmartDockingInfo`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSmartDockingInfo::CopyTo](#copyto)|Kopiert die aktuellen smart docking-Info-Parameter in der bereitgestellten [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) Objekt.|  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSmartDockingInfo::m_bUseThemeColorInShading](#m_busethemecolorinshading)|Gibt an, ob die aktuelle Designfarbe verwenden, wenn vom Framework intelligente andockmarkern angezeigt wird.|  
|[CSmartDockingInfo::m_clrBaseBackground](#m_clrbasebackground)|Gibt die Basis Hintergrundfarbe von intelligenten andockmarkern.|  
|[CSmartDockingInfo::m_clrToneDest](#m_clrtonedest)|Gibt die Farbe, die ersetzt `m_clrToneSrc` in smart docking Marke Bitmaps.|  
|[CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc)|Gibt die Farbe des intelligenten docking Marke Bitmaps.|  
|[CSmartDockingInfo::m_clrTransparent](#m_clrtransparent)|Gibt die Farbe des intelligenten docking Marke Bitmaps, werden transparent.|  
|[CSmartDockingInfo::m_nCentralGroupOffset](#m_ncentralgroupoffset)|Gibt den Offset der zentrale Gruppe von intelligenten andockmarkern innerhalb der Grenzen des Rechtecks zentrale Gruppe.|  
|[CSmartDockingInfo::m_sizeTotal](#m_sizetotal)|Gibt die Gesamtgröße aller intelligenten andockmarkern in einer Gruppe an.|  
|[CSmartDockingInfo::m_uiMarkerBmpResID](#m_uimarkerbmpresid)|Definiert die Ressourcen-IDs für die Bitmap, die das Framework für intelligenten andockmarkern verwendet, die nicht hervorgehoben sind.|  
|[CSmartDockingInfo::m_uiMarkerLightBmpResID](#m_uimarkerlightbmpresid)|Definiert die Ressourcen-IDs für die Bitmap, die das Framework für intelligenten andockmarkern verwendet, die hervorgehoben werden.|  
  
## <a name="remarks"></a>Hinweise  
 Die Framework-Handles intelligenten andockmarkern intern. Die folgende Abbildung zeigt die standardmäßige intelligente andockmarker:  
  
 ![Standardmarker für intelligentes Andocken](../../mfc/reference/media/nextsdmarkers.png "Nextsdmarkers")  
  
 In dieser Abbildung wird das Bild auf der linken Seite eine zentrale Gruppe smart docking Marke, die keine Zuordnung zu einer Registerkarte aktiviert. Das Bild in der Mitte zeigt einen rechten Rand smart docking-Marker. Das Bild rechts zeigt eine zentrale Gruppe smart docking Markierung, die zu einer Registerkarte aktiviert Andocken verfügt. Die zentrale Gruppe smart-docking Markierung hat eine main-Bitmap und fünf smart-docking Marke Bitmaps.  
  
 Sie können die folgenden Parameter von intelligenten andockmarkern anpassen:  
  
-   Farbe Beispielsweise können Sie die blaue Farbe der Marker in der Abbildung durch eine beliebige benutzerdefinierte Farbe ersetzen.  
  
-   Der Transparenzfarbe.  
  
-   Offset der eine intelligente docking Marke in die zentrale Gruppe dem linken Rand des umschließenden Rechtecks.  
  
-   Die Haupt-Bitmap, die die zentrale Gruppe darstellt.  
  
-   Die Bitmaps, die die regelmäßigen und hervorgehobenen intelligenten andockmarkern darstellt.  
  
 Die folgende Abbildung zeigt ein Beispiel von intelligenten andockmarkern, die angepasst wurden:  
  
 ![Benutzerdefinierte Marker für intelligentes Andocken](../../mfc/reference/media/nextsdmarkerscustom.png "Nextsdmarkerscustom")  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxDockingManager.h  
  
##  <a name="copyto"></a>CSmartDockingInfo::CopyTo  
 Kopiert die aktuellen smart-docking-Parameter in der bereitgestellten [CSmartDockingInfo](../../mfc/reference/csmartdockinginfo-class.md) Objekt.  
  
```  
void CopyTo(CSmartDockingInfo& params);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `params`  
 Ein Objekt vom Typ `CSmartDockingInfo` , die mit der aktuellen smart-docking-Parameter aufgefüllt.  
  
##  <a name="m_busethemecolorinshading"></a>CSmartDockingInfo::m_bUseThemeColorInShading  
 Gibt an, ob die aktuelle Designfarbe verwenden, wenn vom Framework intelligente andockmarkern angezeigt wird.  
  
```  
BOOL m_bUseThemeColorInShading;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `TRUE`, die Marker werden mit der aktuellen Designfarbe gezeichnet; andernfalls werden die Marker mit einem hellblau gezeichnet.  
  
 Der Standardwert ist `FALSE`.  
  
##  <a name="m_clrbasebackground"></a>CSmartDockingInfo::m_clrBaseBackground  
 Gibt die Basis Hintergrundfarbe von intelligenten andockmarkern.  
  
```  
COLORREF m_clrBaseBackground;  
```  
  
##  <a name="m_clrtonedest"></a>CSmartDockingInfo::m_clrToneDest  
 Gibt die Farbe, die ersetzt werden `m_clrToneSrc` in smart docking Marke Bitmaps.  
  
```  
COLORREF m_clrToneDest;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert, um die Farbe der Marker Bitmaps programmgesteuert zu ändern. Wenn Sie die Farbe der Marker aus mit dem Framework bereitgestellten standard ändern möchten, legen Sie diesen Wert auf die gewünschte Farbe fest. In der Standardeinstellung [CSmartDockingInfo::m_clrToneSrc](#m_clrtonesrc) in RGB (61, 123, 241) festgelegt ist (bläulich Farbe).  
  
 Um die Farbe des benutzerdefinierten Marker zu ändern, müssen Sie beide angeben `m_clrToneDest` und `m_clrToneSrc`.  
  
##  <a name="m_clrtonesrc"></a>CSmartDockingInfo::m_clrToneSrc  
 Gibt die Farbe des intelligenten docking Marke Bitmaps.  
  
```  
COLORREF m_clrToneSrc;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie diesen Wert nur, wenn Sie mit einer anderen Farbe die Farbe eine benutzerdefinierte Bitmap ersetzen möchten. Sie müssen keinen dieser Wert festgelegt, wenn Sie die Farbe eines Standards (Framework bereitgestellten) ändern Marker.  
  
 Verwendung `(COLORREF)-1` , ein Mitglied der intelligenten andockbaren Gruppe leer lassen.  
  
##  <a name="m_clrtransparent"></a>CSmartDockingInfo::m_clrTransparent  
 Gibt die Farbe des intelligenten docking Marke Bitmaps, werden transparent.  
  
```  
COLORREF m_clrTransparent;  
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert muss festgelegt werden, wenn Sie benutzerdefinierte Marker und benutzerdefinierte Bitmaps in der Dockingstation Gruppe anzeigen.  
  
##  <a name="m_ncentralgroupoffset"></a>CSmartDockingInfo::m_nCentralGroupOffset  
 Gibt den Offset zwischen der zentrale Gruppe von intelligenten andockmarkern und die Grenzen des Rechtecks zentrale Gruppe.  
  
```  
int m_nCentralGroupOffset;  
```  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie diesen Wert, wenn Sie die Standard-Abweichung zwischen benutzerdefinierte Marker und die Grenzen für die zentrale Gruppe von intelligenten andockmarkern ändern möchten. Der Standardwert beträgt 5 Pixel.  
  
##  <a name="m_sizetotal"></a>CSmartDockingInfo::m_sizeTotal  
 Gibt die Gesamtgröße des ein umschließendes Rechteck, das alle intelligente andockmarkern in der zentralen Gruppe einschließt.  
  
```  
CSize m_sizeTotal;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie `m_sizeTotal` auf die Größe des umschließenden Rechtecks des Balkens zentrale Gruppe. Sie müssen diesen Wert angeben, wenn Sie benutzerdefinierte Bitmaps für Marker verwenden.  
  
##  <a name="m_uimarkerbmpresid"></a>CSmartDockingInfo::m_uiMarkerBmpResID  
 Definiert die Ressourcen-IDs für die Bitmap, die für nicht hervorgehobenen benutzerdefinierte intelligenten andockmarkern verwendet werden.  
  
```  
UINT m_uiMarkerBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Hinweise  
 Füllen Sie dieses Array mit den Ressourcen-IDs für die Bitmap der intelligenten andockmarkern darstellt. `AFX_SD_MARKERS_NUM`als 5 ist derzeit definiert werden. Sie füllen das Array wie folgt:  
  
 `params.m_uiMarkerBmpResID[0] = IDB_MARKER_LEFT;`  
  
 `params.m_uiMarkerBmpResID[1] = IDB_MARKER_RIGHT;`  
  
 `params.m_uiMarkerBmpResID[2] = IDB_MARKER_TOP;`  
  
 `params.m_uiMarkerBmpResID[3] = IDB_MARKER_BOTTOM;`  
  
 `params.m_uiMarkerBmpResID[4] = IDB_MARKER_CENTER;`  
  
##  <a name="m_uimarkerlightbmpresid"></a>CSmartDockingInfo::m_uiMarkerLightBmpResID  
 Definiert die Ressourcen-IDs für die Bitmap, die für hervorgehobene benutzerdefinierte intelligenten andockmarkern verwendet werden.  
  
```  
UINT m_uiMarkerLightBmpResID[AFX_SD_MARKERS_NUM];  
```  
  
### <a name="remarks"></a>Hinweise  
 Füllen Sie dieses Array mit den Ressourcen-IDs für die Bitmap, die die hervorgehobenen intelligenten andockmarkern darstellt. `AFX_SD_MARKERS_NUM`als 5 ist derzeit definiert werden. Sie füllen das Array wie folgt:  
  
 `params.m_uiMarkerLightBmpResID[0] = IDB_MARKER_LEFT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[1] = IDB_MARKER_RIGHT_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[2] = IDB_MARKER_TOP_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[3] = IDB_MARKER_BOTTOM_LIGHT;`  
  
 `params.m_uiMarkerLightBmpResID[4] = IDB_MARKER_CENTER_LIGHT;`  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)

