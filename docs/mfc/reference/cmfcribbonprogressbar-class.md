---
title: CMFCRibbonProgressBar Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::CMFCRibbonProgressBar
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMax
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRangeMin
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::GetRegularSize
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::IsInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::OnDraw
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetInfiniteMode
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetPos
- AFXRIBBONPROGRESSBAR/CMFCRibbonProgressBar::SetRange
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonProgressBar [MFC], CMFCRibbonProgressBar
- CMFCRibbonProgressBar [MFC], GetPos
- CMFCRibbonProgressBar [MFC], GetRangeMax
- CMFCRibbonProgressBar [MFC], GetRangeMin
- CMFCRibbonProgressBar [MFC], GetRegularSize
- CMFCRibbonProgressBar [MFC], IsInfiniteMode
- CMFCRibbonProgressBar [MFC], OnDraw
- CMFCRibbonProgressBar [MFC], SetInfiniteMode
- CMFCRibbonProgressBar [MFC], SetPos
- CMFCRibbonProgressBar [MFC], SetRange
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 24981d2544c2b3e2c8be6a3307829f8a1e1c29ad
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040219"
---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar-Klasse
Implementiert ein Steuerelement, das den Fortschritt einer längeren Operation visuell darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Erstellt und initialisiert ein `CMFCRibbonProgressBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::GetPos](#getpos)|Gibt den aktuellen Status zurück.|  
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|Der größte Wert des aktuellen Bereichs zurückgegeben.|  
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|Der minimale Wert des aktuellen Bereichs zurückgegeben.|  
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|Gibt die reguläre Größe des Menübandelements zurück. (Überschreibt [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|Gibt an, ob die Statusleiste im unbegrenzten Modus arbeitet.|  
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|Wird vom Framework aufgerufen, um das Menübandelement zu zeichnen. (Überschreibt [cmfcribbonbaseelement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|Legt die Statusanzeige für unbegrenzte Modus fest.|  
|[CMFCRibbonProgressBar::SetPos](#setpos)|Legt den aktuellen Status an.|  
|[CMFCRibbonProgressBar::SetRange](#setrange)|Legt die minimalen und maximalen Werte.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CMFCRibbonProgressBar` kann in zwei Modi betrieben werden: regulären und unendlich. Im normalen Modus der Statusanzeige von links nach rechts gefüllt wird, und wird beendet, wenn sie den Maximalwert erreicht. Im Modus "unendlich" ist die Statusanzeige wiederholt auf den Maximalwert aus den kleinsten Wert gefüllt. Sie können unendliche Modus verwenden, um anzugeben, dass ein Vorgang durchgeführt wird, aber die Abschlusszeit unbekannt ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCRibbonProgressBar` Klasse. Das Beispiel zeigt die zum Festlegen der Statusleiste können im unbegrenzten Modus (wobei die Ausführungszeit eines Vorgangs unbekannt ist), legen Sie die minimalen und maximalen Werte für die Statusanzeige, und legen die aktuelle Position der Statusanzeige. Dieser Codeausschnitt ist Teil der [MS Office 2007 Demobeispiel für](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo#11](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonProgressBar.h  
  
##  <a name="cmfcribbonprogressbar"></a>  CMFCRibbonProgressBar::CMFCRibbonProgressBar  
 Erstellt und initialisiert ein [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) Objekt.  
  
```  
CMFCRibbonProgressBar();

 
CMFCRibbonProgressBar(
    UINT nID,  
    int nWidth = 90,  
    int nHeight = 22);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nID*  
 Gibt die Befehls-ID für die Menüband-Statusanzeige an.  
  
 [in] *nWidth*  
 Gibt die Breite in Pixel der Menüband-Statusanzeige an.  
  
 [in] *nHeight*  
 Gibt die Höhe in Pixel der Menüband-Statusanzeige an.  
  
##  <a name="getpos"></a>  CMFCRibbonProgressBar::GetPos  
 Gibt die aktuelle Position der Statusanzeige.  
  
```  
int GetPos () const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der die aktuelle Position der Statusanzeige darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Bereich festgelegt wird innerhalb des Bereichs von angegeben werden muss die [CMFCRibbonProgressBar::SetRange](#setrange) Methode.  
  
##  <a name="getrangemax"></a>  CMFCRibbonProgressBar::GetRangeMax  
 Gibt zurück, der Statusanzeige auf die aktuelle maximale Wert.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der maximale Wert des aktuellen Bereichs.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrangemin"></a>  CMFCRibbonProgressBar::GetRangeMin  
 Gibt zurück, der Statusanzeige auf die aktuelle minimalen Bereichswert.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der minimale Wert des aktuellen Bereichs.  
  
##  <a name="getregularsize"></a>  CMFCRibbonProgressBar::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isinfinitemode"></a>  CMFCRibbonProgressBar::IsInfiniteMode  
 Gibt an, ob die Statusleiste im unbegrenzten Modus arbeitet.  
  
```  
BOOL IsInfiniteMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Statusanzeige im unbegrenzten Modus befindet; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Im Modus "unendlich" füllt die Statusanzeige wiederholt aus den kleinsten Wert auf den Maximalwert. Sie können unendliche Modus verwenden, um anzugeben, dass ein Vorgang durchgeführt wird, aber die Abschlusszeit unbekannt ist.  
  
##  <a name="ondraw"></a>  CMFCRibbonProgressBar::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setinfinitemode"></a>  CMFCRibbonProgressBar::SetInfiniteMode  
 Legt die Statusanzeige für unbegrenzte Modus fest.  
  
```  
void SetInfiniteMode(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bSet*  
 `TRUE` um anzugeben, dass die Statusanzeige im unbegrenzten Modus; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel, wenn die Statusanzeige im unbegrenzten Modus befindet, ist es dem Benutzer darüber informiert, dass ein Vorgang durchgeführt wird, aber die Abschlusszeit unbekannt ist. Daher füllt die Statusanzeige wiederholt aus der minimale Wert auf den Maximalwert.  
  
##  <a name="setpos"></a>  CMFCRibbonProgressBar::SetPos  
 Legt die aktuelle Position der Statusanzeige.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nPos*  
 Gibt die Position, die auf der der Statusanzeige auf festgelegt ist.  
  
 [in] *bRedraw*  
 Gibt an, ob die Statusanzeige neu gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Bereich festgelegt wird innerhalb des Bereichs von angegeben werden muss die [CMFCRibbonProgressBar::SetRange](#setrange) Methode.  
  
##  <a name="setrange"></a>  CMFCRibbonProgressBar::SetRange  
 Legt die minimalen und maximalen Werte für die Statusanzeige.  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nMin*  
 Gibt den Mindestwert des Bereichs an.  
  
 [in] *nMax*  
 Gibt den Höchstwert des Bereichs an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um den Bereich der Statusanzeige definieren, durch Minimal-und Maximalwerte festlegen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement-Klasse](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)
