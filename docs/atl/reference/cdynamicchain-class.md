---
title: Klasse von CDynamicChain | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicChain
- ATLWIN/ATL::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CDynamicChain
- ATLWIN/ATL::CDynamicChain::CallChain
- ATLWIN/ATL::CDynamicChain::RemoveChainEntry
- ATLWIN/ATL::CDynamicChain::SetChainEntry
dev_langs:
- C++
helpviewer_keywords:
- message maps, chaining
- chaining message maps
- CDynamicChain class
ms.assetid: f084b2be-0e77-4836-973d-ae278a1e9da8
caps.latest.revision: 21
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4da97d0b3d72400d7e285fde187e6860759900af
ms.lasthandoff: 02/24/2017

---
# <a name="cdynamicchain-class"></a>CDynamicChain-Klasse
Diese Klasse enthält Methoden, die Unterstützung der dynamischen Verkettung von meldungszuordnungen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CDynamicChain
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDynamicChain::CDynamicChain](#cdynamicchain)|Der Konstruktor.|  
|[CDynamicChain:: ~ CDynamicChain](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDynamicChain::CallChain](#callchain)|Weist eine Windows-Meldung zu einem anderen Objekt Nachricht Zuordnung.|  
|[CDynamicChain::RemoveChainEntry](#removechainentry)|Entfernt einen Nachrichtenzuordnungseintrag aus der Auflistung.|  
|[CDynamicChain:: SetChainEntry](#setchainentry)|Fügt einen Nachrichtenzuordnungseintrag der Auflistung hinzu oder ändert einen vorhandenen Eintrag.|  
  
## <a name="remarks"></a>Hinweise  
 `CDynamicChain`verwaltet eine Auflistung von meldungszuordnungen, aktivieren eine Windows-Meldung an, die zur Laufzeit zu einem anderen Objekt Nachricht Zuordnung geleitet werden.  
  
 Führen Sie folgende Schritte aus, um die Unterstützung für dynamische Verkettung von Meldungszuordnungstabellen hinzuzufügen:  
  
-   Leiten Sie eine Klasse von `CDynamicChain`. Geben Sie in der meldungszuordnung der [CHAIN_MSG_MAP_DYNAMIC](http://msdn.microsoft.com/library/7e5c72b7-cb31-4f3b-8a1b-6293804af220) Makro mit einem anderen Objekt Standardkurve Nachricht verkettet sind.  
  
-   Leiten Sie jede Klasse zu verketten, um aus [CMessageMap](../../atl/reference/cmessagemap-class.md). `CMessageMap`ermöglicht es einem Objekt, dessen Meldungszuordnungstabellen auf andere Objekte verfügbar zu machen.  
  
-   Rufen Sie `CDynamicChain::SetChainEntry` ermitteln, die Objekt und die Nachricht ordnen Sie eine Kette zur möchten.  
  
 Nehmen wir beispielsweise an, dass die Klasse wie folgt definiert ist:  
  
 [!code-cpp[NVC_ATL_Windowing&#88;](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]  
  
 Der Client ruft dann `CMyWindow::SetChainEntry`:  
  
 [!code-cpp[NVC_ATL_Windowing&#89;](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]  
  
 wobei `chainedObj` ist das verkettete Objekt und eine Instanz einer Klasse abgeleitet ist `CMessageMap`. Nun, wenn `myCtl` empfängt eine Nachricht, die nicht von behandelt wird `OnPaint` oder `OnSetFocus`, die Fensterprozedur leitet die Nachricht an `chainedObj`des Standardkurve Nachricht.  
  
 Weitere Informationen über das Verketten von Nachricht Zuordnung finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md) im Artikel "ATL-Fensterklassen".  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="callchain"></a>CDynamicChain::CallChain  
 Weist die Windows-Meldung zu einem anderen Objekt Nachricht Zuordnung.  
  
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
 [in] Der eindeutige Bezeichner, der das verkettete Objekt und seiner Nachricht Zuordnung zugeordnet ist.  
  
 `hWnd`  
 [in] Das Handle für das Fenster, das die Nachricht empfängt.  
  
 `uMsg`  
 [in] Die Nachricht an das Fenster gesendet.  
  
 `wParam`  
 [in] Zusätzliche Message-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Message-spezifische Informationen.  
  
 `lResult`  
 [out] Das Ergebnis der Verarbeitung der Nachricht.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** ist die Nachricht vollständig verarbeitet wird; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Für die Prozedur aufrufen `CallChain`, geben Sie die [CHAIN_MSG_MAP_DYNAMIC](http://msdn.microsoft.com/library/7e5c72b7-cb31-4f3b-8a1b-6293804af220) Makro in der Zuordnung angezeigt. Ein Beispiel finden Sie unter der [CDynamicChain](../../atl/reference/cdynamicchain-class.md) (Übersicht).  
  
 `CallChain`erfordert einen vorherigen Aufruf [SetChainEntry](#setchainentry) Zuordnen der `dwChainID` Wert mit einem Objekt und seiner Nachricht Zuordnung.  
  
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
 Entfernt die Zuordnung der angegebenen Nachricht aus der Auflistung.  
  
```
BOOL RemoveChainEntry(DWORD dwChainID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwChainID`  
 [in] Der eindeutige Bezeichner, der das verkettete Objekt und seiner Nachricht Zuordnung zugeordnet ist. Ursprünglich definieren Sie diesen Wert durch einen Aufruf von [SetChainEntry](#setchainentry).  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** , wenn die Zuordnung für die Nachricht erfolgreich aus der Auflistung entfernt wird. Andernfalls **FALSE**.  
  
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
 [in] Der eindeutige Bezeichner, der das verkettete Objekt und seiner Nachricht Zuordnung zugeordnet ist.  
  
 `pObject`  
 [in] Ein Zeiger auf das verkettete Objekt deklarieren die Zuordnung der Nachricht. Dieses Objekt durch Ableiten von [CMessageMap](../../atl/reference/cmessagemap-class.md).  
  
 `dwMsgMapID`  
 [in] Der Bezeichner der Nachricht Zuordnung im verketteten-Objekt. Der Standardwert ist 0 (null) und die Standardkurve-Nachricht identifiziert, die mit [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554). Eine alternative meldungszuordnung angeben, die mit [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), übergeben Sie `msgMapID`.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** , wenn die Nachricht Zuordnung der Auflistung erfolgreich hinzugefügt wurde. Andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `dwChainID` Wert in der Auflistung bereits vorhanden ist, dessen zugeordnete Objekt und meldungszuordnung werden durch ersetzt `pObject` und `dwMsgMapID`bzw.. Andernfalls wird ein neuer Eintrag hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [CWindowImpl-Klasse](../../atl/reference/cwindowimpl-class.md)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

