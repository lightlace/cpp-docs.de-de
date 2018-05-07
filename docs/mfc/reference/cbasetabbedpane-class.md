---
title: CBaseTabbedPane-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CBaseTabbedPane [MFC], AddTab
- CBaseTabbedPane [MFC], AllowDestroyEmptyTabbedPane
- CBaseTabbedPane [MFC], ApplyRestoredTabInfo
- CBaseTabbedPane [MFC], CanFloat
- CBaseTabbedPane [MFC], CanSetCaptionTextToTabName
- CBaseTabbedPane [MFC], ConvertToTabbedDocument
- CBaseTabbedPane [MFC], DetachPane
- CBaseTabbedPane [MFC], EnableSetCaptionTextToTabName
- CBaseTabbedPane [MFC], FillDefaultTabsOrderArray
- CBaseTabbedPane [MFC], FindBarByTabNumber
- CBaseTabbedPane [MFC], FindPaneByID
- CBaseTabbedPane [MFC], FloatTab
- CBaseTabbedPane [MFC], GetDefaultTabsOrder
- CBaseTabbedPane [MFC], GetFirstVisibleTab
- CBaseTabbedPane [MFC], GetMinSize
- CBaseTabbedPane [MFC], GetPaneIcon
- CBaseTabbedPane [MFC], GetPaneList
- CBaseTabbedPane [MFC], GetTabArea
- CBaseTabbedPane [MFC], GetTabsNum
- CBaseTabbedPane [MFC], GetUnderlyingWindow
- CBaseTabbedPane [MFC], GetVisibleTabsNum
- CBaseTabbedPane [MFC], HasAutoHideMode
- CBaseTabbedPane [MFC], IsHideSingleTab
- CBaseTabbedPane [MFC], RecalcLayout
- CBaseTabbedPane [MFC], RemovePane
- CBaseTabbedPane [MFC], SetAutoDestroy
- CBaseTabbedPane [MFC], SetAutoHideMode
- CBaseTabbedPane [MFC], ShowTab
ms.assetid: f22c0080-5b29-4a0a-8f74-8f0a4cd2dbcf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d628758f19c36112bf896e11c97df3e1f92cbc47
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cbasetabbedpane-class"></a>CBaseTabbedPane-Klasse
Erweitert die Funktionalität von [CDockablePane Class](../../mfc/reference/cdockablepane-class.md) , um die Erstellung von Fenstern im Registerkartenformat zu unterstützen  
  
## <a name="syntax"></a>Syntax  
  
