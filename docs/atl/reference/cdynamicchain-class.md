---
title: CDynamicChain-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a64a0c047c39b7c8e1f72a4762217af789481f2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062872"
---
# <a name="cdynamicchain-class"></a>CDynamicChain-Klasse

Diese Klasse stellt die Methoden, die Sie unterstützen die dynamische Verkettung von meldungszuordnungen bereit.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

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
|[CDynamicChain::CallChain](#callchain)|Leitet eine Windows-Meldung an ein anderes Objekt in die nachrichtenzuordnung an.|
|[CDynamicChain::RemoveChainEntry](#removechainentry)|Entfernt einen Nachrichtenzuordnungseintrag aus der Auflistung.|
|[CDynamicChain:: SetChainEntry](#setchainentry)|Fügt einen Nachrichtenzuordnungseintrag der Auflistung hinzu oder ändert einen vorhandenen Eintrag.|

## <a name="remarks"></a>Hinweise

`CDynamicChain` verwaltet eine Auflistung von meldungszuordnungen, aktivieren eine Windows-Meldung, die zur Laufzeit zur meldungszuordnung für ein anderes Objekt weitergeleitet werden.

Um Unterstützung für das dynamische Verketten von meldungszuordnungen hinzuzufügen, führen Sie folgende Schritte aus:

- Leiten Sie eine Klasse von `CDynamicChain`. Geben Sie in der meldungszuordnung, die [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) Makro, eine Verkettung mit Standard-meldungszuordnung eines anderen Objekts.

- Leiten Sie jede Klasse, die Sie aus, zu verketten möchten [CMessageMap](../../atl/reference/cmessagemap-class.md). `CMessageMap` ermöglicht einem Objekt, dessen meldungszuordnungen auf andere Objekte verfügbar zu machen.

- Rufen Sie `CDynamicChain::SetChainEntry` zu identifizieren, die Objekt und der Meldung zugeordnet werden soll, eine Verkettung mit.

Nehmen wir beispielsweise an, dass Ihre Klasse wie folgt definiert ist:

[!code-cpp[NVC_ATL_Windowing#88](../../atl/codesnippet/cpp/cdynamicchain-class_1.h)]

Der Client ruft dann `CMyWindow::SetChainEntry`:

[!code-cpp[NVC_ATL_Windowing#89](../../atl/codesnippet/cpp/cdynamicchain-class_2.cpp)]

wo `chainedObj` ist das verkettete Objekt und ist eine Instanz einer Klasse abgeleitet `CMessageMap`. Jetzt, wenn `myCtl` empfängt eine Nachricht, die durch nicht behandelte `OnPaint` oder `OnSetFocus`, die Fensterprozedur leitet die Nachricht an `chainedObj`des Standard-meldungszuordnung.

Weitere Informationen über das Verketten von Nachricht Zuordnung finden Sie unter [Meldungszuordnungen](../../atl/message-maps-atl.md) im Artikel "ATL-Fensterklassen".

## <a name="requirements"></a>Anforderungen

**Header:** atlwin.h vorhanden

##  <a name="callchain"></a>  CDynamicChain::CallChain

Leitet die Windows-Nachricht an ein anderes Objekt in die nachrichtenzuordnung an.

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

*dwChainID*<br/>
[in] Der eindeutige Bezeichner, der das verkettete Objekt und seine meldungszuordnung, zugeordnet ist.

*hWnd*<br/>
[in] Das Handle für das Fenster mit dem Empfang der Nachricht.

*uMsg*<br/>
[in] Die Meldung, die an das Fenster gesendet wird.

*wParam-Parameter*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

*lParam*<br/>
[in] Zusätzliche meldungsspezifische Informationen.

*lResult*<br/>
[out] Das Ergebnis der Nachrichtenverarbeitung.

### <a name="return-value"></a>Rückgabewert

True, wenn die Nachricht vollständig verarbeitet wird. andernfalls "false".

### <a name="remarks"></a>Hinweise

Für die Fensterprozedur aufzurufende `CallChain`, Sie müssen angeben, die [CHAIN_MSG_MAP_DYNAMIC](message-map-macros-atl.md#chain_msg_map_dynamic) Makro in der meldungszuordnung. Ein Beispiel finden Sie unter den [CDynamicChain](../../atl/reference/cdynamicchain-class.md) Übersicht.

`CallChain` erfordert einen vorherigen Aufruf [SetChainEntry](#setchainentry) Zuordnen der *DwChainID* Wert mit einem Objekt und seine meldungszuordnung.

##  <a name="cdynamicchain"></a>  CDynamicChain::CDynamicChain

Der Konstruktor.

```
CDynamicChain();
```

##  <a name="dtor"></a>  CDynamicChain:: ~ CDynamicChain

Der Destruktor.

```
~CDynamicChain();
```

### <a name="remarks"></a>Hinweise

Gibt alle zugeordnete Ressourcen frei.

##  <a name="removechainentry"></a>  CDynamicChain::RemoveChainEntry

Entfernt die Zuordnung für die angegebene Nachricht aus der Auflistung.

```
BOOL RemoveChainEntry(DWORD dwChainID);
```

### <a name="parameters"></a>Parameter

*dwChainID*<br/>
[in] Der eindeutige Bezeichner, der das verkettete Objekt und seine meldungszuordnung, zugeordnet ist. Sie definieren ursprünglich diesen Wert durch einen Aufruf von [SetChainEntry](#setchainentry).

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die nachrichtenzuordnung erfolgreich aus der Auflistung entfernt wird. Andernfalls "false".

##  <a name="setchainentry"></a>  CDynamicChain:: SetChainEntry

Die Zuordnung der angegebenen Meldung und der Auflistung hinzugefügt.

```
BOOL SetChainEntry(
    DWORD dwChainID,
    CMessageMap* pObject,
    DWORD dwMsgMapID = 0);
```

### <a name="parameters"></a>Parameter

*dwChainID*<br/>
[in] Der eindeutige Bezeichner, der das verkettete Objekt und seine meldungszuordnung, zugeordnet ist.

*pObject*<br/>
[in] Ein Zeiger auf das verkettete Objekt deklarieren die meldungszuordnung. Dieses Objekt muss abgeleitet [CMessageMap](../../atl/reference/cmessagemap-class.md).

*dwMsgMapID*<br/>
[in] Der Bezeichner der Nachricht Zuordnung in den verketteten-Objekt. Der Standardwert ist 0 (null) und die Standard-meldungszuordnung, die mit deklariert identifiziert [BEGIN_MSG_MAP](message-map-macros-atl.md#begin_msg_map). An einem alternativen meldungszuordnung, die mit deklariert [ALT_MSG_MAP(msgMapID)](message-map-macros-atl.md#alt_msg_map), übergeben Sie `msgMapID`.

### <a name="return-value"></a>Rückgabewert

TRUE, wenn die meldungszuordnung erfolgreich zur Auflistung hinzugefügt wurde. Andernfalls "false".

### <a name="remarks"></a>Hinweise

Wenn die *DwChainID* Wert in der Auflistung bereits vorhanden ist, durch die zugeordnete Objekt und eine meldungszuordnung ersetzt *pObject* und *DwMsgMapID*bzw. Andernfalls wird ein neuer Eintrag hinzugefügt.

## <a name="see-also"></a>Siehe auch

[CWindowImpl-Klasse](../../atl/reference/cwindowimpl-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
