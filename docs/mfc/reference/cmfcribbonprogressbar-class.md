---
title: Klasse CMFCRibbonProgressBar | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CMFCRibbonProgressBar class
ms.assetid: de3d9f2e-ed59-480e-aa7d-08a33ab36c67
caps.latest.revision: 26
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
ms.openlocfilehash: 51efd8c4ac84dffe1384b7d664197b4bdebad110
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribbonprogressbar-class"></a>CMFCRibbonProgressBar-Klasse
Implementiert ein Steuerelement, das den Fortschritt einer längeren Operation visuell darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonProgressBar : public CMFCRibbonBaseElement  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::CMFCRibbonProgressBar](#cmfcribbonprogressbar)|Erstellt und initialisiert ein `CMFCRibbonProgressBar`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonProgressBar::GetPos](#getpos)|Gibt den aktuellen Status zurück.|  
|[CMFCRibbonProgressBar::GetRangeMax](#getrangemax)|Der maximale Wert des aktuellen Bereichs zurückgegeben.|  
|[CMFCRibbonProgressBar::GetRangeMin](#getrangemin)|Der minimale Wert des aktuellen Bereichs zurückgegeben.|  
|[CMFCRibbonProgressBar::GetRegularSize](#getregularsize)|Gibt die reguläre Größe des Menübandelements zurück. (Überschreibt [cmfcribbonbaseelement:: Getregularsize](../../mfc/reference/cmfcribbonbaseelement-class.md#getregularsize).)|  
|[CMFCRibbonProgressBar::IsInfiniteMode](#isinfinitemode)|Gibt an, ob die Statusanzeige im unendlichen-Modus ausgeführt wird.|  
|[CMFCRibbonProgressBar::OnDraw](#ondraw)|Wird vom Framework aufgerufen, um das Menübandelement zu zeichnen. (Überschreibt [cmfcribbonbaseelement:: OnDraw](../../mfc/reference/cmfcribbonbaseelement-class.md#ondraw).)|  
|[CMFCRibbonProgressBar::SetInfiniteMode](#setinfinitemode)|Legt die Statusanzeige in unendlich Modus arbeiten.|  
|[CMFCRibbonProgressBar::SetPos](#setpos)|Legt den aktuellen Status an.|  
|[CMFCRibbonProgressBar::SetRange](#setrange)|Legt die minimale und maximale Werte.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CMFCRibbonProgressBar` kann in zwei Modi betrieben werden: reguläre und unendlich. Im normalen Modus der Statusanzeige von links nach rechts gefüllt und wird beendet, wenn sie den maximalen Wert erreicht. Im Modus "unendlich" ist die Statusanzeige wiederholt aus der minimale Wert auf den maximalen Wert gefüllt. Sie können unendlich Modus verwenden, um anzugeben, dass ein Vorgang noch ausgeführt wird, aber die Beendigungszeit unbekannt ist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie verschiedene Methoden in der `CMFCRibbonProgressBar` Klasse. Im Beispiel veranschaulicht das Festlegen der Statusleiste können im unendlichen Modus (wobei die Beendigungszeit eines Vorgangs unbekannt ist), legen Sie die minimalen und maximalen Werte für die Statusanzeige zu bewegen, und legen Sie die aktuelle Position der Statusanzeige. Dieser Codeausschnitt ist Teil der [MS Office 2007-Demo-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo&#11;](../../mfc/reference/codesnippet/cpp/cmfcribbonprogressbar-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonProgressBar.h  
  
##  <a name="cmfcribbonprogressbar"></a>CMFCRibbonProgressBar::CMFCRibbonProgressBar  
 Erstellt und initialisiert ein [CMFCRibbonProgressBar](../../mfc/reference/cmfcribbonprogressbar-class.md) Objekt.  
  
```  
CMFCRibbonProgressBar();

 
CMFCRibbonProgressBar(
    UINT nID,  
    int nWidth = 90,  
    int nHeight = 22);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Gibt die Befehls-ID für die Menüband-Statusanzeige an.  
  
 [in] `nWidth`  
 Gibt die Breite in Pixel der Menüband-Statusanzeige an.  
  
 [in] `nHeight`  
 Gibt die Höhe in Pixel der Menüband-Statusanzeige an.  
  
##  <a name="getpos"></a>CMFCRibbonProgressBar::GetPos  
 Gibt die aktuelle Position der Statusanzeige.  
  
```  
int GetPos () const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der die aktuelle Position der Statusanzeige.  
  
### <a name="remarks"></a>Hinweise  
 Festzulegende Bereich muss innerhalb des angegebenen Bereichs der [CMFCRibbonProgressBar::SetRange](#setrange) Methode.  
  
##  <a name="getrangemax"></a>CMFCRibbonProgressBar::GetRangeMax  
 Gibt die Statusleiste die aktuelle maximale Wert.  
  
```  
int GetRangeMax() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der maximale Wert des aktuellen Bereichs.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getrangemin"></a>CMFCRibbonProgressBar::GetRangeMin  
 Gibt die Statusleiste die aktuelle minimalen Bereichswert.  
  
```  
int GetRangeMin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der minimale Wert des aktuellen Bereichs.  
  
##  <a name="getregularsize"></a>CMFCRibbonProgressBar::GetRegularSize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isinfinitemode"></a>CMFCRibbonProgressBar::IsInfiniteMode  
 Gibt an, ob die Statusanzeige im unendlichen-Modus ausgeführt wird.  
  
```  
BOOL IsInfiniteMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Statusanzeige im unendlichen Modus ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Im Modus "unendlich" füllt die Statusanzeige wiederholt aus der minimale Wert auf den maximalen Wert. Sie können unendlich Modus verwenden, um anzugeben, dass ein Vorgang noch ausgeführt wird, aber die Beendigungszeit unbekannt ist.  
  
##  <a name="ondraw"></a>CMFCRibbonProgressBar::OnDraw  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setinfinitemode"></a>CMFCRibbonProgressBar::SetInfiniteMode  
 Legt die Statusanzeige in unendlich Modus arbeiten.  
  
```  
void SetInfiniteMode(BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 `TRUE`um anzugeben, dass die Statusanzeige im unendlichen Modus ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel, wenn die Statusanzeige im unendlichen Modus befindet, ist es dem Benutzer darüber informiert, dass ein Vorgang noch ausgeführt wird, aber die Beendigungszeit unbekannt ist. Daher füllt die Statusanzeige wiederholt aus der minimale Wert auf den maximalen Wert.  
  
##  <a name="setpos"></a>CMFCRibbonProgressBar::SetPos  
 Legt die aktuelle Position der Statusanzeige.  
  
```  
void SetPos(
    int nPos,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nPos`  
 Gibt die Position auf der Statusleiste festgelegt ist.  
  
 [in] `bRedraw`  
 Gibt an, ob die Statusanzeige neu gezeichnet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Festzulegende Bereich muss innerhalb des angegebenen Bereichs der [CMFCRibbonProgressBar::SetRange](#setrange) Methode.  
  
##  <a name="setrange"></a>CMFCRibbonProgressBar::SetRange  
 Legt die minimalen und maximalen Werte für die Statusanzeige.  
  
```  
void SetRange(
    int nMin,  
    int nMax);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nMin`  
 Gibt den Mindestwert des Bereichs an.  
  
 [in] `nMax`  
 Gibt den Höchstwert des Bereichs an.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um den Bereich der Statusanzeige definieren, durch Festlegen der minimalen und maximalen Wert.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonBaseElement-Klasse](../../mfc/reference/cmfcribbonbaseelement-class.md)   
 [CMFCRibbonBar-Klasse](../../mfc/reference/cmfcribbonbar-class.md)

