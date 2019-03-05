---
title: CMessageMap-Klasse
ms.date: 11/04/2016
f1_keywords:
- CMessageMap
- ATLWIN/ATL::CMessageMap
- ATLWIN/ATL::CMessageMap::ProcessWindowMessage
helpviewer_keywords:
- CMessageMap class
- message maps, ATL
- ATL, message handlers
ms.assetid: 1f97bc16-a8a0-4cf0-b90f-1778813a5c8e
ms.openlocfilehash: 617b7b4592c96625b44fbe5c2b93da971a423128
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293172"
---
# <a name="cmessagemap-class"></a>CMessageMap-Klasse

Diese Klasse ermöglicht, dass ein Objekt des meldungszuordnungen über ein anderes Objekt zugegriffen werden kann.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class ATL_NO_VTABLE CMessageMap
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CMessageMap::ProcessWindowMessage](#processwindowmessage)|Greift auf eine meldungszuordnung in der `CMessageMap`-abgeleitete Klasse.|

## <a name="remarks"></a>Hinweise

`CMessageMap` ist eine abstrakte Basisklasse, die ein Objekt der Nachricht ermöglicht Zuordnungen enthalten, die von einem anderen Objekt zugegriffen werden. Damit kann für ein Objekt, dessen meldungszuordnungen verfügbar zu machen, muss die Klasse von abgeleitet werden `CMessageMap`.

ATL verwendet `CMessageMap` enthaltene Support für Windows und Verketten von dynamische Nachricht zuordnen. Beispielsweise jede Klasse mit einer [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) Objekt muss abgeleitet `CMessageMap`. Der folgende Code stammt aus dem [SUBEDIT](https://github.com/Microsoft/VCSamples/tree/master/VC2008Samples/ATL/Controls/SubEdit) Beispiel. Über [CComControl](../../atl/reference/ccomcontrol-class.md), `CAtlEdit` Klasse automatisch abgeleitet `CMessageMap`.

[!code-cpp[NVC_ATL_Windowing#90](../../atl/codesnippet/cpp/cmessagemap-class_1.h)]

Da im Fenster enthaltene `m_EditCtrl`, verwendet eine meldungszuordnung in der enthaltenden Klasse `CAtlEdit` leitet sich von `CMessageMap`.

Weitere Informationen über meldungszuordnungen finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md) im Artikel "ATL-Fensterklassen".

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="processwindowmessage"></a>  CMessageMap::ProcessWindowMessage

Greift auf die meldungszuordnung identifizierte *DwMsgMapID* in einem `CMessageMap`-abgeleitete Klasse.

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

*hWnd*<br/>
[in] Das Handle für das Fenster mit dem Empfang der Nachricht.

*uMsg*<br/>
[in] Die Meldung, die an das Fenster gesendet wird.

*wParam*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

*lParam*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

*lResult*<br/>
[out] Das Ergebnis der Nachrichtenverarbeitung.

*dwMsgMapID*<br/>
[in] Der Bezeichner der meldungszuordnung, die die Nachricht verarbeitet. Die Standard-meldungszuordnung, die mit deklariert [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map), wird durch 0 identifiziert. Eine alternative meldungszuordnung, mit dem deklariert [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), wird durch identifiziert `msgMapID`.

### <a name="return-value"></a>Rückgabewert

True, wenn die Nachricht vollständig verarbeitet wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

Wird aufgerufen, durch die Fensterprozedur von einem [CContainedWindow](../../atl/reference/ccontainedwindowt-class.md) -Objekts oder eines Objekts ist, die dynamisch an die meldungszuordnung verketten.

## <a name="see-also"></a>Siehe auch

[CDynamicChain-Klasse](../../atl/reference/cdynamicchain-class.md)<br/>
[BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map)<br/>
[ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
