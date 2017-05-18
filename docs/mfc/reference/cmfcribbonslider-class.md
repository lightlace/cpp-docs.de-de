---
title: Klasse CMFCRibbonSlider | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::CMFCRibbonSlider
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMax
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRangeMin
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetRegularSize
- AFXRIBBONSLIDER/CMFCRibbonSlider::GetZoomIncrement
- AFXRIBBONSLIDER/CMFCRibbonSlider::HasZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::OnDraw
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetPos
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetRange
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomButtons
- AFXRIBBONSLIDER/CMFCRibbonSlider::SetZoomIncrement
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonSlider class
ms.assetid: 9351ac34-f234-4e42-91e2-763f1989c8ff
caps.latest.revision: 43
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9f05ae7d0f3e1775a3321928867471749e11e679
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonslider-class"></a>CMFCRibbonSlider-Klasse
Die `CMFCRibbonSlider` -Klasse implementiert ein Schieberegler-Steuerelement, das einer menübandleiste oder einer Menüband-Statusleiste hinzugefügt werden können. Das Schieberegler-Steuerelement im Menüband ähnelt den Zoomschiebereglern, die in Office 2007-Anwendungen verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonSlider : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonSlider::CMFCRibbonSlider](#cmfcribbonslider)|Erstellt und initialisiert ein Menüband-Schieberegler-Steuerelement.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonSlider::GetPos](#getpos)|Gibt die aktuelle Position des Schieberegler-Steuerelements.|  
|[CMFCRibbonSlider::GetRangeMax](#getrangemax)|Der maximale Wert des Schiebereglers zurückgegeben.|  
|[CMFCRibbonSlider::GetRangeMin](#getrangemin)|Gibt den minimalen Wert des Schiebereglers zurück.|  
|[CMFCRibbonSlider::GetRegularSize](#getregularsize)|Gibt die reguläre Größe des Menübandelements zurück. (Überschreibt [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonSlider::GetZoomIncrement](#getzoomincrement)|Gibt die Größe des Zoom-Inkrements für das Schieberegler-Steuerelement zurück.|  
|[CMFCRibbonSlider::HasZoomButtons](#haszoombuttons)|Gibt an, ob der Schieberegler Zoom-Schaltflächen hat.|  
|[CMFCRibbonSlider::OnDraw](#ondraw)|Wird vom Framework aufgerufen, um das Menübandelement zu zeichnen. (Überschreibt [cmfcribbonbaseelement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonSlider::SetPos](#setpos)|Legt die aktuelle Position des Slider-Steuerelements fest.|  
|[CMFCRibbonSlider::SetRange](#setrange)|Gibt den Bereich des Schieberegler-Steuerelements durch Festlegen der minimalen und maximalen Werte an.|  
|[CMFCRibbonSlider::SetZoomButtons](#setzoombuttons)|Anzeigen oder Ausblenden der Zoom-Schaltflächen.|  
|[CMFCRibbonSlider::SetZoomIncrement](#setzoomincrement)|Legt die Größe des Zoom-Inkrements für das Schieberegler-Steuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `SetRange` Methode zum Konfigurieren des Bereichs, der für den Schieberegler Zoom-Inkremente. Sie können die aktuelle Position des Schiebereglers festlegen, mit der `SetPos` Methode.  
  
 Sie können zirkuläre Zoom-Schaltflächen auf der linken und rechten Seite des Schieberegler-Steuerelements anzeigen, indem Sie mit der `SetZoomButtons` Methode. In der Standardeinstellung der Schieberegler horizontal, auf die Schaltfläche Zoom links zeigt ein Minuszeichen und auf die Schaltfläche Zoom rechts zeigt ein Pluszeichen (+).  
  
 Die `SetZoomIncrement` -Methode definiert den inkrementellen Wert hinzufügen oder von der aktuellen Position subtrahiert werden soll, wenn ein Benutzer die Zoom-Schaltflächen klickt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCRibbonSlider` Klasse zum Festlegen der Eigenschaften des Schiebereglers. Das Beispiel zeigt, wie ein `CMFCRibbonSlider` Objekt, Zoomschaltflächen anzuzeigen, legen Sie die aktuelle Position des Schieberegler-Steuerelements und legen Sie den Bereich der Werte für das Schieberegler-Steuerelement.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#12;](../../mfc/reference/codesnippet/cpp/cmfcribbonslider-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSlider](../../mfc/reference/cmfcribbonslider-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribbonslider.h  
  
##  <a name="cmfcribbonslider"></a>CMFCRibbonSlider::CMFCRibbonSlider  
 Erstellen Sie einen Menüband-Schieberegler.  
  
```  
CMFCRibbonSlider(
    UINT nID,  
    int nWidth=100);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Schieberegler-ID.  
  
 [in]. `nWidth`  
 Schieberegler-Breite in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt einen Menüband-Schieberegler, der `nWidth` Pixel in der Systemsteuerung Kategorie, an der der Schieberegler hinzugefügt. Standardmäßig ist der Schieberegler horizontal.  
  
##  <a name="getpos"></a>CMFCRibbonSlider::GetPos  
 Gibt die aktuelle Position des Schieberegler-Steuerelements.  
  
```  
int GetPos() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Position des Schieberegler-Steuerelements, das eine Position relativ zum Anfang des Schiebereglers ist.  
  
##  <a name="getrangemax"></a>CMFCRibbonSlider::GetRangeMax  
 Ruft die maximale Inkrement des Schiebereglers, die der Schieberegler auf dem Schieberegler übertragen werden kann.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das maximale Inkrement des Schiebereglers, die der Schieberegler auf dem Schieberegler übertragen werden kann.  
  
##  <a name="getrangemin"></a>CMFCRibbonSlider::GetRangeMin  
 Gibt die minimale Schrittweite, die der Schieberegler auf dem Schieberegler übertragen werden kann.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die minimale Schrittweite, die der Schieberegler auf dem Schieberegler übertragen werden kann.  
  
##  <a name="getregularsize"></a>CMFCRibbonSlider::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getzoomincrement"></a>CMFCRibbonSlider::GetZoomIncrement  
 Zoom Inkrement für das Schieberegler-Steuerelement zu erhalten.  
  
```  
int GetZoomIncrement() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zoom Inkrement für das Schieberegler-Steuerelement.  
  
##  <a name="haszoombuttons"></a>CMFCRibbonSlider::HasZoomButtons  
 Gibt an, ob der Schieberegler Zoom-Schaltflächen hat.  
  
```  
BOOL HasZoomButtons() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Schieberegler Zoom-Schaltflächen enthält. `FALSE` andernfalls.  
  
##  <a name="ondraw"></a>CMFCRibbonSlider::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpos"></a>CMFCRibbonSlider::SetPos  
 Festlegen Sie die aktuelle Position des Slider-Steuerelements.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nPos`  
 Gibt die Position für den Schieberegler festgelegt. Die Position ist relativ zum Anfang des Schiebereglers.  
  
 [in] `bRedraw`  
 Wenn `TRUE`, wird der Schieberegler neu gezeichnet werden.  
  
##  <a name="setrange"></a>CMFCRibbonSlider::SetRange  
 Legen Sie den Bereich der Werte für das Schieberegler-Steuerelement.  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nMin`  
 Gibt die minimale Wert des Schieberegler-Steuerelements.  
  
 [in] `nMax`  
 Gibt die maximale Wert des Schieberegler-Steuerelements.  
  
### <a name="remarks"></a>Hinweise  
 Gibt den Bereich der Werte für das Schieberegler-Steuerelement durch Festlegen der minimalen und maximalen Werte an.  
  
##  <a name="setzoombuttons"></a>CMFCRibbonSlider::SetZoomButtons  
 Ein- oder Ausblenden von Zoom-Schaltflächen.  
  
```  
void SetZoomButtons(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in]. `bSet`  
 `TRUE`um den Zoom-Schaltflächen angezeigt werden. `FALSE` zum Ausblenden.  
  
##  <a name="setzoomincrement"></a>CMFCRibbonSlider::SetZoomIncrement  
 Legen Sie den Zoom-Inkrement für das Schieberegler-Steuerelement.  
  
```  
void SetZoomIncrement(int nZoomIncrement);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nZoomIncrement`  
 Gibt das Inkrement Zoom des Schieberegler-Steuerelements.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement-Klasse](../../mfc/reference/cmfcribbonbaseelement-class.md)

