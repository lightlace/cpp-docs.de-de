---
title: Klasse CMFCRibbonFontComboBox | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonFontComboBox
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonFontComboBox class
ms.assetid: 33b4db50-df4f-45fa-8f05-2e6e73c31435
caps.latest.revision: 24
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
ms.openlocfilehash: 851ef15013ca62012931fd92baf277d5db96033d
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonfontcombobox-class"></a>CMFCRibbonFontComboBox-Klasse
Implementiert ein Kombinationsfeld, das eine Liste von Schriftarten enthält. Das Kombinationsfeld kann in einem Menübandbereich platziert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonFontComboBox : public CMFCRibbonComboBox  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCRibbonFontComboBox::~CMFCRibbonFontComboBox`|Destruktor.|  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::CMFCRibbonFontComboBox](#cmfcribbonfontcombobox)|Erstellt und initialisiert ein `CMFCRibbonFontComboBox`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonFontComboBox::BuildFonts](#buildfonts)|Füllt das Schriftartkombinationsfeld für das Menüband mit Schriftarten des angegebenen Schriftarttyps, Zeichensatzes, der Zeichenbreite und Schriftfamilie auf.|  
|`CMFCRibbonFontComboBox::CreateObject`|Wird vom Framework verwendet, um eine dynamische Instanz dieses Klassentyps zu erstellen.|  
|[CMFCRibbonFontComboBox::GetCharSet](#getcharset)|Gibt den angegebenen Zeichensatz zurück.|  
|[CMFCRibbonFontComboBox::GetFontDesc](#getfontdesc)||  
|[CMFCRibbonFontComboBox::GetFontType](#getfonttype)|Gibt zurück, welche Schriftarttypen im Kombinationsfeld angezeigt werden. Gültige Optionen sind DEVICE_FONTTYPE, RASTER_FONTTYPE, und TRUETYPE_FONTTYPE oder jede bitweise Kombination davon.|  
|[CMFCRibbonFontComboBox::GetPitchAndFamily](#getpitchandfamily)|Gibt die Schriftbreite und Schriftfamilie der Schriftarten zurück, die im Kombinationsfeld angezeigt werden.|  
|`CMFCRibbonFontComboBox::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCRibbonFontComboBox::RebuildFonts](#rebuildfonts)|Füllt das Schriftartkombinationsfeld für das Menüband mit Schriftarten des zuvor angegebenen Schriftarttyps, Zeichensatzes, der Zeichenbreite und Schriftfamilie auf.|  
|[CMFCRibbonFontComboBox::SetFont](#setfont)|Wählt die angegebene Schriftart im Kombinationsfeld aus.|  
  
## <a name="remarks"></a>Hinweise  
 Nach der Erstellung einer `CMFCRibbonFontComboBox` Objekt, das durch Aufrufen von einem Menüband-Bereich hinzufügen [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
 [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonComboBox.h  
  
##  <a name="a-namebuildfontsa--cmfcribbonfontcomboboxbuildfonts"></a><a name="buildfonts"></a>CMFCRibbonFontComboBox::BuildFonts  
 Füllt das Kombinationsfeld auf der Multifunktionsleiste mit Schriftarten.  
  
```  
void BuildFonts(
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nFontType`  
 Gibt die Schriftart der Schriftarten hinzufügen.  
  
 [in] `nCharSet`  
 Gibt den Zeichensatz für die Schriftarten hinzufügen.  
  
 [in] `nPitchAndFamily`  
 Gibt die Zeichenbreite und Familie Schriftarten hinzufügen.  
  
##  <a name="a-namecmfcribbonfontcomboboxa--cmfcribbonfontcomboboxcmfcribbonfontcombobox"></a><a name="cmfcribbonfontcombobox"></a>CMFCRibbonFontComboBox::CMFCRibbonFontComboBox  
 Erstellt und initialisiert ein [CMFCRibbonFontComboBox](../../mfc/reference/cmfcribbonfontcombobox-class.md) Objekt.  
  
```  
CMFCRibbonFontComboBox(
    UINT nID,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BYTE nPitchAndFamily = DEFAULT_PITCH,  
    int nWidth = -1);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Die Befehls-ID des Befehls, der ausgeführt wird, wenn der Benutzer ein Element aus dem Kombinationsfeld auswählt.  
  
 [in] `nFontType`  
 Gibt an, welche Schriftart Typen im Kombinationsfeld angezeigt. Gültige Optionen sind **DEVICE_FONTTYPE**, **RASTER_FONTTYPE**, und **TRUETYPE_FONTTYPE**, oder einer bitweisen Kombination davon.  
  
 [in] `nCharSet`  
 Filtert die Schriftarten in das Kombinationsfeld auf die in den angegebenen Zeichensatz gehören.  
  
 [in] `nPitchAndFamily`  
 Gibt die Tonhöhe und die Familie der Schriftarten, die im Kombinationsfeld angezeigt werden.  
  
 [in] `nWidth`  
 Gibt die Breite des Kombinationsfelds in Pixel an.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu möglichen `nFontType` Parameterwerte finden Sie unter [EnumFontFamProc](http://msdn.microsoft.com/library/windows/desktop/dd162621) in der Windows SDK-Dokumentation.  
  
 Weitere Informationen zu gültigen Zeichensätzen, die zugewiesen werden können `nCharSet,` und gültigen Werten, die zugewiesen werden können `nPitchAndFamily`, finden Sie unter ["LogFont"](http://msdn.microsoft.com/library/windows/desktop/dd145037) in der Windows SDK-Dokumentation.  
  
##  <a name="a-namegetfontdesca--cmfcribbonfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>CMFCRibbonFontComboBox::GetFontDesc  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex = -1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namerebuildfontsa--cmfcribbonfontcomboboxrebuildfonts"></a><a name="rebuildfonts"></a>CMFCRibbonFontComboBox::RebuildFonts  
 Füllt das Kombinationsfeld auf der Multifunktionsleiste mit Schriftarten eines zuvor angegebenen Schriftart, Zeichensatz und Tonhöhe und Familie.  
  
```  
void RebuildFonts();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie können die Schriftart, den Zeichensatz angeben und die Zeichenbreite und Familie Schriftarten hinzufügen in das Menüband-Kombinationsfeld Schriftart im Dialogfeld die [Konstruktor](#cmfcribbonfontcombobox) für diese Klasse oder durch Aufrufen von [CMFCRibbonFontComboBox::BuildFonts](#buildfonts).  
  
##  <a name="a-namesetfonta--cmfcribbonfontcomboboxsetfont"></a><a name="setfont"></a>CMFCRibbonFontComboBox::SetFont  
 Wählt die angegebene Schriftart im Kombinationsfeld aus.  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    BOOL bExact = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Gibt den Namen der Schriftart auswählen.  
  
 `nCharSet`  
 Gibt den Zeichensatz für die ausgewählte Schriftart an.  
  
 `bExact`  
 `TRUE`um anzugeben, dass der Zeichensatz entsprechen muss, wenn Sie eine Schriftart auswählen; `FALSE` angeben, dass der Zeichensatz ignoriert werden, kann Wenn Sie eine Schriftart auswählen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die angegebene Schriftart gefunden und aktiviert wurde; andernfalls&0; (null).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetcharseta--cmfcribbonfontcomboboxgetcharset"></a><a name="getcharset"></a>CMFCRibbonFontComboBox::GetCharSet  
 Gibt den angegebenen Zeichensatz zurück.  
  
```  
BYTE GetCharSet() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeichensatz (siehe "LogFont" in der Windows SDK-Dokumentation).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetfonttypea--cmfcribbonfontcomboboxgetfonttype"></a><a name="getfonttype"></a>CMFCRibbonFontComboBox::GetFontType  
 Gibt zurück, welche Schriftarttypen im Kombinationsfeld angezeigt werden. Gültige Optionen sind DEVICE_FONTTYPE, RASTER_FONTTYPE, und TRUETYPE_FONTTYPE oder jede bitweise Kombination davon.  
  
```  
int GetFontType() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Schriftarttypen (Siehe EnumFontFamProc in der Windows SDK-Dokumentation).  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpitchandfamilya--cmfcribbonfontcomboboxgetpitchandfamily"></a><a name="getpitchandfamily"></a>CMFCRibbonFontComboBox::GetPitchAndFamily  
 Gibt die Schriftbreite und Schriftfamilie der Schriftarten zurück, die im Kombinationsfeld angezeigt werden.  
  
```  
BYTE GetPitchAndFamily() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeichenbreite und die Familie (siehe "LogFont" in der Windows SDK-Dokumentation).  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonComboBox-Klasse](../../mfc/reference/cmfcribboncombobox-class.md)

