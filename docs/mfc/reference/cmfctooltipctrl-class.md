---
title: CMFCToolTipCtrl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetIconSize
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::GetParams
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawBorder
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawIcon
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawLabel
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnDrawSeparator
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::OnFillBackground
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetDescription
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetFixedWidth
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetHotRibbonButton
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetLocation
- AFXTOOLTIPCTRL/CMFCToolTipCtrl::SetParams
dev_langs: C++
helpviewer_keywords:
- CMFCToolTipCtrl [MFC], GetIconSize
- CMFCToolTipCtrl [MFC], GetParams
- CMFCToolTipCtrl [MFC], OnDrawBorder
- CMFCToolTipCtrl [MFC], OnDrawDescription
- CMFCToolTipCtrl [MFC], OnDrawIcon
- CMFCToolTipCtrl [MFC], OnDrawLabel
- CMFCToolTipCtrl [MFC], OnDrawSeparator
- CMFCToolTipCtrl [MFC], OnFillBackground
- CMFCToolTipCtrl [MFC], SetDescription
- CMFCToolTipCtrl [MFC], SetFixedWidth
- CMFCToolTipCtrl [MFC], SetHotRibbonButton
- CMFCToolTipCtrl [MFC], SetLocation
- CMFCToolTipCtrl [MFC], SetParams
ms.assetid: 9fbfcfb1-a8ab-417f-ae29-9a9ca85ee58f
caps.latest.revision: "33"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ae37349599977b236f111530f170da746b44b425
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfctooltipctrl-class"></a>CMFCToolTipCtrl-Klasse
Eine erweiterte QuickInfo-Implementierung auf Grundlage von [CToolTipCtrl Class](../../mfc/reference/ctooltipctrl-class.md). Eine QuickInfo auf Grundlage der `CMFCToolTipCtrl` -Klasse kann ein Symbol, eine Bezeichnung und eine Beschreibung anzeigen. Sie können das Aussehen anpassen, indem Sie einen Farbverlauf, einen benutzerdefinierter Text, Rahmenfarben, fetten Text, abgerundete Ecken oder ein Sprechblasenformat verwenden.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolTipCtrl : public CToolTipCtrl  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCToolTipCtrl::CMFCToolTipCtrl`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolTipCtrl::GetIconSize](#geticonsize)|Gibt die Größe eines QuickInfo-Symbols zurück.|  
|[CMFCToolTipCtrl::GetParams](#getparams)|Gibt die Anzeigeeinstellungen für QuickInfo zurück.|  
|[CMFCToolTipCtrl::OnDrawBorder](#ondrawborder)|Zeichnet den QuickInfo-Rahmen.|  
|[CMFCToolTipCtrl::OnDrawDescription](#ondrawdescription)||  
|[CMFCToolTipCtrl::OnDrawIcon](#ondrawicon)|Zeigt ein QuickInfo-Symbol an.|  
|[CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel)|Gibt die QuickInfo-Bezeichnung an oder berechnet die Bezeichnungsgröße.|  
|[CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator)|Zeichnet die Trennlinie zwischen der QuickInfo-Bezeichnung und -Beschreibung.|  
|[CMFCToolTipCtrl::OnFillBackground](#onfillbackground)|Füllt den QuickInfo-Hintergrund.|  
|[CMFCToolTipCtrl::SetDescription](#setdescription)|Legt die von der QuickInfo angezeigte Beschreibung fest.|  
|[CMFCToolTipCtrl::SetFixedWidth](#setfixedwidth)||  
|[CMFCToolTipCtrl::SetHotRibbonButton](#sethotribbonbutton)||  
|[CMFCToolTipCtrl::SetLocation](#setlocation)||  
|[CMFCToolTipCtrl::SetParams](#setparams)|Gibt die visuelle Darstellung einer QuickInfo mit einem `CMFCToolTipInfo`-Objekt an.|  
  
## <a name="remarks"></a>Hinweise  
 Verwendung `CMFCToolTipCtrl`, `CMFCToolTipInfo`, und [CTooltipManager Klasse](../../mfc/reference/ctooltipmanager-class.md) Objekte zusammen, um benutzerdefinierte QuickInfos in Ihrer Anwendung zu implementieren.  
  
 Befolgen Sie die folgenden Schritte, wenn Sie beispielsweise QuickInfo-Sprechblasen verwenden möchten:  
  
 1. Verwenden der [CWinAppEx Class](../../mfc/reference/cwinappex-class.md) Methode, um den QuickInfo-Manager in Ihrer Anwendung zu initialisieren.  
  
 2. Erstellen Sie eine `CMFCToolTipInfo`-Struktur, um den gewünschten visuellen Stil anzugeben:  
  
```  
CMFCToolTipInfo params;  
    params.m_bBoldLabel = FALSE;  
    params.m_bDrawDescription = FALSE;  
    params.m_bDrawIcon = FALSE;  
    params.m_bRoundedCorners = TRUE;  
    params.m_bDrawSeparator = FALSE;  
    if (m_bCustomColors)  
 {  
    params.m_clrFill = RGB (255,
    255,
    255);

    params.m_clrFillGradient = RGB (228,
    228,
    240);

    params.m_clrText = RGB (61,
    83,
    80);

    params.m_clrBorder = RGB (144,
    149,
    168);

 }  
