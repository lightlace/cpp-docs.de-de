---
title: CTooltipManager Klasse | Microsoft Docs
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
ms.openlocfilehash: 01d0cb0774af7c1c900f31b4e83bb03dba8bd255
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121085"
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
 Verwendung [CMFCToolTipCtrl Klasse](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, und `CTooltipManager` zusammen, um benutzerdefinierte QuickInfos in Ihrer Anwendung zu implementieren. Ein Beispiel zur Verwendung dieser QuickInfo-Klassen finden Sie unter der [CMFCToolTipCtrl Klasse](../../mfc/reference/cmfctooltipctrl-class.md) Thema.  
  
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
 [out] *pToolTip*  
 Ein Verweis auf ein QuickInfo-Zeiger. Es wird festgelegt, um auf die neu erstellte QuickInfo zu verweisen, wenn die Funktion zurückgibt.  
  
 [in] *pWndParent*  
 Übergeordnete Element der QuickInfo.  
  
 [in] *%nbenachrichtigungen zu*  
 Der Typ der QuickInfo.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn eine QuickInfo erfolgreich erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie [CTooltipManager::DeleteToolTip](#deletetooltip) das QuickInfo-Steuerelement zu löschen, die in zurückgegeben wird *pToolTip*.  
  
 Die [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) legt die visuelle Darstellung-Parameter, der jede QuickInfo, die sie erstellt auf der QuickInfo Grundlage eingeben, *%nbenachrichtigungen zu* angibt. Um die Parameter für einen oder mehrere Typen von QuickInfo zu ändern, rufen [ctooltipmanager:: Settooltipparams](#settooltipparams).  
  
 Gültige QuickInfo-Typen sind in der folgenden Tabelle aufgeführt:  
  
|QuickInfo-Typ|Steuerelement-Kategorie|Beispieltypen|  
|------------------|----------------------|-------------------|  
|AFX_TOOLTIP_TYPE_BUTTON|Eine Schaltfläche.|CMFCButton|  
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Eine Titelleiste.|CMFCCaptionBar|  
|AFX_TOOLTIP_TYPE_DEFAULT|Jedes Steuerelement, das nicht eine der anderen Kategorien passen.|Keine|  
|AFX_TOOLTIP_TYPE_DOCKBAR|Ein andockbares Fenster.|CDockablePane|  
|AFX_TOOLTIP_TYPE_EDIT|Ein Textfeld.|Keine|  
|AFX_TOOLTIP_TYPE_MINIFRAME|Eine Miniframe.|CPaneFrameWnd|  
|AFX_TOOLTIP_TYPE_PLANNER|Ein Planer.|Keine|  
|AFX_TOOLTIP_TYPE_RIBBON|Eine menübandleiste.|CMFCRibbonBar CMFCRibbonPanelMenuBar|  
|AFX_TOOLTIP_TYPE_TAB|Ein Registerkarten-Steuerelement.|CMFCTabCtrl|  
|AFX_TOOLTIP_TYPE_TOOLBAR|Eine Symbolleiste.|CMFCToolBar CMFCPopupMenuBar|  
|AFX_TOOLTIP_TYPE_TOOLBOX|Eine Toolbox.|Keine|  
  
##  <a name="deletetooltip"></a>  CTooltipManager::DeleteToolTip  
 Löscht ein QuickInfo-Steuerelement.  
  
```  
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] *pToolTip*  
 Ein Verweis auf einen Zeiger zu einer QuickInfo, die gelöscht werden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode für jede [CToolTipCtrl-Klasse](../../mfc/reference/ctooltipctrl-class.md) erstellte [CTooltipManager::CreateToolTip](#createtooltip). Das übergeordnete Steuerelement sollte rufen diese Methode aus der `OnDestroy` Handler. Dies ist erforderlich, die QuickInfo ordnungsgemäß aus dem Framework zu entfernen. Diese Methode legt *pToolTip* auf NULL vor dem zurückgeben.  
  
##  <a name="settooltipparams"></a>  Ctooltipmanager:: Settooltipparams  
 Passt die Darstellung der QuickInfo-Steuerelements für die angegebene Windows-Steuerelementtypen an.  
  
```  
void SetTooltipParams(
    UINT nTypes,  
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),  
    CMFCToolTipInfo* pParams=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *nTypes*  
 Gibt die Steuerelementtypen an.  
  
 [in] *pRTC*  
 Benutzerdefinierte QuickInfo-Runtime-Klasse.  
  
 [in] *pParams*  
 QuickInfo-Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt die Laufzeitklasse und die ursprünglichen Parameter, die die [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) beim Erstellen von QuickInfos verwendet. Wenn ein Steuerelement ruft [CTooltipManager::CreateToolTip](#createtooltip) und übergibt in einer QuickInfo-Typ, einer der Typen erkennbar *nTypes*, der QuickInfo-Manager erstellt ein QuickInfo-Steuerelement, das eine Instanz von der Runtime-Klasse, die vom angegebenen *pRTC* und übergibt die Parameter, die vom angegebenen *pParams* auf die neue QuickInfo.  
  
 Wenn Sie diese Methode aufrufen, alle vorhandenen Besitzer der QuickInfo die AFX_WM_UPDATETOOLTIPS Meldung aus, und sie müssen die QuickInfos neu erstellen, mit [CTooltipManager::CreateToolTip](#createtooltip).  
  
 *nTypes* kann eine beliebige Kombination aus gültigen QuickInfo eingibt, [CTooltipManager::CreateToolTip](#createtooltip) verwendet, oder es kann AFX_TOOLTIP_TYPE_ALL sein. Wenn Sie AFX_TOOLTIP_TYPE_ALL übergeben, werden alle QuickInfo Berechtigungstypen beeinflusst.  
  
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
 [in] *pTI*  
 Ein Zeiger auf ein TOOLINFO-Objekt.  
  
 [in, out] *pToolTip*  
 Ein Zeiger auf das QuickInfo-Steuerelement für die den Text und die Beschreibung festgelegt.  
  
 [in] *%nbenachrichtigungen zu*  
 Gibt den Typ des Steuerelements, der dieser QuickInfo zugeordnet ist.  
  
 [in] *StrText*  
 Der Text, der als QuickInfo-Text festgelegt.  
  
 [in] *LpszDescr*  
 Ein Zeiger auf die QuickInfo-Beschreibung. NULL kann sein.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der *%nbenachrichtigungen zu* muss der gleiche Wert wie die *%nbenachrichtigungen zu* Parameter [CTooltipManager::CreateToolTip](#createtooltip) beim Erstellen der QuickInfo angezeigt.  
  
##  <a name="updatetooltips"></a>  CTooltipManager::UpdateTooltips  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void UpdateTooltips();
```  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolTipCtrl-Klasse](../../mfc/reference/cmfctooltipctrl-class.md)   
 [CMFCToolTipInfo-Klasse](../../mfc/reference/cmfctooltipinfo-class.md)
