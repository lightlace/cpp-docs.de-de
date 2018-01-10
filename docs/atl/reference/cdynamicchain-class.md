---
title: CDynamicChain Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
dev_langs: C++
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f57da02b764c1cbce6a97ecbea8aa84e4ffcce9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicchain-class"></a>CDynamicChain-Klasse
Diese Klasse stellt die Methoden, die Unterstützung der dynamischen Verkettung von meldungszuordnungen bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CDynamicChain
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDynamicChain::CDynamicChain](#cdynamicchain)|Der Konstruktor.|  
|[CDynamicChain:: ~ CDynamicChain](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDynamicChain::CallChain](#callchain)|Leitet eine Windows-Nachricht an ein anderes Objekt meldungszuordnung.|  
|[CDynamicChain::RemoveChainEntry](#removechainentry)|Entfernt einen Nachrichtenzuordnungseintrag aus der Auflistung.|  
|[CDynamicChain:: SetChainEntry](#setchainentry)|Fügt der Auflistung einen Nachrichtenzuordnungseintrag hinzu oder ändert einen vorhandenen Eintrag.|  
  
## <a name="remarks"></a>Hinweise  
 `CDynamicChain`verwaltet eine Auflistung von meldungszuordnungen, aktivieren eine Windows-Meldung, die zur Laufzeit, um ein anderes Objekt meldungszuordnung umgeleitet werden.  
  
 Um Unterstützung für das dynamische Verketten von meldungszuordnungen hinzuzufügen, führen Sie folgende Schritte aus:  
  
-   Leiten Sie eine Klasse von `CDynamicChain`. Geben Sie in der meldungszuordnung, die [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) Makro, das mit einem anderen Objekt Standard-meldungszuordnung verkettet.  
  
-   Leiten Sie jede Klasse, die für von verkettet werden sollen [CMessageMap](../../atl/reference/cmessagemap-class.md). `CMessageMap`ermöglicht es einem Objekt, dessen meldungszuordnungen zu anderen Objekten verfügbar zu machen.  
  
-   Rufen Sie `CDynamicChain::SetChainEntry` identifizieren Sie die Kette zu Objekt und die Nachricht zuordnen, Sie möchten.  
  
 Nehmen wir beispielsweise an, dass die Klasse wie folgt definiert ist:  
  
 [!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]  
  
 Dann ruft der Client `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]  
  
 wobei `chainedObj` ist das verkettete Objekt und eine Instanz einer Klasse abgeleitet ist `CMessageMap`. Nun, wenn `myCtl` empfängt eine Nachricht, die nicht von behandelt wird `OnPaint` oder `OnSetFocus`, die Fensterprozedur leitet die Nachricht an `chainedObj`des Standard-meldungszuordnung.  
  
 Weitere Informationen zu Message Zuordnung verketten, finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md) im Artikel "ATL-Fensterklassen".  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="callchain"></a>CDynamicChain::CallChain  
 Leitet die Windows-Meldung an ein anderes Objekt meldungszuordnung.  
  
```
BOOL CallChain(  
    DWORD dwChainID,
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult);
```  
  
### <a name="parameters"></a>Parameter  
 `dwChainID`  
 [in] Der eindeutige Bezeichner, der das verkettete Objekt und seine meldungszuordnung zugeordnet ist.  
  
 `hWnd`  
 [in] Das Handle für das Empfangen der Nachricht ein.  
  
 `uMsg`  
 [in] Die Nachricht an das Fenster gesendet.  
  
 `wParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
 `lResult`  
 [out] Das Ergebnis der Nachrichtenverarbeitung.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** ist die Nachricht vollständig verarbeitet wird; andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Für die Fensterprozedur aufzurufenden `CallChain`, geben Sie die [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) Makro in Ihrer nachrichtenzuordnung. Ein Beispiel finden Sie die [CDynamicChain](../../atl/reference/cdynamicchain-class.md) (Übersicht).  
  
 `CallChain`erfordert einen vorherigen Aufruf von [SetChainEntry](#setchainentry) zum Zuordnen der `dwChainID` Wert mit einem Objekt und seine meldungszuordnung.  
  
##  <a name="cdynamicchain"></a>CDynamicChain::CDynamicChain  
 Der Konstruktor.  
  
```
CDynamicChain();
```  
  
##  <a name="dtor"></a>CDynamicChain:: ~ CDynamicChain  
 Der Destruktor.  
  
```
~CDynamicChain();
```  
  
### <a name="remarks"></a>Hinweise  
 Gibt alle zugeordnete Ressourcen frei.  
  
##  <a name="removechainentry"></a>CDynamicChain::RemoveChainEntry  
 Entfernt die Zuordnung für die angegebene Nachricht aus der Auflistung.  
  
```
BOOL RemoveChainEntry(DWORD dwChainID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwChainID`  
 [in] Der eindeutige Bezeichner, der das verkettete Objekt und seine meldungszuordnung zugeordnet ist. Ursprünglich definieren Sie diesen Wert durch einen Aufruf von [SetChainEntry](#setchainentry).  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** , wenn die meldungszuordnung erfolgreich aus der Auflistung entfernt wird. Andernfalls **"false"**.  
  
##  <a name="setchainentry"></a>CDynamicChain:: SetChainEntry  
 Die Zuordnung der angegebenen Meldung und der Auflistung hinzugefügt.  
  
```
BOOL SetChainEntry(  
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `dwChainID`  
 [in] Der eindeutige Bezeichner, der das verkettete Objekt und seine meldungszuordnung zugeordnet ist.  
  
 `pObject`  
 [in] Ein Zeiger auf das verkettete Objekt deklarieren die meldungszuordnung. Dieses Objekt muss abgeleitet [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Der Bezeichner der Nachricht Zuordnung in den verketteten-Objekt. Der Standardwert ist 0 (null) und die Standard-meldungszuordnung deklariert identifiziert mit [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). An einem alternativen meldungszuordnung deklariert mit [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), übergeben Sie `msgMapID`.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** die meldungszuordnung erfolgreich zur Auflistung hinzugefügt wird. Andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `dwChainID` Wert in der Auflistung bereits vorhanden ist, werden seine zugeordneten Objekts und eine meldungszuordnung durch ersetzt `pObject` und `dwMsgMapID`zugeordnet. Andernfalls wird ein neuer Eintrag hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [CWindowImpl-Klasse](../../atl/reference/cwindowimpl-class.md)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