```  
3. Verwenden der [ctooltipmanager:: Settooltipparams](../../mfc/reference/ctooltipmanager-class.md#settooltipparams) Methode, um den visuellen Stil für alle QuickInfos in der Anwendung festgelegt werden, mithilfe der in definierten Formatvorlagen der `CMFCToolTipInfo` Objekt:  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMFCToolTipCtrl), &params);
```  
Zum Steuern des QuickInfo-Verhaltens und -Renderings können Sie auch eine neue Klasse von `CMFCToolTipCtrl` ableiten. Verwenden Sie zum Angeben einer neuen QuickInfo-Steuerelementklasse die `CTooltipManager::SetTooltipParams`-Methode:  
  
```  
myApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    RUNTIME_CLASS (CMyToolTipCtrl))  
```  
Legen Sie zum Wiederherstellen der standardmäßigen QuickInfo-Steuerelementklasse und zum Zurücksetzen des QuickInfo-Formats auf die Standardeinstellung die Laufzeitklasse und die QuickInfo-Parameter von `SetTooltipParams` auf NULL fest.  
  
```  
theApp.GetTooltipManager ()->SetTooltipParams (AFX_TOOLTIP_TYPE_ALL,  
    NULL,
    NULL);
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Sie ein `CMFCToolTipCtrl`-Objekt erstellen, die von der QuickInfo angezeigte Beschreibung und die Breite des Tooltip-Steuerelements festlegen können.  
  
 [!code-cpp[NVC_MFC_RibbonApp#41](../../mfc/reference/codesnippet/cpp/cmfctooltipctrl-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CToolTipCtrl](../../mfc/reference/ctooltipctrl-class.md)  
  
 [CMFCToolTipCtrl](../../mfc/reference/cmfctooltipctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtooltipctrl.h  
  
##  <a name="cmfctooltipctrl"></a>CMFCToolTipCtrl::CMFCToolTipCtrl  

  
```  
CMFCToolTipCtrl(CMFCToolTipInfo* pParams = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pParams`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="geticonsize"></a>CMFCToolTipCtrl::GetIconSize  
 Gibt die Größe eines QuickInfo-Symbols zurück.  
  
```  
virtual CSize GetIconSize();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe des Symbols, in Pixel.  
  
##  <a name="getparams"></a>CMFCToolTipCtrl::GetParams  
 Gibt die Anzeigeeinstellungen für QuickInfo zurück.  
  
```  
const CMFCToolTipInfo& GetParams() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle QuickInfo-Anzeigeeinstellungen, und im rowsetcache eine [CMFCToolTipInfo Klasse](../../mfc/reference/cmfctooltipinfo-class.md) Objekt.  
  
##  <a name="ondrawborder"></a>CMFCToolTipCtrl::OnDrawBorder  
 Zeichnet den QuickInfo-Rahmen.  
  
```  
virtual void OnDrawBorder(
    CDC* pDC,  
    CRect rect,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] pDC`  
 Zeiger zu einem Gerätekontext.  
  
 `[in] rect`  
 Das umschließende Rechteck der QuickInfo.  
  
 `[in] clrLine`  
 Farbe des Rahmens.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse die Darstellung des QuickInfo-Rahmens anpassen.  
  
##  <a name="ondrawdescription"></a>CMFCToolTipCtrl::OnDrawDescription  

  
```  
virtual CSize OnDrawDescription(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 [in] `rect`  
 [in] `bCalcOnly`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawicon"></a>CMFCToolTipCtrl::OnDrawIcon  
 Zeigt ein QuickInfo-Symbol an.  
  
```  
virtual BOOL OnDrawIcon(
    CDC* pDC,  
    CRect rectImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rectImage`  
 Koordinaten des Symbols.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Symbol gezeichnet wurde. Andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse ein benutzerdefiniertes Symbol angezeigt. Sie müssen auch überschreiben [CMFCToolTipCtrl::GetIconSize](#geticonsize) So aktivieren Sie die QuickInfo ein, das Layout von Text und Beschreibung ordnungsgemäß berechnet.  
  
##  <a name="ondrawlabel"></a>CMFCToolTipCtrl::OnDrawLabel  
 Gibt die QuickInfo-Bezeichnung an oder berechnet die Bezeichnungsgröße.  
  
```  
virtual CSize OnDrawLabel(
    CDC* pDC,  
    CRect rect,  
    BOOL bCalcOnly);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 `[in] rect`  
 Umschließende Rechteck des Beschriftungsbereichs.  
  
 `[in] bCalcOnly`  
 Wenn `TRUE`, die Bezeichnung nicht gezeichnet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe der Beschriftung in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie die Darstellung der QuickInfo-Bezeichnung anpassen möchten.  
  
##  <a name="ondrawseparator"></a>CMFCToolTipCtrl::OnDrawSeparator  
 Zeichnet die Trennlinie zwischen der QuickInfo-Bezeichnung und -Beschreibung.  
  
```  
virtual void OnDrawSeparator(
    CDC* pDC,  
    int x1,  
    int x2,  
    int y);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `x1`  
 Horizontale Koordinate der linken Ende des Trennzeichens.  
  
 [in] `x2`  
 Horizontale Koordinate der rechten Ende des Trennzeichens.  
  
 [in] `Y`  
 Vertikale Koordinate des Trennzeichens.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung zeichnet eine verbindende Linie ab dem Punkt (X1, y) auf den Punkt (X2, y).  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse zum Anpassen der Darstellung des Trennzeichens.  
  
##  <a name="onfillbackground"></a>CMFCToolTipCtrl::OnFillBackground  
 Füllt den QuickInfo-Hintergrund.  
  
```  
virtual void OnFillBackground(
    CDC* pDC,  
    CRect rect,  
    COLORREF& clrText,  
    COLORREF& clrLine);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 `[in] rect`  
 Gibt das umschließende Rechteck der den auszufüllenden Bereich an.  
  
 `[in] clrText`  
 QuickInfo-Vordergrundfarbe.  
  
 `[in] clrLine`  
 Die Farbe des Rahmens sowie die Trennzeichen-Zeile zwischen Bezeichnung und Beschreibung.  
  
### <a name="remarks"></a>Hinweise  
 Das Rechteck, das angegeben wird, füllt die standardmäßige Implementierung `rect` mit der Farbe oder einem Muster, die durch den letzten Aufruf angegeben [CMFCToolTipCtrl::SetParams](#setparams).  
  
 Überschreiben Sie diese Methode in einer abgeleiteten Klasse, wenn Sie die Darstellung der QuickInfo anpassen möchten.  
  
##  <a name="setdescription"></a>CMFCToolTipCtrl::SetDescription  
 Legt die von der QuickInfo angezeigte Beschreibung fest.  
  
```  
virtual void SetDescription(const CString strDesrciption);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] strDesrciption`  
 Description-Text.  
  
### <a name="remarks"></a>Hinweise  
 Der Description-Text wird auf die QuickInfo unter der Trennlinie angezeigt.  
  
##  <a name="setfixedwidth"></a>CMFCToolTipCtrl::SetFixedWidth  

  
```  
void SetFixedWidth(
    int nWidthRegular,  
    int nWidthLargeImage);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nWidthRegular`  
 [in] `nWidthLargeImage`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="sethotribbonbutton"></a>CMFCToolTipCtrl::SetHotRibbonButton  

  
```  
void SetHotRibbonButton(CMFCRibbonButton* pRibbonButton);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pRibbonButton`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setlocation"></a>CMFCToolTipCtrl::SetLocation  

  
```  
void SetLocation(CPoint pt);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pt`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setparams"></a>CMFCToolTipCtrl::SetParams  
 Gibt die visuelle Darstellung einer QuickInfo mit einer [CMFCToolTipInfo Klasse](../../mfc/reference/cmfctooltipinfo-class.md) Objekt.  
  
```  
void SetParams(CMFCToolTipInfo* pParams);
```  
  
### <a name="parameters"></a>Parameter  
 `[in] pParams`  
 Zeiger auf eine [CMFCToolTipInfo Klasse](../../mfc/reference/cmfctooltipinfo-class.md) Objekt, das die Parameter enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die QuickInfo wird angezeigt, wird es mithilfe der Farben gezeichnet und visuelle, die Stile `pParams` angibt. Der Wert der `pParams` befindet sich in das geschützte Mitglied `m_Params`, zugegriffen werden kann, durch eine abgeleitete Klasse, die überschreibt [CMFCToolTipCtrl::OnDrawBorder](#ondrawborder), [CMFCToolTipCtrl::OnDrawIcon](#ondrawicon), [CMFCToolTipCtrl::OnDrawLabel](#ondrawlabel), [CMFCToolTipCtrl::OnDrawSeparator](#ondrawseparator), oder [CMFCToolTipCtrl::OnFillBackground](#onfillbackground) zum Verwalten der angegebene Darstellung.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CToolTipCtrl-Klasse](../../mfc/reference/ctooltipctrl-class.md)   
 [CTooltipManager-Klasse](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipInfo-Klasse](../../mfc/reference/cmfctooltipinfo-class.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)
