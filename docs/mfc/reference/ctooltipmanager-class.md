---
title: CTooltipManager-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
dev_langs:
- C++
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81e027108d0f7b62ba707718c5396432396bdc5e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711879"
---
# <a name="ctooltipmanager-class"></a>CTooltipManager-Klasse
Verwaltet Laufzeitinformationen über QuickInfos. Die `CTooltipManager` -Klasse wird einmal pro Anwendung instanziiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTooltipManager : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTooltipManager::CreateToolTip](#createtooltip)|Erstellt ein QuickInfo-Steuerelement für die angegebenen Windows-Steuerelementtypen.|  
|[CTooltipManager::DeleteToolTip](#deletetooltip)|Löscht ein QuickInfo-Steuerelement.|  
|[Ctooltipmanager:: Settooltipparams](#settooltipparams)|Passt die visuelle Darstellung des QuickInfo-Steuerelements für die angegebenen Windows-Steuerelementtypen an.|  
|[CTooltipManager::SetTooltipText](#settooltiptext)|Legt den Text und die Beschreibung für ein QuickInfo-Steuerelement fest.|  
|[CTooltipManager::UpdateTooltips](#updatetooltips)||  
  
## <a name="remarks"></a>Hinweise  
 Verwendung [CMFCToolTipCtrl-Klasse](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, und `CTooltipManager` zusammen, um benutzerdefinierte QuickInfos in Ihrer Anwendung zu implementieren. Ein Beispiel zur Verwendung dieser QuickInfo-Klassen finden Sie unter den [CMFCToolTipCtrl-Klasse](../../mfc/reference/cmfctooltipctrl-class.md) Thema.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtooltipmanager.h  
  
##  <a name="createtooltip"></a>  CTooltipManager::CreateToolTip  
 Erstellt ein QuickInfo-Steuerelement.  
  
```  
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,  
    CWnd* pWndParent,  
    UINT nType);
```  
  
### <a name="parameters"></a>Parameter  
*pToolTip*<br/>
[out] Ein Verweis auf ein QuickInfo-Zeiger. Es wird festgelegt, um auf die neu erstellte QuickInfo zu verweisen, bei Rückgabe der Funktion.  
  
*pWndParent*<br/>
[in] Übergeordnete Element der QuickInfo.  
  
*nType*<br/>
[in] Der Typ der QuickInfo.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn eine QuickInfo wurde erfolgreich erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [CTooltipManager::DeleteToolTip](#deletetooltip) So löschen Sie das QuickInfo-Steuerelement, das zurück übergeben wird *pToolTip*.  
  
 Die [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) legt die visuelle Darstellung-Parameter, der jede QuickInfo erstellt auf der QuickInfo Grundlage eingeben, die *nType* angibt. Um die Parameter für einen oder mehrere QuickInfo-Typen zu ändern, rufen [ctooltipmanager:: Settooltipparams](#settooltipparams).  
  
 Gültige QuickInfo-Typen werden in der folgenden Tabelle aufgelistet:  
  
|QuickInfo-Typ|Kategorie "Steuerelement"|Beispieltypen|  
|------------------|----------------------|-------------------|  
|AFX_TOOLTIP_TYPE_BUTTON|Eine Schaltfläche.|CMFCButton|  
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Titelleiste.|CMFCCaptionBar|  
|AFX_TOOLTIP_TYPE_DEFAULT|Jedes Steuerelement, das nicht mit einer anderen Kategorie passt.|Keine|  
|AFX_TOOLTIP_TYPE_DOCKBAR|Einen andockbaren Bereich.|CDockablePane|  
|AFX_TOOLTIP_TYPE_EDIT|Ein Textfeld.|Keine|  
|AFX_TOOLTIP_TYPE_MINIFRAME|Ein Benutzer.|CPaneFrameWnd|  
|AFX_TOOLTIP_TYPE_PLANNER|Eine Planner.|Keine|  
|AFX_TOOLTIP_TYPE_RIBBON|Eine menübandleiste.|CMFCRibbonBar, CMFCRibbonPanelMenuBar|  
|AFX_TOOLTIP_TYPE_TAB|Ein Registerkarten-Steuerelement.|CMFCTabCtrl|  
|AFX_TOOLTIP_TYPE_TOOLBAR|Eine Symbolleiste.|CMFCToolBar, CMFCPopupMenuBar|  
|AFX_TOOLTIP_TYPE_TOOLBOX|Eine Toolbox.|Keine|  
  
##  <a name="deletetooltip"></a>  CTooltipManager::DeleteToolTip  
 Löscht ein QuickInfo-Steuerelement.  
  
```  
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```  
  
### <a name="parameters"></a>Parameter  
*pToolTip*<br/>
[in, out] Ein Verweis auf einen Zeiger auf eine QuickInfo ein, die zerstört werden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode für die einzelnen [CToolTipCtrl-Klasse](../../mfc/reference/ctooltipctrl-class.md) erstellte [CTooltipManager::CreateToolTip](#createtooltip). Das übergeordnete Steuerelement sollten diese Methode aus Aufrufen seiner `OnDestroy` Handler. Dies ist erforderlich, um die QuickInfo aus dem Framework ordnungsgemäß zu entfernen. Diese Methode legt *pToolTip* auf NULL, bevor sie zurückkehrt.  
  
##  <a name="settooltipparams"></a>  Ctooltipmanager:: Settooltipparams  
 Passt die Darstellung der QuickInfo-Steuerelements für die angegebenen Windows-Steuerelementtypen.  
  
```  
void SetTooltipParams(
    UINT nTypes,  
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),  
    CMFCToolTipInfo* pParams=NULL);
```  
  
### <a name="parameters"></a>Parameter  
*nTypes*<br/>
[in] Gibt die Steuerelementtypen an.  
  
*pRTC*<br/>
[in] Runtime-Klasse, der benutzerdefinierte QuickInfo angezeigt.  
  
*pParams*<br/>
[in] QuickInfo-Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt die Runtime-Klasse und die ursprünglichen Parameter, die die [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) verwendet beim Erstellen von QuickInfos. Wenn ein Steuerelement ruft [CTooltipManager::CreateToolTip](#createtooltip) und übergibt in einer QuickInfo-Typ, eine der folgenden Datentypen von *nTypes*, der QuickInfo-Manager erstellt ein QuickInfo-Steuerelement, das eine Instanz von der Runtime-Klasse, die anhand des *pRTC* und übergibt die vom angegebenen Parametern *pParams* auf die neue QuickInfo.  
  
 Wenn Sie diese Methode aufrufen, alle vorhandenen Besitzer der QuickInfo die AFX_WM_UPDATETOOLTIPS Meldung aus, und sie müssen ihre QuickInfos neu erstellen, mit [CTooltipManager::CreateToolTip](#createtooltip).  
  
 *nTypes* kann eine beliebige Kombination aus gültigen QuickInfo-Typen, die [CTooltipManager::CreateToolTip](#createtooltip) verwendet wird, oder er kann AFX_TOOLTIP_TYPE_ALL sein. Wenn Sie AFX_TOOLTIP_TYPE_ALL übergeben, sind alle Typen von QuickInfo betroffen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `SetTooltipParams` Methode der `CTooltipManager` Klasse. Dieser Codeausschnitt ist Teil des [Draw Client-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]  
  
##  <a name="settooltiptext"></a>  CTooltipManager::SetTooltipText  
 Legt den Text und die Beschreibung für eine QuickInfo an.  
  
```  
static void SetTooltipText(
    TOOLINFO* pTI,  
    CToolTipCtrl* pToolTip,  
    UINT nType,  
    const CString strText,  
    LPCTSTR lpszDescr=NULL);
```  
  
### <a name="parameters"></a>Parameter  
*PTI*<br/>
[in] Ein Zeiger auf ein TOOLINFO-Objekt.  
  
*pToolTip*<br/>
[in, out] Ein Zeiger auf das QuickInfo-Steuerelement für die Text und Beschreibung festgelegt.  
  
*nType*<br/>
[in] Gibt den Typ des Steuerelements, das dieser QuickInfo zugeordnet ist.  
  
*strText*<br/>
[in] Der Text als QuickInfo-Text festlegen.  
  
*lpszDescr*<br/>
[in] Ein Zeiger auf die QuickInfo-Beschreibung. NULL kann sein.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert des *nType* muss der gleiche Wert wie die *nType* Parameter [CTooltipManager::CreateToolTip](#createtooltip) beim Erstellen der QuickInfos.  
  
##  <a name="updatetooltips"></a>  CTooltipManager::UpdateTooltips  
 Weitere Informationen finden Sie im Quellcode der **VC\\Atlmfc\\Src\\Mfc** Ordner von Visual Studio-Installation.  
  
```  
void UpdateTooltips();
```  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolTipCtrl-Klasse](../../mfc/reference/cmfctooltipctrl-class.md)   
 [CMFCToolTipInfo-Klasse](../../mfc/reference/cmfctooltipinfo-class.md)
