---
title: Klasse CMFCToolTipInfo | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolTipInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolTipInfo class
ms.assetid: f9d3d7f8-1f08-4342-a7b2-683860e5d2a5
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ed15ce9f3e1abb48c0a6c4eacdf662cc2ef3f9c9
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctooltipinfo-class"></a>CMFCToolTipInfo-Klasse
Speichert Informationen über die visuelle Darstellung von QuickInfos.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolTipInfo  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolTipInfo::operator =](#operator_eq)||  
  
### <a name="data-members"></a>Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolTipInfo::m_bBalloonTooltip](#m_bballoontooltip)|Eine boolesche Variable, die angibt, ob die QuickInfo über eine Sprechblasendarstellung verfügt.|  
|[CMFCToolTipInfo::m_bBoldLabel](#m_bboldlabel)|Eine boolesche Variable, die angibt, ob die QuickInfo-Bezeichnungen in fett formatierter Schrift angezeigt werden.|  
|[CMFCToolTipInfo::m_bDrawDescription](#m_bdrawdescription)|Eine boolesche Variable, die angibt, ob die QuickInfo eine Beschreibung enthält.|  
|[CMFCToolTipInfo::m_bDrawIcon](#m_bdrawicon)|Eine boolesche Variable, die angibt, ob die QuickInfo ein Symbol enthält.|  
|[CMFCToolTipInfo::m_bDrawSeparator](#m_bdrawseparator)|Eine boolesche Variable, die angibt, ob eine Trennzeichen zwischen der QuickInfo-Bezeichnung und der QuickInfo-Beschreibung angezeigt wird.|  
|[CMFCToolTipInfo::m_bRoundedCorners](#m_broundedcorners)|Eine boolesche Variable, die angibt, ob die QuickInfo abgerundete Ecken besitzt.|  
|[CMFCToolTipInfo::m_bVislManagerTheme](#m_bvislmanagertheme)|Eine boolesche Variable, der angibt, ob die Darstellung der QuickInfo durch einen visuellen Manager gesteuert werden sollte (siehe [CMFCVisualManager Klasse](../../mfc/reference/cmfcvisualmanager-class.md)).|  
|[CMFCToolTipInfo::m_clrBorder](#m_clrborder)|Die Farbe des QuickInfo-Rahmens.|  
|[CMFCToolTipInfo::m_clrFill](#m_clrfill)|Die Farbe des QuickInfo-Hintergrunds.|  
|[CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient)|Die Farbe der Verlaufsfläche in der QuickInfo.|  
|[CMFCToolTipInfo::m_clrText](#m_clrtext)|Die Textfarbe in der QuickInfo.|  
|[CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle)|Der Winkel der Verlaufsfläche in der QuickInfo.|  
|[CMFCToolTipInfo::m_nMaxDescrWidth](#m_nmaxdescrwidth)|Die maximal mögliche Breite der Beschreibung in der QuickInfo in Pixel.|  
  
## <a name="remarks"></a>Hinweise  
 Verwendung [CMFCToolTipCtrl Klasse](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, und [CTooltipManager Klasse](../../mfc/reference/ctooltipmanager-class.md) zusammen, um benutzerdefinierte QuickInfos in Ihre Anwendung implementieren. Ein Beispiel zur Verwendung dieser QuickInfo-Klassen finden Sie unter der [CMFCToolTipCtrl Klasse](../../mfc/reference/cmfctooltipctrl-class.md) Thema.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Festlegung der Werte für die verschiedenen Membervariablen in der `CMFCToolTipInfo`-Klasse veranschaulicht.  
  
 [!code-cpp[NVC_MFC_RibbonApp&#42;](../../mfc/reference/codesnippet/cpp/cmfctooltipinfo-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtooltipctrl.h  
  
##  <a name="a-namembballoontooltipa--cmfctooltipinfombballoontooltip"></a><a name="m_bballoontooltip"></a>CMFCToolTipInfo::m_bBalloonTooltip  
 Gibt die Art der Anzeige aller QuickInfos.  
  
```  
BOOL m_bBalloonTooltip;  
```  
  
### <a name="remarks"></a>Hinweise  
 `TRUE`Gibt an, dass QuickInfos der sprechblasenformat `FALSE` gibt an, dass QuickInfos den rechteckigen Stil verwenden.  
  
##  <a name="a-namembboldlabela--cmfctooltipinfombboldlabel"></a><a name="m_bboldlabel"></a>CMFCToolTipInfo::m_bBoldLabel  
 Gibt an, ob die Schriftart des QuickInfo-Text fett formatiert ist.  
  
```  
BOOL m_bBoldLabel;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses Element auf `TRUE` anzuzeigende QuickInfo-Text und fett, oder `FALSE` QuickInfo Bezeichnungen mit Schriftart nicht fett angezeigt.  
  
##  <a name="a-namembdrawdescriptiona--cmfctooltipinfombdrawdescription"></a><a name="m_bdrawdescription"></a>CMFCToolTipInfo::m_bDrawDescription  
 Gibt an, ob jede QuickInfo Beschreibungstext angezeigt.  
  
```  
BOOL m_bDrawDescription;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses Element auf `TRUE` zur Anzeige der Beschreibung oder `FALSE` Beschreibung ausblenden. Sie können die Beschreibung als QuickInfo angeben, durch Aufrufen von [CMFCToolTipCtrl::SetDescription](../../mfc/reference/cmfctooltipctrl-class.md#setdescription)  
  
##  <a name="a-namembdrawicona--cmfctooltipinfombdrawicon"></a><a name="m_bdrawicon"></a>CMFCToolTipInfo::m_bDrawIcon  
 Gibt an, ob alle QuickInfos Symbole anzuzeigen.  
  
```  
BOOL m_bDrawIcon;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses Element auf `TRUE` ein Symbol für jede QuickInfo angezeigt oder `FALSE` QuickInfos ohne Symbole angezeigt.  
  
##  <a name="a-namembdrawseparatora--cmfctooltipinfombdrawseparator"></a><a name="m_bdrawseparator"></a>CMFCToolTipInfo::m_bDrawSeparator  
 Gibt an, ob es sich bei jeder QuickInfo Trennzeichen zwischen der Beschriftung und die Beschreibung enthält.  
  
```  
BOOL m_bDrawSeparator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses Element auf `TRUE` Trennzeichen zwischen den QuickInfo-Bezeichnung und Beschreibung angezeigt oder `FALSE` ohne Trennzeichen QuickInfo.  
  
##  <a name="a-namembroundedcornersa--cmfctooltipinfombroundedcorners"></a><a name="m_broundedcorners"></a>CMFCToolTipInfo::m_bRoundedCorners  
 Gibt an, ob alle QuickInfos abgerundete Ecken besitzen.  
  
```  
BOOL m_bRoundedCorners;  
```  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie dieses Element auf `TRUE` abgerundete Ecken auf QuickInfos anzeigen oder `FALSE` rechteckige Ecken auf QuickInfos angezeigt.  
  
##  <a name="a-namemclrbordera--cmfctooltipinfomclrborder"></a><a name="m_clrborder"></a>CMFCToolTipInfo::m_clrBorder  
 Gibt die Farbe des Rahmens für alle QuickInfos an.  
  
```  
COLORREF m_clrBorder;  
```  
  
##  <a name="a-namemclrfilla--cmfctooltipinfomclrfill"></a><a name="m_clrfill"></a>CMFCToolTipInfo::m_clrFill  
 Gibt die Farbe des QuickInfo-Hintergrund an.  
  
```  
COLORREF m_clrFill;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) ist-1, wird die Hintergrundfarbe für QuickInfo `m_clrFill`. Andernfalls `m_clrFill` gibt die Farbe für den Anfang des Farbverlaufs und `m_clrFillGradient` gibt die Farbe am Ende des Farbverlaufs an. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) bestimmt die Richtung des Farbverlaufs.  
  
##  <a name="a-namemclrfillgradienta--cmfctooltipinfomclrfillgradient"></a><a name="m_clrfillgradient"></a>CMFCToolTipInfo::m_clrFillGradient  
 Gibt die Endfarbe für einen Farbverlauf als Hintergrund für QuickInfos.  
  
```  
COLORREF m_clrFillGradient;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `m_clrFillGradient` ist-1, es wird kein Farbverlauf. Andernfalls wird die anfängliche Farbverlauf angegeben, indem [CMFCToolTipInfo::m_clrFill](#m_clrfill) und die Farbe graduell "Fertig stellen" wird angegeben, indem `m_clrFillGradient`. [CMFCToolTipInfo::m_nGradientAngle](#m_ngradientangle) bestimmt die Richtung des Farbverlaufs.  
  
##  <a name="a-namemclrtexta--cmfctooltipinfomclrtext"></a><a name="m_clrtext"></a>CMFCToolTipInfo::m_clrText  
 Gibt die Textfarbe aller QuickInfos.  
  
```  
COLORREF m_clrText;  
```  
  
##  <a name="a-namemngradientanglea--cmfctooltipinfomngradientangle"></a><a name="m_ngradientangle"></a>CMFCToolTipInfo::m_nGradientAngle  
 Gibt den Winkel, in dem ein Farbverlauf für den Hintergrund von QuickInfos gezeichnet wird.  
  
```  
int m_nGradientAngle;  
```  
  
### <a name="remarks"></a>Hinweise  
 `m_nGradientAngle`Gibt den Winkel in Grad, von der horizontalen Farbverlauf für den Hintergrund von QuickInfos versetzt ist. Wenn `m_nGradientAngle` gleich 0 ist, der Farbverlauf von links nach rechts gezeichnet wird. Wenn `m_nGradientAngle` ist zwischen 1 und 360 ist der Gradient um diese Anzahl von Grad im Uhrzeigersinn drehen. Wenn `m_nGradientAngle` ist-1 und der Standardwert ist, der Farbverlauf von oben nach unten gezeichnet wird. Dies entspricht der Einstellung `m_nGradientAngle` 90.  
  
 [CMFCToolTipInfo::m_clrFill](#m_clrfill) `clrFill` gibt die Farbe für den Anfang des Farbverlaufs und [CMFCToolTipInfo::m_clrFillGradient](#m_clrfillgradient) `clrFillGradient` gibt die Farbe am Ende des Farbverlaufs an. Wenn `m_clrFillGradient` ist-1, es wird kein Farbverlauf.  
  
##  <a name="a-namemnmaxdescrwidtha--cmfctooltipinfomnmaxdescrwidth"></a><a name="m_nmaxdescrwidth"></a>CMFCToolTipInfo::m_nMaxDescrWidth  
 Gibt die maximale Breite der Beschreibung, die sie in jede QuickInfo angezeigt. Wenn die Breite Beschreibung den angegebenen Wert überschreitet, wird der Text umbrochen.  
  
```  
int m_nMaxDescrWidth;  
```  
  
##  <a name="a-namembvislmanagerthemea--cmfctooltipinfombvislmanagertheme"></a><a name="m_bvislmanagertheme"></a>CMFCToolTipInfo::m_bVislManagerTheme  
 Gibt an, ob es sich bei den visuelle Manager der Anwendung das Erscheinungsbild aller QuickInfos gesteuert.  
  
```  
BOOL m_bVislManagerTheme;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn `m_bVislManagerTheme` ist `TRUE`, jede QuickInfo fordert ein neues [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) aus visuellen Manager von der Anwendung, bevor sie auf dem Bildschirm angezeigt, und die Werte in diesem Objekt verwendet, um ihre Darstellung zu bestimmen. Die weiteren Mitglieder Ihrer [CMFCToolTipInfo](../../mfc/reference/cmfctooltipinfo-class.md) werden ignoriert.  
  
##  <a name="a-nameoperatoreqa--cmfctooltipinfooperator"></a><a name="operator_eq"></a>CMFCToolTipInfo::operator =  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
CMFCToolTipInfo& operator=(CMFCToolTipInfo& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `src`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CTooltipManager-Klasse](../../mfc/reference/ctooltipmanager-class.md)   
 [CMFCToolTipCtrl-Klasse](../../mfc/reference/cmfctooltipctrl-class.md)

