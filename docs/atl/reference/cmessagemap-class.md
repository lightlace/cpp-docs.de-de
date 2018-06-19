---
title: CMessageMap Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
dev_langs:
- C++
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 187d9964da0929516207a67b0e3a769649fc375b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359018"
---
# <a name="cmessagemap-class"></a>CMessageMap-Klasse
Diese Klasse ermöglicht es, dass ein Objekt meldungszuordnungen, um den Zugriff durch ein anderes Objekt sein.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class ATL_NO_VTABLE CMessageMap
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|Greift auf eine meldungszuordnung in der `CMessageMap`-Klasse.|  
  
## <a name="remarks"></a>Hinweise  
 `CMessageMap` ist eine abstrakte Basisklasse, die ein Objekt Nachricht ermöglicht Zuordnungen enthalten, die von einem anderen Objekt zugegriffen werden. Damit kann für ein Objekt, dessen meldungszuordnungen verfügbar zu machen, muss von die Klasse abgeleitet `CMessageMap`.  
  
 ATL verwendet `CMessageMap` eigenständiger Windows und dynamische Nachricht Zuordnung verketten. Z. B. eine Klasse mit einem [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) Objekt leiten von `CMessageMap`. Der folgende Code stammt aus dem [SUBEDIT](../../visual-cpp-samples.md) Beispiel. Über [CComControl](../../atl/reference/ccomcontrol-class.md), `CAtlEdit` Klasse automatisch abgeleitet `CMessageMap`.  
  
 [!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]  
  
 Da Fenster enthaltenen `m_EditCtrl`, verwendet eine meldungszuordnung in der enthaltenden Klasse `CAtlEdit` leitet sich von `CMessageMap`.  
  
 Weitere Informationen zu den meldungszuordnungen, finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md) im Artikel "ATL-Fensterklassen".  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlwin.h vorhanden  
  
##  <a name="processwindowmessage"></a>  CMessageMap::ProcessWindowMessage  
 Greift auf die identifizierte meldungszuordnung `dwMsgMapID` in eine `CMessageMap`-Klasse.  
  
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
 [in] Das Handle für das Empfangen der Nachricht ein.  
  
 `uMsg`  
 [in] Die Nachricht an das Fenster gesendet.  
  
 `wParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
 `lParam`  
 [in] Zusätzliche Meldung-spezifische Informationen.  
  
 `lResult`  
 [out] Das Ergebnis der Nachrichtenverarbeitung.  
  
 `dwMsgMapID`  
 [in] Der Bezeichner für die meldungszuordnung, die die Nachricht verarbeitet. Die Standard-meldungszuordnung deklariert mit [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), von 0 bezeichnet wird. Eine alternative meldungszuordnung deklariert mit [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), wird durch identifiziert `msgMapID`.  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** ist die Nachricht vollständig verarbeitet, andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Wird aufgerufen, indem die Fensterprozedur der eine [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) -Objekts oder eines Objekts ist, die dynamisch an die meldungszuordnung verketten.  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicChain-Klasse](../../atl/reference/cdynamicchain-class.md)   
 [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)   
 [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)   
 [Klassenübersicht](../../atl/atl-class-overview.md)
