---
title: Klasse CBaseTabbedPane | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::AddTab
- AFXBASETABBEDPANE/CBaseTabbedPane::AllowDestroyEmptyTabbedPane
- AFXBASETABBEDPANE/CBaseTabbedPane::ApplyRestoredTabInfo
- AFXBASETABBEDPANE/CBaseTabbedPane::CanFloat
- AFXBASETABBEDPANE/CBaseTabbedPane::CanSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::ConvertToTabbedDocument
- AFXBASETABBEDPANE/CBaseTabbedPane::DetachPane
- AFXBASETABBEDPANE/CBaseTabbedPane::EnableSetCaptionTextToTabName
- AFXBASETABBEDPANE/CBaseTabbedPane::FillDefaultTabsOrderArray
- AFXBASETABBEDPANE/CBaseTabbedPane::FindBarByTabNumber
- AFXBASETABBEDPANE/CBaseTabbedPane::FindPaneByID
- AFXBASETABBEDPANE/CBaseTabbedPane::FloatTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetDefaultTabsOrder
- AFXBASETABBEDPANE/CBaseTabbedPane::GetFirstVisibleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::GetMinSize
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneIcon
- AFXBASETABBEDPANE/CBaseTabbedPane::GetPaneList
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabArea
- AFXBASETABBEDPANE/CBaseTabbedPane::GetTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::GetUnderlyingWindow
- AFXBASETABBEDPANE/CBaseTabbedPane::GetVisibleTabsNum
- AFXBASETABBEDPANE/CBaseTabbedPane::HasAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::IsHideSingleTab
- AFXBASETABBEDPANE/CBaseTabbedPane::RecalcLayout
- AFXBASETABBEDPANE/CBaseTabbedPane::RemovePane
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoDestroy
- AFXBASETABBEDPANE/CBaseTabbedPane::SetAutoHideMode
- AFXBASETABBEDPANE/CBaseTabbedPane::ShowTab
dev_langs:
- C++
helpviewer_keywords:
- CBaseTabbedPane class
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b72804dd8b2ca2253caff4cebf5b0631ae6040c6
ms.lasthandoff: 02/24/2017

