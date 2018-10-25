---
title: CBaseTabbedPane-Klasse | Microsoft-Dokumentation
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
ms.openlocfilehash: addbc7c81c8cd38f44b7b1004c0b4e23ca183ecb
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067319"
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
|[Cbasetabbedpane:: addTab](#addtab)|Fügt eine neue Registerkarte zu einem Bereich im Registerkartenformat.|
|[CBaseTabbedPane::AllowDestroyEmptyTabbedPane](#allowdestroyemptytabbedpane)|Gibt an, ob es sich bei einem leeren Bereich im Registerkartenformat zerstört werden kann.|
|[CBaseTabbedPane::ApplyRestoredTabInfo](#applyrestoredtabinfo)|Registerkarte Einstellungen, die aus der Registrierung, um einen Bereich im Registerkartenformat geladen werden angewendet.|
|[CBaseTabbedPane::CanFloat](#canfloat)|Bestimmt, ob der Bereich wechseln kann. (Überschreibt [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).)|
|[CBaseTabbedPane::CanSetCaptionTextToTabName](#cansetcaptiontexttotabname)|Bestimmt, ob die Beschriftung für den Bereich im Registerkartenformat den gleichen Text als aktive Registerkarte angezeigt werden soll.|
|[CBaseTabbedPane::ConvertToTabbedDocument](#converttotabbeddocument)|(Überschreibt [CDockablePane::ConvertToTabbedDocument](../../mfc/reference/cdockablepane-class.md#converttotabbeddocument).)|
|[Cbasetabbedpane:: Detachpane](#detachpane)|Konvertiert einen oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumenten.|
|[CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname)|Aktiviert oder deaktiviert die Möglichkeit der Bereich im Registerkartenformat, Beschriftungstext mit dem Bezeichnungstext auf der aktiven Registerkarte zu synchronisieren.|
|[CBaseTabbedPane::FillDefaultTabsOrderArray](#filldefaulttabsorderarray)|Stellt die internen Aktivierreihenfolge zu einem Standardzustand.|
|[CBaseTabbedPane::FindBarByTabNumber](#findbarbytabnumber)|Gibt einen Bereich, der auf einer Registerkarte befindet, wenn die Registerkarte "durch einen nullbasierten Registerkartenindex identifiziert wird.|
|||
|[CBaseTabbedPane::FindPaneByID](#findpanebyid)|Gibt einen Bereich, der durch die im Bereich-ID identifiziert wird|
|[Cbasetabbedpane:: Floattab](#floattab)|Hebt die Verankerung eines Bereichs auf, aber nur, wenn der Bereich sich auf einer lösbaren Registerkarte befindet.|
|[CBaseTabbedPane::GetDefaultTabsOrder](#getdefaulttabsorder)|Gibt die Standardreihenfolge der Registerkarten im Bereich zurück.|
|[CBaseTabbedPane::GetFirstVisibleTab](#getfirstvisibletab)|Ruft einen Zeiger auf die erste angezeigte Registerkarte ab.|
|[CBaseTabbedPane::GetMinSize](#getminsize)|Ruft den minimal zulässigen Größe für den Bereich ab. (Überschreibt [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).)|
|[CBaseTabbedPane::GetPaneIcon](#getpaneicon)|Gibt ein Handle auf das Symbol "Bereich" zurück. (Überschreibt [CBasePane::GetPaneIcon](../../mfc/reference/cbasepane-class.md#getpaneicon).)|
|[CBaseTabbedPane::GetPaneList](#getpanelist)|Gibt eine Liste von Bereichen, die enthalten sind in den Bereich im Registerkartenformat zurück.|
|[CBaseTabbedPane::GetTabArea](#gettabarea)|Gibt zurück, das die umschließenden Rechtecke für die oberen und unteren Registerkarte Bereiche.|
|[CBaseTabbedPane::GetTabsNum](#gettabsnum)|Gibt die Anzahl der Registerkarten in einem Registerkartenfenster zurück.|
|[CBaseTabbedPane::GetUnderlyingWindow](#getunderlyingwindow)|Ruft die zugrunde liegende Registerkartenfenster (umschlossene) ab.|
|[CBaseTabbedPane::GetVisibleTabsNum](#getvisibletabsnum)|Gibt die Anzahl der angezeigten Registerkarten zurück.|
|[Cbasetabbedpane:: Hasautohidemode](#hasautohidemode)|Bestimmt, ob der Bereich im Registerkartenformat zum Modus "automatisch ausblenden" umgeschaltet werden kann.|
|[CBaseTabbedPane::IsHideSingleTab](#ishidesingletab)|Bestimmt, ob der Bereich im Registerkartenformat ausgeblendet ist, wenn nur eine Registerkarte angezeigt wird.|
|`CBaseTabbedPane::LoadSiblingPaneIDs`|Wird intern verwendet, während der Serialisierung.|
|[CBaseTabbedPane::RecalcLayout](#recalclayout)|Berechnet die Layoutinformationen für den Bereich an. (Überschreibt [cpane:: RecalcLayout](../../mfc/reference/cpane-class.md#recalclayout).)|
|[CBaseTabbedPane::RemovePane](#removepane)|Entfernt einen Bereich im Bereich im Registerkartenformat.|
|`CBaseTabbedPane::SaveSiblingBarIDs`|Wird intern verwendet, während der Serialisierung.|
|`CBaseTabbedPane::Serialize`|(Überschreibt [CDockablePane:: SaveState](cdockablepane-class.md).)|
|`CBaseTabbedPane::SerializeTabWindow`|Wird intern verwendet, während der Serialisierung.|
|[CBaseTabbedPane::SetAutoDestroy](#setautodestroy)|Bestimmt, ob die Steuerleiste im Registerkartenformat automatisch zerstört wird.|
|[CBaseTabbedPane::SetAutoHideMode](#setautohidemode)|Schaltet die andockbare Bereich zwischen angezeigt und automatisch ausgeblendet. (Überschreibt [CDockablePane::SetAutoHideMode](../../mfc/reference/cdockablepane-class.md#setautohidemode).)|
|[CBaseTabbedPane::ShowTab](#showtab)|Anzeigen oder ausblenden eine Registerkarte.|

## <a name="remarks"></a>Hinweise

Diese Klasse ist eine abstrakte Klasse und kann nicht instanziiert werden. Es implementiert die Dienste, die für alle Arten von Seiten im Registerformat gelten.

Die Bibliothek enthält derzeit zwei Bereich im Registerkartenformat an abgeleitete Klassen: [CTabbedPane-Klasse](../../mfc/reference/ctabbedpane-class.md) und [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).

Ein `CBaseTabbedPane` Objekt umschließt einen Zeiger auf eine [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) Objekt. [CMFCBaseTabCtrl-Klasse](../../mfc/reference/cmfcbasetabctrl-class.md) dann wird ein untergeordnetes Fenster von der Seite im Registerformat.

Weitere Informationen zum Erstellen von Seiten im Registerformat finden Sie unter [CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md), [CTabbedPane-Klasse](../../mfc/reference/ctabbedpane-class.md), und [CMFCOutlookBar-Klasse](../../mfc/reference/cmfcoutlookbar-class.md).

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

Fügt eine neue Registerkarte zu einem Bereich im Registerkartenformat.

```
virtual BOOL AddTab(
    CWnd* pNewBar,
    BOOL bVisible = TRUE,
    BOOL bSetActive = TRUE,
    BOOL bDetachable = TRUE);
```

### <a name="parameters"></a>Parameter

*pNewBar*<br/>
[in, out] Ein Zeiger auf den Bereich, um Sie hinzuzufügen. This-Zeiger kann ungültig werden, nachdem Sie diese Methode aufrufen. Weitere Informationen finden Sie im Abschnitt "Hinweise".

*bVisible*<br/>
[in] True, um die Registerkarte sichtbar zu machen. andernfalls "false".

*bSetActive*<br/>
[in] True, um der Registerkarte der aktiven Registerkarte machen. andernfalls "false".

*bDetachable*<br/>
[in] True, damit die lösbaren Registerkarte; andernfalls "false".

### <a name="return-value"></a>Rückgabewert

"True", wenn der Bereich erfolgreich als Registerkarte hinzugefügt wurde und wurde im Prozess nicht zerstört. FALSE, wenn der Bereich, der hinzugefügt wird ein Objekt des Typs ist `CBaseTabbedPane`. Weitere Informationen finden Sie im Abschnitt "Hinweise".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um einen Bereich als eine neue Registerkarte in einem Bereich im Registerkartenformat hinzugefügt. Wenn *pNewBar* verweist auf ein Objekt des Typs `CBaseTabbedPane`, werden alle Registerkarten auf der Seite im Registerformat kopiert und dann *pNewBar* zerstört wird. Daher *pNewBar* wird ein ungültiger Zeiger und sollte nicht verwendet werden.

##  <a name="allowdestroyemptytabbedpane"></a>  CBaseTabbedPane::AllowDestroyEmptyTabbedPane

Gibt an, ob es sich bei einem leeren Bereich im Registerkartenformat zerstört werden kann.

```
virtual BOOL AllowDestroyEmptyTabbedPane() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn Sie einen leeren Bereich im Registerkartenformat zerstört werden kann. andernfalls "false". Immer die Standardimplementierung gibt "true" zurück.

### <a name="remarks"></a>Hinweise

Wenn Sie einen leeren Bereich im Registerkartenformat nicht zulässig ist, zerstört werden soll, wird das Framework stattdessen Bereich ausgeblendet.

##  <a name="applyrestoredtabinfo"></a>  CBaseTabbedPane::ApplyRestoredTabInfo

Lädt Einstellungen aus der Registrierung, und klicken Sie auf einen Bereich im Registerkartenformat angewendet.

```
virtual void ApplyRestoredTabInfo(BOOL bUseTabIndexes = FALSE);
```

### <a name="parameters"></a>Parameter

*bUseTabIndexes*<br/>
[in] Dieser Parameter wird intern vom Framework verwendet.

### <a name="remarks"></a>Hinweise

Diese Methode wird vom Framework aufgerufen, wenn es Andocken Zustandsinformationen aus der Registrierung erneut geladen. Die Methode ruft Informationen über die Tab-Reihenfolge und die Namen von Registern in einem Bereich im Registerkartenformat ab.

##  <a name="canfloat"></a>  CBaseTabbedPane::CanFloat

Gibt an, ob die Seite im Registerformat wechseln kann.

```
virtual BOOL CanFloat() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich wechseln kann. andernfalls "false".

##  <a name="cansetcaptiontexttotabname"></a>  CBaseTabbedPane::CanSetCaptionTextToTabName

Bestimmt, ob die Beschriftung für den Bereich im Registerkartenformat den gleichen Text als aktive Registerkarte angezeigt werden soll.

```
virtual BOOL CanSetCaptionTextToTabName() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn es sich bei der Beschriftungstext der Bereich im Registerkartenformat auf den Text der aktiven Registerkarte festgelegt ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Die Methode wird verwendet, um festzustellen, ob der Text auf der Seite im Registerformat Beschriftung Duplikate die Bezeichnung der aktiven Registerkarte angezeigt. Sie können aktivieren oder deaktivieren Sie diese Funktionalität durch Aufrufen von [CBaseTabbedPane::EnableSetCaptionTextToTabName](#enablesetcaptiontexttotabname).

##  <a name="converttotabbeddocument"></a>  CBaseTabbedPane::ConvertToTabbedDocument

Konvertiert einen oder mehrere andockbare Bereiche im Registerkartenformat MDI-Dokumenten.

```
virtual void ConvertToTabbedDocument(BOOL bActiveTabOnly = TRUE);
```

### <a name="parameters"></a>Parameter

*bActiveTabOnly*<br/>
[in] Wenn Sie einen Bereich im Registerkartenformat konvertieren, geben Sie "true", um nur die aktive Registerkarte zu konvertieren. Geben Sie "false", um alle Registerkarten in den Bereich zu konvertieren.

##  <a name="detachpane"></a>  Cbasetabbedpane:: Detachpane

Trennt einen Bereich von Bereich im Registerkartenformat.

```
virtual BOOL DetachPane(
    CWnd* pBar,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
[in] Zeiger auf den Bereich zu trennen.

*bHide*<br/>
[in] Boolescher Parameter, der angibt, ob das Framework den Bereich wird ausgeblendet, nachdem sie getrennt wird.

### <a name="return-value"></a>Rückgabewert

True, wenn das Framework die im Bereich erfolgreich getrennt. FALSE, wenn *pBar* NULL ist oder bezieht sich auf einen Bereich, der nicht in den Bereich im Registerkartenformat ist.

### <a name="remarks"></a>Hinweise

Das Framework gleitet Bereich getrennt, wenn möglich. Weitere Informationen finden Sie unter [CBasePane::CanFloat](../../mfc/reference/cbasepane-class.md#canfloat).

##  <a name="enablesetcaptiontexttotabname"></a>  CBaseTabbedPane::EnableSetCaptionTextToTabName

Aktiviert oder deaktiviert die Möglichkeit der Bereich im Registerkartenformat, Beschriftungstext mit dem Bezeichnungstext auf der aktiven Registerkarte zu synchronisieren.

```
virtual void EnableSetCaptionTextToTabName(BOOL bEnable);
```

### <a name="parameters"></a>Parameter

*bAktivieren*<br/>
[in] True, um die Beschriftung für die Seite im Registerformat mit der Beschriftung für die aktive Registerkarte zu synchronisieren. andernfalls "false".

##  <a name="filldefaulttabsorderarray"></a>  CBaseTabbedPane::FillDefaultTabsOrderArray

Stellt die internen Aktivierreihenfolge zu einem Standardzustand.

```
void FillDefaultTabsOrderArray();
```

### <a name="remarks"></a>Hinweise

Diese Methode wird aufgerufen, wenn das Framework eine Outlook-Leiste in den ursprünglichen Zustand wiederherstellt.

##  <a name="findpanebyid"></a>  CBaseTabbedPane::FindPaneByID

Gibt einen Bereich, der durch den Bereich-ID identifiziert zurück

```
virtual CWnd* FindPaneByID(UINT uBarID);
```

### <a name="parameters"></a>Parameter

*uBarID*<br/>
[in] Gibt die ID des Bereichs zu suchen.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den Bereich, wenn es gefunden wurde; andernfalls NULL.

### <a name="remarks"></a>Hinweise

Diese Methode vergleicht alle Registerkarten in den Bereich und gibt das mit der ID, die gemäß der *uBarID* Parameter.

##  <a name="findbarbytabnumber"></a>  CBaseTabbedPane::FindBarByTabNumber

Gibt einen Bereich, der auf einer Registerkarte befindet.

```
virtual CWnd* FindBarByTabNumber(
    int nTabNum,
    BOOL bGetWrappedBar = FALSE);
```

### <a name="parameters"></a>Parameter

*nTabNum*<br/>
[in] Gibt an, der nullbasierte Index der abzurufenden Registerkarte.

*bGetWrappedBar*<br/>
[in] True, um das zugrunde liegende (umschlossene) Fenster im Bereich im Bereich selbst zurückgeben. andernfalls "false". Dies gilt nur für Bereiche, die von abgeleiteten [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md).

### <a name="return-value"></a>Rückgabewert

Wenn der Bereich; gefunden wird wird ein gültiger Zeiger auf den Bereich gesucht wird zurückgegeben, andernfalls NULL.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum Abrufen von im Bereich befinden, auf der Registerkarte, die gemäß der *nTabNum* Parameter.

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

*pBar*<br/>
[in, out] Ein Zeiger auf den Bereich, um "float".

*nTabID*<br/>
[in] Gibt an, der nullbasierte Index der Registerkarte "float".

*dockMethod*<br/>
[in] Gibt die Methode zu verwenden, um den Bereich "float". Weitere Informationen finden Sie im Abschnitt "Hinweise".

*bHide*<br/>
[in] True, um den Bereich ausblenden, bevor Sie die floating. andernfalls "false".

### <a name="return-value"></a>Rückgabewert

True, wenn der Bereich abgedockt. andernfalls "false".

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um einen Bereich "float", der sich derzeit in einer lösbaren Registerkarte befindet.

Wenn Sie einen Bereich programmgesteuert trennen möchten, geben Sie DM_SHOW für die *DockMethod* Parameter. Wenn den Bereich in der gleichen Position "float", in denen umfließt es zuvor, werden sollen, geben Sie DM_DBL_CLICK als die *DockMethod* Parameter.

##  <a name="getdefaulttabsorder"></a>  CBaseTabbedPane::GetDefaultTabsOrder

Gibt die Standardreihenfolge der Registerkarten im Bereich zurück.

```
const CArray<int,int>& GetDefaultTabsOrder();
```

### <a name="return-value"></a>Rückgabewert

Ein `CArray` Objekt, das die Standardreihenfolge der Registerkarten im Bereich angibt.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn eine Outlook-Leiste in den ursprünglichen Zustand zurückgesetzt wird.

##  <a name="getfirstvisibletab"></a>  CBaseTabbedPane::GetFirstVisibleTab

Ruft einen Zeiger auf die erste angezeigte Registerkarte ab.

```
virtual CWnd* GetFirstVisibleTab(int& iTabNum);
```

### <a name="parameters"></a>Parameter

*iTabNum*<br/>
[in] Ein Verweis auf eine ganze Zahl. Diese Methode schreibt dem nullbasierten Index des ersten angezeigten Registerkarte an diesen Parameter, oder -1, wenn Nein, die angezeigt, dass die Registerkarte befindet.

### <a name="return-value"></a>Rückgabewert

Bei Erfolg einen Zeiger auf die erste angezeigte Registerkarte; andernfalls NULL.

##  <a name="getminsize"></a>  CBaseTabbedPane::GetMinSize

Ruft den minimal zulässigen Größe für den Bereich ab.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parameter

*size*<br/>
[out] Ein `CSize` -Objekt, das mit den minimal zulässigen Größe gefüllt ist.

### <a name="remarks"></a>Hinweise

Wenn der einheitlichen Handhabung der Größen der minimalen Bereich aktiv ist ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *Größe* mit den minimal zulässigen Größe für die aktive Registerkarte gefüllt ist. Andernfalls *Größe* wird gefüllt, bei dem Rückgabewert der [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).

##  <a name="getpaneicon"></a>  CBaseTabbedPane::GetPaneIcon

Ruft den minimal zulässigen Größe für den Bereich ab.

```
virtual void GetMinSize(CSize& size) const;
```

### <a name="parameters"></a>Parameter

*size*<br/>
[out] Ein `CSize` -Objekt, das mit den minimal zulässigen Größe gefüllt ist.

### <a name="remarks"></a>Hinweise

Wenn der einheitlichen Handhabung der Größen der minimalen Bereich aktiv ist ( [CPane::m_bHandleMinSize](../../mfc/reference/cpane-class.md#m_bhandleminsize)), *Größe* mit den minimal zulässigen Größe für die aktive Registerkarte gefüllt ist. Andernfalls *Größe* wird gefüllt, bei dem Rückgabewert der [CPane::GetMinSize](../../mfc/reference/cpane-class.md#getminsize).

##  <a name="getpanelist"></a>  CBaseTabbedPane::GetPaneList

Gibt eine Liste von Bereichen, die enthalten sind in den Bereich im Registerkartenformat zurück.

```
virtual void GetPaneList(
    CObList& lst,
    CRuntimeClass* pRTCFilter = NULL);
```

### <a name="parameters"></a>Parameter

*lst*<br/>
[out] Ein `CObList` , gefüllt ist, mit die Bereiche, die im Bereich mit Registerkarten enthalten sind.

*pRTCFilter*<br/>
[in] Wenn er nicht NULL ist, enthält die zurückgegebene Liste nur die Bereiche, die die angegebene Runtime-Klasse.

##  <a name="gettabarea"></a>  CBaseTabbedPane::GetTabArea

Gibt zurück, das die umschließenden Rechtecke für die oberen und unteren Registerkarte Bereiche.

```
virtual void GetTabArea(
    CRect& rectTabAreaTop,
    CRect& rectTabAreaBottom) const = 0;
```

### <a name="parameters"></a>Parameter

*rectTabAreaTop*<br/>
[out] Empfängt die Bildschirmkoordinaten des oberen Registerkartenbereichs.

*rectTabAreaBottom*<br/>
[out] Empfängt die Bildschirmkoordinaten des im unteren Registerkartenbereich an.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode, um die umschließenden Rechtecke, in Bildschirmkoordinaten, für die oberen und unteren Registerkarte Bereiche zu bestimmen.

##  <a name="gettabsnum"></a>  CBaseTabbedPane::GetTabsNum

Gibt die Anzahl der Registerkarten in einem Registerkartenfenster zurück.

```
virtual int GetTabsNum() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Registerkarten im Bereich im Registerkartenformat.

##  <a name="getunderlyingwindow"></a>  CBaseTabbedPane::GetUnderlyingWindow

Ruft die zugrunde liegende Registerkartenfenster (umschlossene) ab.

```
virtual CMFCBaseTabCtrl* GetUnderlyingWindow();
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das zugrunde liegende Registerkartenfenster.

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

True, wenn der Bereich in den Hintergrundmodus gewechselt werden kann. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn in den Hintergrundmodus deaktiviert ist, wird keine Schaltfläche "anheften" auf der Seite im Registerformat Beschriftung angezeigt.

##  <a name="ishidesingletab"></a>  CBaseTabbedPane::IsHideSingleTab

Bestimmt, ob der Bereich im Registerkartenformat ausgeblendet ist, wenn nur eine Registerkarte angezeigt wird.

```
virtual BOOL IsHideSingleTab() const;
```

### <a name="return-value"></a>Rückgabewert

True, wenn das Registerkartenfenster nicht angezeigt wird, wenn nur eine eingeblendete Registerkarte vorhanden ist. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn der Bereich nicht angezeigt wird, da nur eine Registerkarte geöffnet ist, können Sie diese Methode, um zu bestimmen, ob der Bereich im Registerkartenformat ordnungsgemäß arbeitet aufrufen.

##  <a name="removepane"></a>  CBaseTabbedPane::RemovePane

Entfernt einen Bereich im Bereich im Registerkartenformat.

```
virtual BOOL RemovePane(CWnd* pBar);
```

### <a name="parameters"></a>Parameter

*pBar*<br/>
[in, out] Ein Zeiger auf den Bereich, um aus dem Fenster im Registerkartenformat zu entfernen.

### <a name="return-value"></a>Rückgabewert

"True", wenn im Bereich erfolgreich aus dem Fenster im Registerkartenformat entfernt wurde und der Bereich im Registerkartenformat noch gültig ist. "False", wenn der letzte Bereich aus dem Fenster im Registerkartenformat entfernt wurde und der Bereich im Registerkartenformat zerstört werden soll. Wenn der Rückgabewert FALSE ist, verwenden Sie nicht die Seite im Registerformat mehr.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Methode zum Entfernen der im Bereich gemäß der *pBar* Parameter aus dem Fenster im Registerkartenformat.

##  <a name="setautodestroy"></a>  CBaseTabbedPane::SetAutoDestroy

Bestimmt, ob die Steuerleiste im Registerkartenformat automatisch zerstört wird.

```
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>Parameter

*bAutoDestroy*<br/>
[in] True, wenn der Bereich im Registerkartenformat dynamisch erstellt wurde, und Sie nicht, dessen Lebensdauer steuern sind. andernfalls "false".

### <a name="remarks"></a>Hinweise

Legen Sie die Auto-Modus auf "true", wenn Sie einen Bereich im Registerkartenformat dynamisch erstellen und zerstören, wenn Sie nicht seine Lebensdauer steuern, sind. Wenn Auto-löschen-Modus ist "true", wird der Bereich im Registerkartenformat automatisch durch das Framework zerstört werden.

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

*pBar*<br/>
[in] Ein Zeiger auf den Bereich, um Sie anzuzeigen oder auszublenden.

*bShow*<br/>
[in] True, um im Bereich angezeigt. "False" zum Ausblenden des Fensters.

*bDelay*<br/>
[in] True, um die Anpassung von der Registerkartenlayout zu verzögern. andernfalls "false".

*bActivate*<br/>
[in] True, um der Registerkarte der aktiven Registerkarte machen. andernfalls "false".

### <a name="return-value"></a>Rückgabewert

True, wenn die Registerkarte wurde entweder angezeigt oder ausgeblendet erfolgreich. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn Sie diese Methode aufrufen, ein Bereich entweder angezeigt oder ausgeblendet wird, abhängig vom Wert der *bShow* Parameter. Wenn Sie einer Registerkarte ausblenden, und die letzten eingeblendete Registerkarte im zugrunde liegenden Registerkartenfenster ist, wird der Bereich im Registerkartenformat ausgeblendet. Wenn Sie eine Registerkarte angezeigt, wenn zuvor keine Registerkarten angezeigt wurden, wird der Bereich im Registerkartenformat angezeigt.

##  <a name="recalclayout"></a>  CBaseTabbedPane::RecalcLayout

Berechnet die Layoutinformationen für den Bereich an.

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>Hinweise

Wenn der Bereich verankert ist, benachrichtigt diese Methode das Framework zum Ändern der Größe im Bereich, um die aktuelle Größe der Minirahmenfensters an.

Wenn der Bereich angedockt ist, bewirkt diese Methode nichts.

##  <a name="setautohidemode"></a>  CBaseTabbedPane::SetAutoHideMode

Legt den automatischen Ausblendemodus für entfernbare Bereiche in den Bereich im Registerkartenformat fest.

```
virtual CMFCAutoHideToolBar* SetAutoHideMode(
    BOOL bMode,
    DWORD dwAlignment,
    CMFCAutoHideToolBar* pCurrAutoHideBar = NULL,
    BOOL bUseTimer = TRUE);
```

### <a name="parameters"></a>Parameter

*bMode*<br/>
[in] True, um die automatisch ausblendbare-Modus zu aktivieren. "False", um reguläre Andockmodus zu aktivieren.

*dwAlignment*<br/>
[in] Gibt die Ausrichtung der automatisch ausblendbaren Bereich, der erstellt werden soll. Eine Liste der möglichen Werte, finden Sie unter [CPane::MoveByAlignment](../../mfc/reference/cpane-class.md#movebyalignment).

*pCurrAutoHideBar*<br/>
[in, out] Ein Zeiger auf der Symbolleiste des aktuellen automatisch im Hintergrund. NULL kann sein.

*bUseTimer*<br/>
[in] Gibt an, ob den automatisch ausblendbaren Effekt zu verwenden, wenn der Benutzer im Bereich in den Modus "automatisch ausblenden" wechselt, oder sofort Ausblenden des Fensters.

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf der Symbolleiste des automatischen Ausblenden, die erstellt wird, beim Wechseln zur automatischen Ausblendemodus oder NULL, wenn keine Symbolleiste erstellt wird.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Methode auf, wenn ein Benutzer die Pin-Schaltfläche, um die Seite im Registerformat automatischen Ausblendemodus oder regulären Andockmodus wechseln auswählt.

Modus "automatisch ausblenden" wird für jede entfernbare Bereich im Bereich mit Registerkarten festgelegt. Bereiche, die nicht lösbare sind, werden ignoriert. Weitere Informationen finden Sie unter [Mfcbasetabctrl](../../mfc/reference/cmfcbasetabctrl-class.md#enabletabdetach).

Rufen Sie diese Methode, um einen Bereich im Registerkartenformat zu automatischen Ausblendemodus programmgesteuert zu wechseln. Der Bereich angedockt werden muss, an das Hauptrahmenfenster ( [CDockablePane::GetDefaultPaneDivider](../../mfc/reference/cdockablepane-class.md#getdefaultpanedivider) muss einen gültigen Zeiger auf Zurückgeben der [CPaneDivider](../../mfc/reference/cpanedivider-class.md)).

## <a name="see-also"></a>Siehe auch

[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[Klassen](../../mfc/reference/mfc-classes.md)<br/>
[CDockablePane-Klasse](../../mfc/reference/cdockablepane-class.md)