```  
class CBaseTabbedPane : public CDockablePane  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CBaseTabbedPane::CBaseTabbedPane`|Standardkonstruktor|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[Cbasetabbedpane:: addTab](#addtab)|Fügt eine neue Registerkarte zu einem Bereich mit Registerkarten.|  
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Gibt an, ob es sich bei einem leeren Bereich im Registerkartenformat gelöscht werden kann.|  
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|Wendet die Einstellungen, die aus der Registrierung, um einen Bereich im Registerkartenformat geladen werden.|  
|[CBaseTabbedPane::CanFloat](#canfloat)|Bestimmt, ob im Bereich verschieben kann. (Überschreibt [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|  
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Bestimmt, ob die Beschriftung für den Bereich im Registerkartenformat derselben Text als aktive Registerkarte angezeigt werden soll.|  
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(Überschreibt [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|  
|[Cbasetabbedpane:: Detachpane](#detachpane)|Konvertiert einen oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumenten an.|  
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|Aktiviert oder deaktiviert die Möglichkeit der Bereich im Registerkartenformat, Beschriftungstext mit den Bezeichnungstext auf der Registerkarte "aktiv" zu synchronisieren.|  
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|Stellt die internen Aktivierreihenfolge Standardstatus wieder her.|  
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|Gibt einen Bereich, der in einer Registerkarte befindet, während die Registerkarte "durch einen nullbasierten Registerkartenindex identifiziert wird.|  
|||  
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|Gibt einen Bereich, der durch den Bereich-ID identifiziert wird|  
|[Cbasetabbedpane:: Floattab](#floattab)|Hebt die Verankerung eines Bereichs auf, aber nur, wenn der Bereich sich auf einer lösbaren Registerkarte befindet.|  
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|Gibt die standardmäßige Reihenfolge der Registerkarten im Bereich zurück.|  
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|Ruft einen Zeiger auf die erste angezeigten Registerkarte ab.|  
|[CBaseTabbedPane::GetMinSize](#getminsize)|Ruft den minimal zulässigen Größe für den Bereich ab. (Überschreibt [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|  
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|Gibt ein Handle auf das Symbol "Bereich" zurück. (Überschreibt [CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|  
|[CBaseTabbedPane::GetPaneList](#getpanelist)|Gibt eine Liste von Bereichen, die enthalten sind in den Bereich im Registerkartenformat zurück.|  
|[CBaseTabbedPane::GetTabArea](#gettabarea)|Gibt die umgebenden Rechtecken für die oberen und unteren Registerkarte Bereiche zurück.|  
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|Gibt die Anzahl der Registerkarten in einem Registerkartenfenster zurück.|  
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|Ruft den zugrunde liegenden (umschlossene) "Verwaltung" ab.|  
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|Gibt die Anzahl der angezeigten Registerkarten zurück.|  
|[Cbasetabbedpane:: Hasautohidemode](#hasautohidemode)|Bestimmt, ob der Bereich im Registerkartenformat zum automatischen Ausblenden Modus umgeschaltet werden kann.|  
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|Bestimmt, ob der Bereich im Registerkartenformat ausgeblendet ist, wenn nur eine Registerkarte angezeigt wird.|  
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Wird intern verwendet, während der Serialisierung.|  
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|Berechnet die Layoutinformationen für den Bereich an. (Überschreibt [cpane:: RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|  
|[CBaseTabbedPane::RemovePane](#removepane)|Entfernt einen Bereich aus dem Fenster im Registerkartenformat.|  
|`CBaseTabbedPane::SaveSiblingBarIDs`|Wird intern verwendet, während der Serialisierung.|  
|`CBaseTabbedPane::Serialize`|(Überschreibt [CDockablePane:: SaveState](http://msdn.microsoft.com/en-us/09787e59-e446-4e76-894b-206d303dcfd6).)|  
|`CBaseTabbedPane::SerializeTabWindow`|Wird intern verwendet, während der Serialisierung.|  
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|Bestimmt, ob die Steuerleiste im Registerkartenformat automatisch zerstört wird.|  
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|Schaltet zwischen andockbare Bereich angezeigt und automatisch im Hintergrund-Modus. (Überschreibt [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|  
|[CBaseTabbedPane::ShowTab](#showtab)|Anzeigen oder ausblenden eine Registerkarte.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse ist eine abstrakte Klasse und kann nicht instanziiert werden. Es implementiert die Dienste, die für alle Arten von Bereiche im Registerkartenformat gemeinsam verwendet werden.  
  
 Die Bibliothek enthält derzeit zwei Bereich im Registerkartenformat an abgeleitete Klassen: [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md) und [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).  
  
 Ein `CBaseTabbedPane` Objekt umschließt einen Zeiger auf eine [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) Objekt. [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) wird dann ein untergeordnetes Fenster im Registerkartenformat im Bereich.  
  
 Weitere Informationen dazu, wie Bereiche im Registerkartenformat zu erstellen, finden Sie unter [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md), [CTabbedPane Klasse](../../mfc/reference/ctabbedpane-class.md), und [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md)  
  
 [CPane](../../mfc/reference/cpane-class.md)  
  
 [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 `CBaseTabbedPane`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxBaseTabbedPane.h  
  
##  <a name="addtab"></a>  Cbasetabbedpane:: addTab  
 Fügt eine neue Registerkarte zu einem Bereich mit Registerkarten.  
  
```  
virtual BOOL AddTab(
    CWnd* pNewBar,  
    BOOL bVisible = TRUE,  
    BOOL bSetActive = TRUE,  
    BOOL bDetachable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out] `pNewBar`  
 Ein Zeiger auf den Bereich hinzufügen. This-Zeiger kann ungültig werden, nachdem Sie diese Methode aufrufen. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 [in] `bVisible`  
 `TRUE` um die Registerkarte sichtbar zu machen; andernfalls `FALSE`.  
  
 [in] `bSetActive`  
 `TRUE` auf der Registerkarte "als aktive Registerkarte festzulegen; andernfalls `FALSE`.  
  
 [in] `bDetachable`  
 `TRUE` um die Registerkarte lösbar festzulegen; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich als eine Registerkarte erfolgreich hinzugefügt wurde und nicht im Prozess zerstört wurde. `FALSE` Wenn der Bereich, der hinzugefügt wird ein Objekt des Typs wird `CBaseTabbedPane`. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich als neue Registerkarte auf einen Bereich im Registerkartenformat hinzufügen. Wenn `pNewBar` verweist auf ein Objekt des Typs `CBaseTabbedPane`, werden alle Registerkarten auf der Seite im Registerformat kopiert und dann `pNewBar` zerstört wird. Folglich `pNewBar` wird ein ungültiger Zeiger und sollte nicht verwendet werden.  
  
##  <a name="allowdestroyemptytabbedpane"></a>  CBaseTabbedPane::AllowDestroyEmptyTabbedPane  
 Gibt an, ob es sich bei einem leeren Bereich im Registerkartenformat gelöscht werden kann.  
  
```  
virtual BOOL AllowDestroyEmptyTabbedPane() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn Sie einen leeren Bereich im Registerkartenformat zerstört werden kann. andernfalls `FALSE`. Gibt die standardmäßige Implementierung immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen leeren Bereich im Registerkartenformat nicht zulässig ist, zerstört werden, wird der Bereich von Framework stattdessen ausgeblendet.  
  
##  <a name="applyrestoredtabinfo"></a>  CBaseTabbedPane::ApplyRestoredTabInfo  
 Lädt Einstellungen aus der Registrierung, und wendet diese auf einen Bereich im Registerkartenformat.  
  
```  
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bUseTabIndexes`  
 Dieser Parameter wird intern vom Framework verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird vom Framework aufgerufen, wenn es Andocken Zustandsinformationen aus der Registrierung erneut geladen. Die Methode ruft Informationen zur Reihenfolge der Registerkarten und Namen von Registern in einen Bereich im Registerkartenformat ab.  
  
##  <a name="canfloat"></a>  CBaseTabbedPane::CanFloat  
 Gibt an, ob der Bereich im Registerkartenformat float kann.  
  
```  
virtual BOOL CanFloat() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich float kann; andernfalls `FALSE`.  
  
##  <a name="cansetcaptiontexttotabname"></a>  CBaseTabbedPane::CanSetCaptionTextToTabName  
 Bestimmt, ob die Beschriftung für den Bereich im Registerkartenformat derselben Text als aktive Registerkarte angezeigt werden soll.  
  
```  
virtual BOOL CanSetCaptionTextToTabName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn Sie der Beschriftungstext Bereich im Registerkartenformat auf den Text der aktiven Registerkarte festgelegt ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Methode wird verwendet, um zu bestimmen, ob der Text auf der Seite im Registerformat Beschriftung dupliziert die Bezeichnung der aktiven Registerkarte angezeigt. Sie aktivieren oder deaktivieren Sie diese Funktionalität durch Aufrufen von [CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname).  
  
##  <a name="converttotabbeddocument"></a>  CBaseTabbedPane::ConvertToTabbedDocument  
 Konvertiert einen oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumenten an.  
  
```  
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bActiveTabOnly`  
 Geben Sie bei der Konvertierung eines Bereich im Registerkartenformat `TRUE` nur die aktive Registerkarte zu konvertieren. Geben Sie `FALSE` aller Registerkarten im Bereich zu konvertieren.  
  
##  <a name="detachpane"></a>  Cbasetabbedpane:: Detachpane  
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
 Boolescher Parameter, der angibt, ob das Framework der Bereich ausgeblendet, nachdem sie getrennt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn das Framework erfolgreich Bereich trennt; `FALSE` Wenn `pBar` ist `NULL` oder bezieht sich auf einen Bereich, der nicht im Bereich im Registerkartenformat ist.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework gleitet der getrennten Bereich nach Möglichkeit. Weitere Informationen finden Sie unter [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).  
  
##  <a name="enablesetcaptiontexttotabname"></a>  CBaseTabbedPane::EnableSetCaptionTextToTabName  
 Aktiviert oder deaktiviert die Möglichkeit der Bereich im Registerkartenformat, Beschriftungstext mit den Bezeichnungstext auf der Registerkarte "aktiv" zu synchronisieren.  
  
```  
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE` die Beschriftung im Registerformat mit der aktiven Registerkarte Beschriftung synchronisiert; andernfalls `FALSE`.  
  
##  <a name="filldefaulttabsorderarray"></a>  CBaseTabbedPane::FillDefaultTabsOrderArray  
 Stellt die internen Aktivierreihenfolge Standardstatus wieder her.  
  
```  
void FillDefaultTabsOrderArray();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode wird aufgerufen, wenn das Framework eine Outlook-Leiste auf einen Ausgangszustand wiederherstellt.  
  
##  <a name="findpanebyid"></a>  CBaseTabbedPane::FindPaneByID  
 Gibt einen Bereich, der durch den Bereich-ID gekennzeichnet zurück  
  
```  
virtual CWnd* FindPaneByID(UINT uBarID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uBarID`  
 Gibt die ID des Bereichs zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf den Bereich, wenn es gefunden wurde; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode vergleicht alle Registerkarten im Bereich, und gibt die Methode mit der die angegebene ID der `uBarID` Parameter.  
  
##  <a name="findbarbytabnumber"></a>  CBaseTabbedPane::FindBarByTabNumber  
 Gibt einen Bereich, der auf einer Registerkarte befindet.  
  
```  
virtual CWnd* FindBarByTabNumber(
    int nTabNum,  
    BOOL bGetWrappedBar = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTabNum`  
 Gibt den nullbasierten Index des abzurufenden der Registerkarte "-".  
  
 [in] `bGetWrappedBar`  
 `TRUE` um das zugrunde liegende (umschlossene) Fenster im Bereich anstatt im Bereich selbst zurückgegeben. andernfalls `FALSE`. Dies gilt nur für Bereiche, die von abgeleiteten [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md).  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Bereich; gefunden wurde ein gültiger Zeiger auf den Bereich, der zu suchenden zurückgegeben wird, andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Abrufen von Bereich befinden, auf der Registerkarte gemäß der `nTabNum` Parameter.  
  
##  <a name="floattab"></a>  Cbasetabbedpane:: Floattab  
 Hebt die Verankerung eines Bereichs auf, aber nur, wenn der Bereich sich auf einer lösbaren Registerkarte befindet.  
  
```  
virtual BOOL FloatTab(
    CWnd* pBar,  
    int nTabID,  
    AFX_DOCK_METHOD dockMethod,  
    BOOL bHide = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out] `pBar`  
 Ein Zeiger auf den Bereich, um "float".  
  
 [in] `nTabID`  
 Gibt den nullbasierten Index der Registerkarte "float".  
  
 [in] `dockMethod`  
 Gibt die Methode zu verwenden, um den Bereich "float" auszuführen. Weitere Informationen finden Sie im Abschnitt "Hinweise".  
  
 [in] `bHide`  
 `TRUE` der Bereich ausgeblendet vor Gleitkommawert; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich umfließt; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um einen Bereich zu verschieben, der sich derzeit in einer lösbaren Registerkarte befindet.  
  
 Wenn Sie einen Bereich programmgesteuert trennen möchten, geben Sie `DM_SHOW` für die `dockMethod` Parameter. Wenn Sie float-Bereich in der gleichen Position, in denen umfließt es zuvor, angeben möchten `DM_DBL_CLICK` als die `dockMethod` Parameter.  
  
##  <a name="getdefaulttabsorder"></a>  CBaseTabbedPane::GetDefaultTabsOrder  
 Gibt die standardmäßige Reihenfolge der Registerkarten im Bereich zurück.  
  
```  
const CArray<int,int>& GetDefaultTabsOrder();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CArray` Objekt, das die Standardreihenfolge der Registerkarten im Bereich angibt.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn eine Outlook-Leiste auf einen Ausgangszustand zurückgesetzt wird.  
  
##  <a name="getfirstvisibletab"></a>  CBaseTabbedPane::GetFirstVisibleTab  
 Ruft einen Zeiger auf die erste angezeigten Registerkarte ab.  
  
```  
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iTabNum`  
 Ein Verweis auf eine ganze Zahl. Diese Methode schreibt dem nullbasierten Index des ersten angezeigten Registerkarte an diesen Parameter, oder -1, wenn kein Wert angezeigt, dass die Registerkarte gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg, ein Zeiger auf den ersten angezeigten Registerkarte; andernfalls `NULL`.  
  
##  <a name="getminsize"></a>  CBaseTabbedPane::GetMinSize  
 Ruft den minimal zulässigen Größe für den Bereich ab.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `size`  
 Ein `CSize` -Objekt, das mit dem niedrigsten zulässigen Größe gefüllt ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der einheitlichen Handhabung der Größen der minimalen Bereich aktiv ist ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), `size` mit dem niedrigsten zulässigen Größe für die aktive Registerkarte gefüllt ist. Andernfalls `size` gefüllt wird, bei dem Rückgabewert von [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpaneicon"></a>  CBaseTabbedPane::GetPaneIcon  
 Ruft den minimal zulässigen Größe für den Bereich ab.  
  
```  
virtual void GetMinSize(CSize& size) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `size`  
 Ein `CSize` -Objekt, das mit dem niedrigsten zulässigen Größe gefüllt ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der einheitlichen Handhabung der Größen der minimalen Bereich aktiv ist ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), `size` mit dem niedrigsten zulässigen Größe für die aktive Registerkarte gefüllt ist. Andernfalls `size` gefüllt wird, bei dem Rückgabewert von [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).  
  
##  <a name="getpanelist"></a>  CBaseTabbedPane::GetPaneList  
 Gibt eine Liste von Bereichen, die enthalten sind in den Bereich im Registerkartenformat zurück.  
  
```  
virtual void GetPaneList(
    CObList& lst,  
    CRuntimeClass* pRTCFilter = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `lst`  
 Ein `CObList` , gefüllt wird, mit der Bereiche, in den Bereich mit Registerkarten enthalten sind.  
  
 [in] `pRTCFilter`  
 Ist er nicht `NULL`, die zurückgegebene Liste enthält nur die Bereiche, die dem angegebenen Common Language Runtime-Klasse.  
  
##  <a name="gettabarea"></a>  CBaseTabbedPane::GetTabArea  
 Gibt die umgebenden Rechtecken für die oberen und unteren Registerkarte Bereiche zurück.  
  
```  
virtual void GetTabArea(
    CRect& rectTabAreaTop,  
    CRect& rectTabAreaBottom) const = 0;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `rectTabAreaTop`  
 Empfängt die Bildschirmkoordinaten des oberen Registerkartenbereichs.  
  
 [out] `rectTabAreaBottom`  
 Empfängt die Bildschirmkoordinaten des im unteren Bereich der Registerkarte ".  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die umschließende Rechtecke, in Bildschirmkoordinaten, für die oberen und unteren Registerkarte Bereiche zu bestimmen.  
  
##  <a name="gettabsnum"></a>  CBaseTabbedPane::GetTabsNum  
 Gibt die Anzahl der Registerkarten in einem Registerkartenfenster zurück.  
  
```  
virtual int GetTabsNum() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Registerkarten im Bereich im Registerkartenformat.  
  
##  <a name="getunderlyingwindow"></a>  CBaseTabbedPane::GetUnderlyingWindow  
 Ruft den zugrunde liegenden (umschlossene) "Verwaltung" ab.  
  
```  
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die zugrunde liegenden "Verwaltung".  
  
##  <a name="getvisibletabsnum"></a>  CBaseTabbedPane::GetVisibleTabsNum  
 Gibt die Anzahl eingeblendeter Registerkarten zurück.  
  
```  
virtual int GetVisibleTabsNum() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl eingeblendeter Registerkarten, die größer als oder gleich 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um die Anzahl eingeblendeter Registerkarten im Bereich im Registerkartenformat zu bestimmen.  
  
##  <a name="hasautohidemode"></a>  Cbasetabbedpane:: Hasautohidemode  
 Bestimmt, ob der Bereich im Registerkartenformat automatisch in den Hintergrundmodus gewechselt werden kann.  
  
```  
virtual BOOL HasAutoHideMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich in den Hintergrundmodus gewechselt werden kann; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn in den Hintergrundmodus deaktiviert ist, wird keine Schaltfläche "Pin" auf der Seite im Registerformat Beschriftung angezeigt.  
  
##  <a name="ishidesingletab"></a>  CBaseTabbedPane::IsHideSingleTab  
 Bestimmt, ob der Bereich im Registerkartenformat ausgeblendet ist, wenn nur eine Registerkarte angezeigt wird.  
  
```  
virtual BOOL IsHideSingleTab() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die "Verwaltung" nicht angezeigt wird, wenn nur eine eingeblendete Registerkarte vorhanden ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Bereich nicht angezeigt wird, da nur eine Registerkarte geöffnet ist, können Sie diese Methode, um zu bestimmen, ob der Bereich im Registerkartenformat ordnungsgemäß arbeitet aufrufen.  
  
##  <a name="removepane"></a>  CBaseTabbedPane::RemovePane  
 Entfernt einen Bereich aus dem Fenster im Registerkartenformat.  
  
```  
virtual BOOL RemovePane(CWnd* pBar);
```  
  
### <a name="parameters"></a>Parameter  
 [in] [out] `pBar`  
 Ein Zeiger auf den Bereich, um aus dem Fenster im Registerkartenformat zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn der Bereich aus dem Fenster im Registerkartenformat erfolgreich entfernt wurde und Bereich im Registerkartenformat noch gültig ist. `FALSE` Wenn der letzte Bereich aus dem Fenster im Registerkartenformat entfernt wurde und der Bereich im Registerkartenformat zerstört werden soll. Wenn der Rückgabewert ist `FALSE`, Bereich im Registerkartenformat nicht mehr verwenden.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Entfernen von des Bereich gemäß der `pBar` Parameter aus dem Fenster im Registerkartenformat.  
  
##  <a name="setautodestroy"></a>  CBaseTabbedPane::SetAutoDestroy  
 Bestimmt, ob die Steuerleiste im Registerkartenformat automatisch zerstört wird.  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bAutoDestroy`  
 `TRUE` Wenn der Bereich im Registerkartenformat dynamisch erstellt wurde, und Sie nicht die Lebensdauer steuern sind; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Legen Sie den Modus für automatische zu zerstören `TRUE` , wenn Sie einen Bereich im Registerkartenformat dynamisch erstellen und Sie seine Lebensdauer nicht steuern. Wenn automatische zerstören Modus ist `TRUE`, wird der Bereich im Registerkartenformat automatisch durch das Framework zerstört werden.  
  
##  <a name="showtab"></a>  CBaseTabbedPane::ShowTab  
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
 Ein Zeiger auf den Bereich, um Sie anzuzeigen oder auszublenden.  
  
 [in] `bShow`  
 `TRUE` um den Bereich anzuzeigen; `FALSE` So blenden Sie den Bereich aus.  
  
 [in] `bDelay`  
 `TRUE` um die Anpassung von der Registerkartenlayout verzögern; andernfalls `FALSE`.  
  
 [in] `bActivate`  
 `TRUE` auf der Registerkarte "als aktive Registerkarte festzulegen; andernfalls `FALSE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die Registerkarte "wurde entweder angezeigt oder ausgeblendet; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Methode aufrufen, ein Bereich entweder ein- oder ausgeblendet wird, abhängig vom Wert der `bShow` Parameter. Wenn Sie einer Registerkarte ausblenden, und es die letzte, eingeblendete Registerkarte in der zugrunde liegenden "Verwaltung ist", wird der Bereich im Registerkartenformat ausgeblendet. Wenn Sie eine Registerkarte anzeigen, wenn zuvor keine Registerkarten angezeigt wurden, wird der Bereich im Registerkartenformat angezeigt.  
  
##  <a name="recalclayout"></a>  CBaseTabbedPane::RecalcLayout  
 Berechnet die Layoutinformationen für den Bereich an.  
  
```  
virtual void RecalcLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Bereich unverankert ist, informiert diese Methode das Framework den Bereich, um die aktuelle Größe der kleinen Rahmenfenster Größe.  
  
 Wenn der Bereich angedockt ist, wird diese Methode keine Aktion ausgeführt.  
  
##  <a name="setautohidemode"></a>  CBaseTabbedPane::SetAutoHideMode  
 Legt den automatischen Ausblendemodus für lösbare Bereiche in den Bereich mit Registerkarten fest.  
  
```  
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,  
    DWORD dwAlignment,  
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,  
    BOOL bUseTimer = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMode`  
 `TRUE` So aktivieren Sie den automatischen Ausblendemodus; `FALSE` reguläre Andockmodus zu aktivieren.  
  
 [in] `dwAlignment`  
 Gibt die Ausrichtung des Bereichs automatisch im Hintergrund erstellt werden soll. Eine Liste der möglichen Werte finden Sie unter [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment).  
  
 [in] [out] `pCurrAutoHideBar`  
 Ein Zeiger auf der Symbolleiste des aktuellen automatisch im Hintergrund. Kann `NULL`.  
  
 [in] `bUseTimer`  
 Gibt an, ob den automatisch ausblendbaren Effekt zu verwenden, wenn der Benutzer den Bereich in den automatischen Ausblendemodus wechselt oder den Bereich unmittelbar ausblenden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die automatisch ausblendbare-Symbolleiste, die erstellt wird, wenn der Wechsel zu automatischen Ausblendemodus oder `NULL` , wenn keine Symbolleiste erstellt wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Methode auf, wenn ein Benutzer die Pin-Schaltfläche, um den Bereich im Registerkartenformat zu automatischen Ausblendemodus oder zu regulären Andockmodus wechseln auswählt.  
  
 Automatischen Ausblendemodus ist für jede lösbare Bereich im Bereich im Registerkartenformat festgelegt. Bereiche, die nicht lösbare sind, werden ignoriert. Weitere Informationen finden Sie unter [Mfcbasetabctrl](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach).  
  
 Rufen Sie diese Methode, um einen Bereich im Registerkartenformat zum automatischen Ausblendemodus programmgesteuert zu wechseln. Der Bereich angedockt werden muss, an das Hauptrahmenfenster ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) muss einen gültigen Zeiger auf Zurückgeben der [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)
