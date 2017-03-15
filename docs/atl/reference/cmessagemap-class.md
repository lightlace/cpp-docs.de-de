---
title: CMessageMap Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMessageMap
- ATL.CMessageMap
- ATL::CMessageMap
dev_langs:
- C++
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f0b40c73101463b934e3fcf299171bea142fe838
ms.lasthandoff: 02/24/2017

---
# <a name="cmessagemap-class"></a>CMessageMap-Klasse
Diese Klasse ermöglicht, dass ein Objekt Nachricht Zugriff von einem anderen Objekt zugeordnet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class ATL_NO_VTABLE CMessageMap
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|Greift auf eine Zuordnung der Nachricht in der `CMessageMap`-Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 `CMessageMap`ist eine abstrakte Basisklasse, die ein Objekt Nachricht ermöglicht wird, um von einem anderen Objekt zugegriffen werden. In der Reihenfolge für ein Objekt, dessen Meldungszuordnungstabellen verfügbar zu machen, muss von die Klasse abgeleitet `CMessageMap`.  
  
 ATL verwendet `CMessageMap` eigenständiger Windows und dynamische Meldung Zuordnung verketten. Z. B. jede Klasse mit einer [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) Objekt durch Ableiten von `CMessageMap`. Der folgende Code stammt aus der [SUBEDIT](../../visual-cpp-samples.md) Beispiel. Durch [CComControl](../../atl/reference/ccomcontrol-class.md), `CAtlEdit` Klasse automatisch abgeleitet `CMessageMap`.  
  
 [!code-cpp[NVC_ATL_Windowing&#90;](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]  
  
 Da Fenster enthaltenen `m_EditCtrl`, verwendet eine Zuordnung für die Nachricht in der enthaltenden Klasse `CAtlEdit` leitet sich von `CMessageMap`.  
  
 Weitere Informationen über meldungszuordnungen finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md) im Artikel "ATL-Fensterklassen".  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h  
  
##  <a name="a-nameprocesswindowmessagea--cmessagemapprocesswindowmessage"></a><a name="processwindowmessage"></a>CMessageMap::ProcessWindowMessage  
 Greift auf den identifizierten meldungszuordnung `dwMsgMapID` in einem `CMessageMap`-abgeleiteten Klasse.  
  
```
virtual BOOL ProcessWindowMessage(  
    HWND hWnd,
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    LRESULT& lResult,
    DWORD dwMsgMapID) = 0;
```  
  
### <a name="parameters"></a>Parameter  
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
  
 `dwMsgMapID`  
 [in] Der Bezeichner der Nachricht Zuordnung, die die Nachricht verarbeitet. Die Standard-meldungszuordnung, die mit [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554), durch 0 identifiziert. Eine Zuordnung alternative Nachricht, die mit [ALT_MSG_MAP(msgMapID)](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8), wird durch identifiziert `msgMapID`.  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** ist die Nachricht vollständig verarbeitet, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Durch die Fensterprozedur des Namens einer [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) -Objekts oder eines Objekts ist, die dynamisch an die Nachricht Map verketten.  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicChain-Klasse](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN_MSG_MAP](http://msdn.microsoft.com/library/8bbb5af9-18b1-48c6-880e-166f599ee554)   
 [ALT_MSG_MAP](http://msdn.microsoft.com/library/2c8871bf-abc0-4d52-bcf7-6b2ab9eb5af8)   
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