---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane-Klasse
Erweitert die Funktionalität von der [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md) unterstützt die Erstellung von Fenstern im Registerkartenformat.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CBaseTabbedPane::CBaseTabbedPane`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CBaseTabbedPane::AddTab](#addtab)|Ein Fenster mit Registerkarten wird eine neue Registerkarte hinzugefügt.|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Gibt an, ob eine leere Seite im Registerformat gelöscht werden kann.|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|Registerkarte Einstellungen, die aus der Registrierung, um ein Fenster mit Registerkarten geladen werden angewendet.|  
|[CBaseTabbedPane::CanFloat](#canfloat)|Bestimmt, ob der Bereich wechseln kann. (Überschreibt [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Bestimmt, ob die Beschriftung für die Seite im Registerformat den gleichen Text wie der aktiven Registerkarte angezeigt werden soll.|  
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(Überschreibt [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|  
|[CBaseTabbedPane::DetachPane](#detachpane)|Konvertiert eine oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumente.|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|Aktiviert oder deaktiviert die Fähigkeit von dem Fenster im Registerkartenformat Beschriftungstext mit den Bezeichnungstext auf der aktiven Registerkarte synchronisieren.|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|Stellt den Standardzustand der internen Reihenfolge wieder her.|  
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|Gibt einen Bereich, der auf einer Registerkarte befindet, wenn die Registerkarte durch eine nullbasierten Registerkartenindex identifiziert wird.|  
|||  
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|Gibt einen Bereich, der durch die Bereich-ID identifiziert wird|  
|[CBaseTabbedPane::FloatTab](#floattab)|Hebt die Verankerung eines Bereichs auf, aber nur, wenn der Bereich sich auf einer lösbaren Registerkarte befindet.|  
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|Die Standardreihenfolge der Registerkarten zurückgibt im Bereich.|  
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|Ruft einen Zeiger auf den ersten angezeigten Registerkarte ab.|  
|[CBaseTabbedPane::GetMinSize](#getminsize)|Ruft den minimal zulässigen Größe für den Bereich ab. (Überschreibt [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|  
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|Gibt ein Handle auf das Symbol "Bereich". (Überschreibt [CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|  
|[CBaseTabbedPane::GetPaneList](#getpanelist)|Gibt eine Liste von Bereichen, die enthalten sind in dem Fenster im Registerkartenformat zurück.|  
|[CBaseTabbedPane::GetTabArea](#gettabarea)|Gibt die umgebenden Rechtecken für die oberen und unteren Registerkarte Bereiche zurück.|  
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|Gibt die Anzahl der Registerkarten in einem Registerkartenfenster zurück.|  
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|Ruft das zugrunde liegende (eingebundene) Registerkartenfenster.|  
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|Gibt die Anzahl der angezeigten Registerkarten zurück.|  
|[CBaseTabbedPane::HasAutoHideMode](#hasautohidemode)|Bestimmt, ob die Seite im Registerformat zum automatischen Ausblenden-Modus gewechselt werden kann.|  
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|Bestimmt, ob die Seite im Registerformat ausgeblendet ist, wenn nur eine Registerkarte angezeigt wird.|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Wird intern verwendet, um während der Serialisierung.|  
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|Berechnet die Layoutinformationen für den Bereich. (Überschreibt [cpane:: RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|  
|[CBaseTabbedPane::RemovePane](#removepane)|Entfernt einen Bereich aus dem Fenster im Registerkartenformat.|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|Wird intern verwendet, um während der Serialisierung.|  
|`CBaseTabbedPane::Serialize`|(Überschreibt [CDockablePane:: SaveState](http://msdn.microsoft.com/en-us/09787e59-e446-4e76-894b-206d303dcfd6).)|  
|`CBaseTabbedPane::SerializeTabWindow`|Wird intern verwendet, um während der Serialisierung.|  
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|Bestimmt, ob die Steuerleiste im Registerkartenformat automatisch zerstört wird.|  
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|Schaltet zwischen der andockbaren angezeigt und automatisch ausgeblendet. (Überschreibt [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|  
|[CBaseTabbedPane::ShowTab](#showtab)|Anzeigen oder ausblenden eine Registerkarte.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse ist eine abstrakte Klasse und kann nicht instanziiert werden. Es implementiert die Dienste, die für alle Arten von Seiten im Registerformat gelten.  
  
 Die Bibliothek enthält derzeit zwei im Registerformat abgeleiteten Klassen: [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md) und [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Ein `CBaseTabbedPane` Objekt umschließt einen Zeiger auf eine [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) Objekt. [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) wird als untergeordnetes Fenster von dem Fenster im Registerkartenformat.  
  
 Weitere Informationen zum Erstellen von Seiten im Registerformat finden Sie unter [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md), [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md), und [CMFCOutlookBar Class](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 `CBaseTabbedPane`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxBaseTabbedPane.h  
  
##  <a name="addtab"></a>CBaseTabbedPane::AddTab  
 Ein Fenster mit Registerkarten wird eine neue Registerkarte hinzugefügt.  
  
```  
virtual BOOL AddTab(
    CWnd* pNewBar,  
    BOOL bVisible = TRUE,  
    BOOL bSetActive = TRUE,  
    BOOL bDetachable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pNewBar`  
 Ein Zeiger auf den Bereich hinzuzufügen. This-Zeiger kann ungültig werden, nachdem Sie diese Methode aufrufen. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 [in] `bVisible`  
 `TRUE`auf die Registerkarte sichtbar zu machen; andernfalls `FALSE`.  
  
 [in] `bSetActive`  
 `TRUE`auf der Registerkarte auf die aktive Registerkarte stellen. andernfalls `FALSE`.  
  
 [in] `bDetachable`  
 `TRUE`auf die Registerkarte lösbar stellen. andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich erfolgreich als Registerkarte hinzugefügt wurde und nicht im Prozess zerstört wurde. `FALSE`ist der Bereich hinzugefügt wird ein Objekt vom Typ `CBaseTabbedPane`. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich als neue Registerkarte für ein Fenster mit Registerkarten hinzufügen. Wenn `pNewBar` verweist auf ein Objekt vom Typ `CBaseTabbedPane`, werden alle Registerkarten auf der Seite im Registerformat kopiert und dann `pNewBar` zerstört wird. Folglich `pNewBar` wird ein ungültiger Zeiger und sollte nicht verwendet werden.  
  
##  <a name="allowdestroyemptytabbedpane"></a>CBaseTabbedPane::AllowDestroyEmptyTabbedPane  
 Gibt an, ob eine leere Seite im Registerformat gelöscht werden kann.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn eine leere Seite im Registerformat zerstört werden kann. andernfalls `FALSE`. Die standardmäßige Implementierung gibt immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine leere Seite im Registerformat gelöscht werden, nicht zulässig ist, wird der Bereich von Framework stattdessen ausgeblendet.  
  
##  <a name="applyrestoredtabinfo"></a>CBaseTabbedPane::ApplyRestoredTabInfo  
 Registerkarte Einstellungen aus der Registrierung geladen, und wendet diese auf einer Seite im Registerformat.  
  
```  
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bUseTabIndexes`  
 Dieser Parameter wird intern vom Framework verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn es Andocken Zustandsinformationen aus der Registrierung erneut geladen. Die-Methode ruft Informationen zur Reihenfolge und Registerkartennamen für ein Fenster mit Registerkarten.  
  
##  <a name="canfloat"></a>CBaseTabbedPane::CanFloat  
 Gibt an, ob die Seite im Registerformat wechseln kann.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich wechseln kann; andernfalls `FALSE`.  
  
##  <a name="cansetcaptiontexttotabname"></a>CBaseTabbedPane::CanSetCaptionTextToTabName  
 Bestimmt, ob die Beschriftung für die Seite im Registerformat den gleichen Text wie der aktiven Registerkarte angezeigt werden soll.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Beschriftungstext für die Seite im Registerformat auf den Text der aktiven Registerkarte festgelegt ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode wird verwendet, um zu bestimmen, ob der Text auf der Seite im Registerformat Beschriftung Duplikate die Bezeichnung der aktiven Registerkarte angezeigt. Sie können aktivieren oder deaktivieren Sie diese Funktionalität durch Aufrufen von [CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname).  
  
##  <a name="converttotabbeddocument"></a>CBaseTabbedPane::ConvertToTabbedDocument  
 Konvertiert eine oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumente.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActiveTabOnly`  
 Geben Sie bei der Konvertierung ein Fenster mit Registerkarten `TRUE` nur die aktive Registerkarte zu konvertieren. Geben Sie `FALSE` alle Registerkarten im Bereich zu konvertieren.  
  
##  <a name="detachpane"></a>CBaseTabbedPane::DetachPane  
 Trennt einen Bereich aus dem Fenster im Registerkartenformat.  
  
```  
virtual BOOL DetachPane(
    CWnd* pBar,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf den Bereich zu trennen.  
  
 [in] `bHide`  
 Boolescher Parameter, der angibt, ob das Framework Bereich ausgeblendet, nachdem sie getrennt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Framework erfolgreich Bereich getrennt; `FALSE` Wenn `pBar` ist `NULL` oder verweist auf einen Bereich, der nicht in die Seite im Registerformat.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework befindet sich im getrennten Bereich Wenn möglich. Weitere Informationen finden Sie unter [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).  
  
##  <a name="enablesetcaptiontexttotabname"></a>CBaseTabbedPane::EnableSetCaptionTextToTabName  
 Aktiviert oder deaktiviert die Fähigkeit von dem Fenster im Registerkartenformat Beschriftungstext mit den Bezeichnungstext auf der aktiven Registerkarte synchronisieren.  
  
```  
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`Synchronisieren Sie die Beschriftung im Registerformat mit der aktiven Registerkarte Beschriftung; andernfalls `FALSE`.  
  
##  <a name="filldefaulttabsorderarray"></a>CBaseTabbedPane::FillDefaultTabsOrderArray  
 Stellt den Standardzustand der internen Reihenfolge wieder her.  
  
```  
void FillDefaultTabsOrderArray();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn das Framework eine Outlook-Leiste auf einen Ausgangszustand wiederherstellt.  
  
##  <a name="findpanebyid"></a>CBaseTabbedPane::FindPaneByID  
 Gibt einen Bereich, der durch die Bereich-ID identifiziert werden  
  
```  
virtual CWnd* FindPaneByID(UINT uBarID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uBarID`  
 Gibt die ID des Bereichs zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Bereich, wenn es gefunden wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode vergleicht alle Registerkarten im Bereich, und gibt das mit der angegebenen ID der `uBarID` Parameter.  
  
##  <a name="findbarbytabnumber"></a>CBaseTabbedPane::FindBarByTabNumber  
 Gibt einen Bereich, der auf einer Registerkarte befindet.  
  
```  
virtual CWnd* FindBarByTabNumber(
    int nTabNum,  
    BOOL bGetWrappedBar = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTabNum`  
 Gibt den nullbasierten Index der abzurufenden Registerkarte.  
  
 [in] `bGetWrappedBar`  
 `TRUE`um das zugrunde liegende (eingebundene) Fenster im Bereich anstelle der Bereich selbst zurückgegeben wird. andernfalls `FALSE`. Dies gilt nur für Bereiche, die von abgeleiteten [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md).  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Bereich, gefunden wird wird ein gültiger Zeiger auf den Bereich gesucht wird zurückgegeben wird andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen von Bereich, die in der angegebenen Registerkarte wohnen die `nTabNum` Parameter.  
  
##  <a name="floattab"></a>CBaseTabbedPane::FloatTab  
 Hebt die Verankerung eines Bereichs auf, aber nur, wenn der Bereich sich auf einer lösbaren Registerkarte befindet.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pBar`  
 Ein Zeiger auf den Bereich in einen Gleitkommawert.  
  
 [in] `nTabID`  
 Gibt den nullbasierten Index der Registerkarte in einen Gleitkommawert an.  
  
 [in] `dockMethod`  
 Gibt die Methode zu verwenden, um den Bereich loszulösen. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 [in] `bHide`  
 `TRUE`um das Fenster auszublenden vor Gleitkommawert; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich umfließt; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich float, der derzeit in einer abnehmbaren Registerkarte befindet.  
  
 Wenn Sie einen Bereich programmgesteuert trennen möchten, geben Sie `DM_SHOW` für die `dockMethod` Parameter. Float-Bereich in der gleichen Position es, in dem zuvor umfließt, geben Sie ggf. `DM_DBL_CLICK` als die `dockMethod` Parameter.  
  
##  <a name="getdefaulttabsorder"></a>CBaseTabbedPane::GetDefaultTabsOrder  
 Die Standardreihenfolge der Registerkarten zurückgibt im Bereich.  
  
```  
const CArray<int,int>& GetDefaultTabsOrder();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CArray` Objekt, das die Standardreihenfolge der Registerkarten im Bereich angibt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn eine Outlook-Leiste auf einen Ausgangszustand zurückgesetzt wird.  
  
##  <a name="getfirstvisibletab"></a>CBaseTabbedPane::GetFirstVisibleTab  
 Ruft einen Zeiger auf den ersten angezeigten Registerkarte ab.  
  
```  
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iTabNum`  
 Ein Verweis auf eine ganze Zahl. Diese Methode schreibt dem nullbasierten Index des ersten angezeigten Registerkarte an diesen Parameter oder -1, wenn keine angezeigt Tabstopp gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn erfolgreich, ein Zeiger auf den ersten angezeigten Registerkarte; andernfalls `NULL`.  
  
##  <a name="getminsize"></a>CBaseTabbedPane::GetMinSize  
 Ruft den minimal zulässigen Größe für den Bereich ab.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `size`  
 Ein `CSize` -Objekt, das mit den minimal zulässigen Größe gefüllt ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die konsistente Behandlung von Größen minimalen Bereich aktiv ist ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), `size` wird mit den minimal zulässigen Größe für die aktive Registerkarte gefüllt. Andernfalls `size` wird gefüllt, mit dem Rückgabewert der [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpaneicon"></a>CBaseTabbedPane::GetPaneIcon  
 Ruft den minimal zulässigen Größe für den Bereich ab.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `size`  
 Ein `CSize` -Objekt, das mit den minimal zulässigen Größe gefüllt ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die konsistente Behandlung von Größen minimalen Bereich aktiv ist ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), `size` wird mit den minimal zulässigen Größe für die aktive Registerkarte gefüllt. Andernfalls `size` wird gefüllt, mit dem Rückgabewert der [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpanelist"></a>CBaseTabbedPane::GetPaneList  
 Gibt eine Liste von Bereichen, die enthalten sind in dem Fenster im Registerkartenformat zurück.  
  
```  
virtual void GetPaneList(
    CObList& lst,  
    CRuntimeClass* pRTCFilter = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `lst`  
 Ein `CObList` gefüllt, die mit den Bereichen, die in die Seite im Registerformat enthalten sind.  
  
 [in] `pRTCFilter`  
 Ist dies nicht `NULL`, die zurückgegebene Liste enthält nur die Bereiche, die die angegebene Runtime-Klasse.  
  
##  <a name="gettabarea"></a>CBaseTabbedPane::GetTabArea  
 Gibt die umgebenden Rechtecken für die oberen und unteren Registerkarte Bereiche zurück.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectTabAreaTop`  
 Empfängt die Bildschirmkoordinaten der oberen Registerkartenbereichs.  
  
 [out] `rectTabAreaBottom`  
 Empfängt die Bildschirmkoordinaten des im unteren Registerkartenbereich.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die umschließende Rechtecke, in Bildschirmkoordinaten, für die oberen und unteren Registerkarte Bereiche zu bestimmen.  
  
##  <a name="gettabsnum"></a>CBaseTabbedPane::GetTabsNum  
 Gibt die Anzahl der Registerkarten in einem Registerkartenfenster zurück.  
  
```  
virtual int GetTabsNum() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Registerkarten in der Seite im Registerformat.  
  
##  <a name="getunderlyingwindow"></a>CBaseTabbedPane::GetUnderlyingWindow  
 Ruft das zugrunde liegende (eingebundene) Registerkartenfenster.  
  
```  
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das zugrunde liegende Registerkartenfenster.  
  
##  <a name="getvisibletabsnum"></a>CBaseTabbedPane::GetVisibleTabsNum  
 Gibt die Anzahl eingeblendeter Registerkarten zurück.  
  
```  
virtual int GetVisibleTabsNum() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der sichtbaren Registerkarten, die größer als oder gleich&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl der sichtbaren Registerkarten in dem Fenster im Registerkartenformat zu bestimmen.  
  
##  <a name="hasautohidemode"></a>CBaseTabbedPane::HasAutoHideMode  
 Bestimmt, ob der Bereich im Registerkartenformat automatisch in den Hintergrundmodus gewechselt werden kann.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bereich automatisch im Hintergrund-Modus gewechselt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Ausblendmodus zum automatischen deaktiviert ist, wird keine Pin-Schaltfläche auf der Seite im Registerformat Beschriftung angezeigt.  
  
##  <a name="ishidesingletab"></a>CBaseTabbedPane::IsHideSingleTab  
 Bestimmt, ob die Seite im Registerformat ausgeblendet ist, wenn nur eine Registerkarte angezeigt wird.  
  
```  
virtual BOOL IsHideSingleTab() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Registerkartenfenster nicht angezeigt wird, wenn nur eine eingeblendete Registerkarte ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Bereich nicht angezeigt wird, da nur eine Registerkarte geöffnet ist, können Sie diese Methode, um zu bestimmen, ob die Seite im Registerformat ordnungsgemäß arbeitet aufrufen.  
  
##  <a name="removepane"></a>CBaseTabbedPane::RemovePane  
 Entfernt einen Bereich aus dem Fenster im Registerkartenformat.  
  
```  
virtual BOOL RemovePane(CWnd* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out]`pBar`  
 Ein Zeiger auf den Bereich, um aus dem Fenster im Registerkartenformat zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`im Bereich aus dem Fenster im Registerkartenformat erfolgreich entfernt wurde und die Seite im Registerformat noch gültig ist. `FALSE`Wenn der letzte Bereich aus dem Fenster im Registerkartenformat entfernt wurde und die Seite im Registerformat zerstört werden soll. Wenn der Rückgabewert ist `FALSE`, verwenden Sie die Seite im Registerformat nicht mehr.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um den angegebenen Bereich Entfernen der `pBar` Parameter aus dem Fenster im Registerkartenformat.  
  
##  <a name="setautodestroy"></a>CBaseTabbedPane::SetAutoDestroy  
 Bestimmt, ob die Steuerleiste im Registerkartenformat automatisch zerstört wird.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAutoDestroy`  
 `TRUE`Wenn die Seite im Registerformat dynamisch erstellt wurde, und Sie sind nicht dessen Lebensdauer steuern; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie den Modus zur automatischen-Zerstörung `TRUE` , wenn Sie ein Fenster mit Registerkarten dynamisch erstellen und seine Lebensdauer nicht aktiv ist. Wenn automatische zerstören Modus ist `TRUE`, die im Registerformat werden automatisch vom Framework gelöscht.  
  
##  <a name="showtab"></a>CBaseTabbedPane::ShowTab  
 Anzeigen oder ausblenden eine Registerkarte.  
  
```  
virtual BOOL ShowTab(
    CWnd* pBar,  
    BOOL bShow,  
    BOOL bDelay,  
    BOOL bActivate);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pBar`  
 Ein Zeiger auf den Bereich, um ein- oder ausblenden.  
  
 [in] `bShow`  
 `TRUE`um den Bereich anzuzeigen; `FALSE` zum Ausblenden des Fensters.  
  
 [in] `bDelay`  
 `TRUE`die Anpassung von der Registerkartenlayout verzögert; andernfalls `FALSE`.  
  
 [in] `bActivate`  
 `TRUE`auf der Registerkarte auf die aktive Registerkarte stellen. andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Registerkarte wurde entweder angezeigt oder ausgeblendet; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Methode aufrufen, ein Bereich entweder ein- oder ausgeblendet wird, abhängig vom Wert der `bShow` Parameter. Wenn Sie einer Registerkarte ausblenden, und es die letzte sichtbare Registerkarte im Registerkartenfenster zugrunde liegenden ist, wird die Seite im Registerformat ausgeblendet. Wenn Sie eine Registerkarte anzuzeigen, wenn zuvor keine Registerkarten sichtbar sind, wird die Seite im Registerformat angezeigt.  
  
##  <a name="recalclayout"></a>CBaseTabbedPane::RecalcLayout  
 Berechnet die Layoutinformationen für den Bereich.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Bereich verankert ist, benachrichtigt diese Methode das Framework den Bereich, um die aktuelle Größe des Mini-Frames in der Größe anpassen.  
  
 Wenn der Bereich angedockt ist, bewirkt diese Methode nichts.  
  
##  <a name="setautohidemode"></a>CBaseTabbedPane::SetAutoHideMode  
 Legt automatisch ausblenden-Modus für die abnehmbare Bereiche in die Seite im Registerformat.  
  
```  
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMode`  
 `TRUE`So aktivieren Sie automatisch ausgeblendet; `FALSE` reguläre Andockmodus aktivieren.  
  
 [in] `dwAlignment`  
 Gibt die Ausrichtung des Bereichs automatisch im Hintergrund erstellt werden soll. Eine Liste der möglichen Werte finden Sie unter [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment).  
  
 [in] [out]`pCurrAutoHideBar`  
 Ein Zeiger auf die aktuelle automatisch im Hintergrund-Symbolleiste. Kann `NULL`.  
  
 [in] `bUseTimer`  
 Gibt an, ob den Effekt automatisch im Hintergrund zu verwenden, wenn der Benutzer den Bereich zum automatischen Ausblenden Modus wechselt, oder sofort Ausblenden des Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die automatisch im Hintergrund-Symbolleiste, die erstellt wird, beim Wechseln zum Modus "automatisch ausblenden" oder `NULL` Wenn keine Symbolleiste erstellt wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Benutzer die Pin-Schaltfläche, um die Seite im Registerformat automatisch ausgeblendet oder regulären Andockmodus wechseln.  
  
 Automatisch ausgeblendet wird für jede abnehmbare Bereich in dem Fenster im Registerkartenformat festgelegt. Bereiche, die nicht lösbare werden ignoriert. Weitere Informationen finden Sie unter [Mfcbasetabctrl](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach).  
  
 Rufen Sie diese Methode, um ein Fenster mit Registerkarten programmgesteuert in automatisch im Hintergrund-Modus zu wechseln. Der Bereich muss an das Hauptrahmenfenster angedockt werden ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) muss einen gültigen Zeiger auf Zurückgeben der [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)

