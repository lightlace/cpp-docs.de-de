---
title: CMFCRibbonLinkCtrl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CopyFrom
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetCompactSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetRegularSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetToolTipText
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::IsDrawTooltipImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDraw
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDrawMenuImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnMouseMove
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnSetIcon
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OpenLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::SetLink
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonLinkCtrl [MFC], CMFCRibbonLinkCtrl
- CMFCRibbonLinkCtrl [MFC], CopyFrom
- CMFCRibbonLinkCtrl [MFC], GetCompactSize
- CMFCRibbonLinkCtrl [MFC], GetLink
- CMFCRibbonLinkCtrl [MFC], GetRegularSize
- CMFCRibbonLinkCtrl [MFC], GetToolTipText
- CMFCRibbonLinkCtrl [MFC], IsDrawTooltipImage
- CMFCRibbonLinkCtrl [MFC], OnDraw
- CMFCRibbonLinkCtrl [MFC], OnDrawMenuImage
- CMFCRibbonLinkCtrl [MFC], OnMouseMove
- CMFCRibbonLinkCtrl [MFC], OnSetIcon
- CMFCRibbonLinkCtrl [MFC], OpenLink
- CMFCRibbonLinkCtrl [MFC], SetLink
ms.assetid: 77ae1941-e0ab-4a9d-911e-1752d34c079b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d078900c3436c2205905b92d651bab86e94db246
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039010"
---
# <a name="cmfcribbonlinkctrl-class"></a>CMFCRibbonLinkCtrl-Klasse
Implementiert einen Hyperlink, der auf einem Menüband positioniert wird. Wenn Sie den Hyperlink anklicken, wird eine Webseite geöffnet.  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonLinkCtrl : public CMFCRibbonButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl](#cmfcribbonlinkctrl)|Erstellt und initialisiert ein `CMFCRibbonLinkCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonLinkCtrl::CopyFrom](#copyfrom)|(Überschreibt `CMFCRibbonButton::CopyFrom`.)|  
|[CMFCRibbonLinkCtrl::GetCompactSize](#getcompactsize)|(Überschreibt [cmfcribbonbutton:: Getcompactsize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|  
|[CMFCRibbonLinkCtrl::GetLink](#getlink)|Gibt den Wert des Links zurück.|  
|[CMFCRibbonLinkCtrl::GetRegularSize](#getregularsize)|(Überschreibt [cmfcribbonbutton:: Getregularsize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|  
|[CMFCRibbonLinkCtrl::GetToolTipText](#gettooltiptext)|(Überschreibt [cmfcribbonbutton:: GetToolTipText](../../mfc/reference/cmfcribbonbutton-class.md#gettooltiptext).)|  
|[CMFCRibbonLinkCtrl::IsDrawTooltipImage](#isdrawtooltipimage)|(Überschreibt `CMFCRibbonButton::IsDrawTooltipImage`.)|  
|[CMFCRibbonLinkCtrl::OnDraw](#ondraw)|(Überschreibt [cmfcribbonbutton:: OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|  
|[CMFCRibbonLinkCtrl::OnDrawMenuImage](#ondrawmenuimage)|(Überschreibt [cmfcribbonbaseelement:: Ondrawmenuimage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|  
|[CMFCRibbonLinkCtrl::OnMouseMove](#onmousemove)|(Überschreibt `CMFCRibbonButton::OnMouseMove`.)|  
|[CMFCRibbonLinkCtrl::OnSetIcon](#onseticon)||  
|[CMFCRibbonLinkCtrl::OpenLink](#openlink)|Öffnet die im Link angegebene Webseite.|  
|[CMFCRibbonLinkCtrl::SetLink](#setlink)|Legt den Wert des Links fest.|  
  
## <a name="remarks"></a>Hinweise  
 Nachdem Sie einen Hyperlink erstellen, hinzufügen zu einem Bereich durch Aufrufen von [cmfcribbonpanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md) [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md) [CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxRibbonLinkCtrl.h  
  
##  <a name="cmfcribbonlinkctrl"></a>  CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl  
 Erstellt und initialisiert ein [CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md) Objekt.  
  
```  
CMFCRibbonLinkCtrl(
    UINT nID,  
    LPCTSTR lpszText,  
    LPCTSTR lpszLink);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nID*  
 Gibt die Befehls-ID des Befehls, der ausgeführt wird, wenn das Linksteuerelement geklickt wird.  
  
 [in] *LpszText*  
 Gibt die Bezeichnung auf die Link-Steuerelement angezeigt werden sollen.  
  
 [in] *LpszLink*  
 Gibt den Link, der dem Linksteuerelement zugeordnet.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie mithilfe des Konstruktors, der die `CMFCRibbonLinkCtrl` Klasse. Dieser Codeausschnitt ist Teil der [Menüband Gadgets Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_RibbonGadgets#1](../../mfc/reference/codesnippet/cpp/cmfcribbonlinkctrl-class_1.cpp)]  
  
##  <a name="copyfrom"></a>  CMFCRibbonLinkCtrl::CopyFrom  

  
```  
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Src*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcompactsize"></a>  CMFCRibbonLinkCtrl::GetCompactSize  

  
```  
virtual CSize GetCompactSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getlink"></a>  CMFCRibbonLinkCtrl::GetLink  
 Gibt den Wert des Links zurück.  
  
```  
LPCTSTR GetLink() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der aktuelle Wert des Links.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getregularsize"></a>  CMFCRibbonLinkCtrl::GetRegularSize  

  
```  
virtual CSize GetRegularSize(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gettooltiptext"></a>  CMFCRibbonLinkCtrl::GetToolTipText  

  
```  
virtual CString GetToolTipText() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondrawmenuimage"></a>  CMFCRibbonLinkCtrl::OnDrawMenuImage  

  
```  
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *CDC**  
 [in] *CRect*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="isdrawtooltipimage"></a>  CMFCRibbonLinkCtrl::IsDrawTooltipImage  

  
```  
virtual BOOL IsDrawTooltipImage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ondraw"></a>  CMFCRibbonLinkCtrl::OnDraw  

  
```  
virtual void OnDraw(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pDC*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onmousemove"></a>  CMFCRibbonLinkCtrl::OnMouseMove  

  
```  
virtual void OnMouseMove(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *zeigen*  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="onseticon"></a>  CMFCRibbonLinkCtrl::OnSetIcon  

  
```  
virtual void OnSetIcon();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="openlink"></a>  CMFCRibbonLinkCtrl::OpenLink  
 Öffnet die im Link angegebene Webseite.  
  
```  
BOOL OpenLink();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der zugeordnete Webseite erfolgreich geöffnet wurde; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Öffnet eine Webseite, die über den Link zugeordnet der `CMFCRibbonLinkCtrl` Objekt.  
  
##  <a name="setlink"></a>  CMFCRibbonLinkCtrl::SetLink  
 Legt den Wert des Links fest.  
  
```  
void SetLink(LPCTSTR lpszLink);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *LpszLink*  
 Gibt den Text des Links.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonButton-Klasse](../../mfc/reference/cmfcribbonbutton-class.md)
