---
title: Klasse CTooltipManager | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTooltipManager
dev_langs:
- C++
helpviewer_keywords:
- CTooltipManager class
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
caps.latest.revision: 22
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
ms.openlocfilehash: 3bbf191aacdd318f2afb0bd1a126c3eff290fad6
ms.lasthandoff: 02/24/2017

---
# <a name="ctooltipmanager-class"></a>CTooltipManager-Klasse
Verwaltet Laufzeitinformationen über QuickInfos. Die `CTooltipManager` -Klasse wird einmal pro Anwendung instanziiert.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CTooltipManager : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CTooltipManager::CreateToolTip](#createtooltip)|Erstellt ein QuickInfo-Steuerelement für die angegebenen Windows-Steuerelementtypen.|  
|[CTooltipManager::DeleteToolTip](#deletetooltip)|Löscht ein QuickInfo-Steuerelement.|  
|[CTooltipManager::SetTooltipParams](#settooltipparams)|Passt die visuelle Darstellung des QuickInfo-Steuerelements für die angegebenen Windows-Steuerelementtypen an.|  
|[CTooltipManager::SetTooltipText](#settooltiptext)|Legt den Text und die Beschreibung für ein QuickInfo-Steuerelement fest.|  
|[CTooltipManager::UpdateTooltips](#updatetooltips)||  
  
## <a name="remarks"></a>Hinweise  
 Verwendung [CMFCToolTipCtrl Klasse](../../mfc/reference/cmfctooltipctrl-class.md), `CMFCToolTipInfo`, und `CTooltipManager` zusammen, um benutzerdefinierte QuickInfos in Ihre Anwendung implementieren. Ein Beispiel zur Verwendung dieser QuickInfo-Klassen finden Sie unter der [CMFCToolTipCtrl Klasse](../../mfc/reference/cmfctooltipctrl-class.md) Thema.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtooltipmanager.h  
  
##  <a name="a-namecreatetooltipa--ctooltipmanagercreatetooltip"></a><a name="createtooltip"></a>CTooltipManager::CreateToolTip  
 Erstellt ein QuickInfo-Steuerelement.  
  
```  
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,  
    CWnd* pWndParent,  
    UINT nType);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `pToolTip`  
 Ein Verweis auf ein QuickInfo-Zeiger. Es wird auf die neu erstellte QuickInfo zeigen bei Rückgabe der Funktion festgelegt.  
  
 [in] `pWndParent`  
 Übergeordnete Element der QuickInfo.  
  
 [in] `nType`  
 Der Typ der QuickInfo.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn eine QuickInfo erfolgreich erstellt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen Aufrufen [CTooltipManager::DeleteToolTip](#deletetooltip) das QuickInfo-Steuerelement zu löschen, die in übergeben wird `pToolTip`.  
  
 Die [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md) legt die visuelle Anzeige-Parameter von jeder QuickInfo erstellt auf der QuickInfo Grundlage zu geben, die `nType` angibt. Um die Parameter für einen oder mehrere Typen von QuickInfo zu ändern, rufen [CTooltipManager::SetTooltipParams](#settooltipparams).  
  
 Gültige QuickInfo-Typen sind in der folgenden Tabelle aufgeführt:  
  
|QuickInfo-Typ|Steuerelement-Kategorie|Beispieltypen|  
|------------------|----------------------|-------------------|  
|AFX_TOOLTIP_TYPE_BUTTON|Eine Schaltfläche.|CMFCButton|  
|AFX_TOOLTIP_TYPE_CAPTIONBAR|Eine Titelleiste.|CMFCCaptionBar|  
|AFX_TOOLTIP_TYPE_DEFAULT|Jedes Steuerelement, das nicht in eine der anderen Kategorien passen.|Keine.|  
|AFX_TOOLTIP_TYPE_DOCKBAR|Einen andockbaren Bereich.|CDockablePane|  
|AFX_TOOLTIP_TYPE_EDIT|Ein Textfeld.|Keine.|  
|AFX_TOOLTIP_TYPE_MINIFRAME|Ein Miniframe.|CPaneFrameWnd|  
|AFX_TOOLTIP_TYPE_PLANNER|Ein Planer.|Keine.|  
|AFX_TOOLTIP_TYPE_RIBBON|Eine menübandleiste.|CMFCRibbonBar CMFCRibbonPanelMenuBar|  
|AFX_TOOLTIP_TYPE_TAB|Ein Registerkarten-Steuerelement.|CMFCTabCtrl|  
|AFX_TOOLTIP_TYPE_TOOLBAR|Eine Symbolleiste.|CMFCToolBar CMFCPopupMenuBar|  
|AFX_TOOLTIP_TYPE_TOOLBOX|Eine Toolbox.|Keine|  
  
##  <a name="a-namedeletetooltipa--ctooltipmanagerdeletetooltip"></a><a name="deletetooltip"></a>CTooltipManager::DeleteToolTip  
 Löscht ein QuickInfo-Steuerelement.  
  
```  
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```  
  
### <a name="parameters"></a>Parameter  
 [in, out] `pToolTip`  
 Ein Verweis auf einen Zeiger auf eine QuickInfo zerstört werden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode für jede [CToolTipCtrl-Klasse](../../mfc/reference/ctooltipctrl-class.md) erstellte [CTooltipManager::CreateToolTip](#createtooltip). Das übergeordnete Steuerelement sollten diese Methode von Aufrufen der `OnDestroy` Handler. Dies ist erforderlich, die QuickInfo vom Framework ordnungsgemäß zu entfernen. Diese Methode legt `pToolTip` an `NULL` vor der Rückgabe.  
  
##  <a name="a-namesettooltipparamsa--ctooltipmanagersettooltipparams"></a><a name="settooltipparams"></a>CTooltipManager::SetTooltipParams  
 Passt die Darstellung des QuickInfo-Steuerelements für die angegebene Windows-Steuerelementtypen.  
  
```  
void SetTooltipParams(
    UINT nTypes,  
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),  
    CMFCToolTipInfo* pParams=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTypes`  
 Gibt die Steuerelementtypen.  
  
 [in] `pRTC`  
 Common Language Runtime-Klasse des benutzerdefinierten QuickInfo.  
  
 [in] `pParams`  
 QuickInfo-Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt die Common Language Runtime-Klasse und die ursprünglichen Parameter, die die [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) beim Erstellen von QuickInfos verwendet. Wenn ein Steuerelement ruft [CTooltipManager::CreateToolTip](#createtooltip) und übergibt in einer QuickInfo-Typ, einer der Typen, die durch angegebene `nTypes`, der QuickInfo-Manager erstellt ein QuickInfo-Steuerelement, das eine Instanz vom angegebenen Common Language Runtime-Klasse ist `pRTC` und übergibt die angegebenen Parameter `pParams` zu den neuen QuickInfo.  
  
 Wenn Sie diese Methode aufrufen, alle vorhandenen Besitzer von QuickInfo die AFX_WM_UPDATETOOLTIPS angezeigt werden und sie müssen die QuickInfos neu erstellen, mit [CTooltipManager::CreateToolTip](#createtooltip).  
  
 `nTypes`kann eine beliebige Kombination aus gültigen QuickInfo eingibt, [CTooltipManager::CreateToolTip](#createtooltip) verwendet, oder es kann AFX_TOOLTIP_TYPE_ALL sein. Wenn Sie AFX_TOOLTIP_TYPE_ALL übergeben, werden alle Typen von QuickInfo beeinflusst.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `SetTooltipParams` Methode der `CTooltipManager` Klasse. Dieser Codeausschnitt ist Teil der [zeichnen Clientbeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient&#11;](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]  
  
##  <a name="a-namesettooltiptexta--ctooltipmanagersettooltiptext"></a><a name="settooltiptext"></a>CTooltipManager::SetTooltipText  
 Legt den Text und die Beschreibung für die QuickInfo.  
  
```  
static void SetTooltipText(
    TOOLINFO* pTI,  
    CToolTipCtrl* pToolTip,  
    UINT nType,  
    const CString strText,  
    LPCTSTR lpszDescr=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pTI`  
 Ein Zeiger auf ein TOOLINFO-Objekt.  
  
 [in, out] `pToolTip`  
 Ein Zeiger auf das QuickInfo-Steuerelement für den Text und Beschreibung festgelegt.  
  
 [in] `nType`  
 Gibt den Typ des Steuerelements, dem dieser QuickInfo zugeordnet ist.  
  
 [in] `strText`  
 Der Text, der als QuickInfo-Text festgelegt.  
  
 [in] `lpszDescr`  
 Ein Zeiger auf die QuickInfo-Beschreibung. Kann `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der `nType` muss der gleiche Wert wie die `nType` Parameter der [CTooltipManager::CreateToolTip](#createtooltip) beim Erstellen der QuickInfos.  
  
##  <a name="a-nameupdatetooltipsa--ctooltipmanagerupdatetooltips"></a><a name="updatetooltips"></a>CTooltipManager::UpdateTooltips  
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

