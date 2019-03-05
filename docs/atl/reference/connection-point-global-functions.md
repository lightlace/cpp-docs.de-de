---
title: Verbindungspunkt für globale Funktionen
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlAdvise
- atlbase/ATL::AtlUnadvise
- atlbase/ATL::AtlAdviseSinkMap
helpviewer_keywords:
- connection points [C++], global functions
ms.assetid: bcb4bf50-2155-4e20-b8bb-f2908b03a6e7
ms.openlocfilehash: 0313e93ee82bb96f3bfe08e45f70ccfee30dbee6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263883"
---
# <a name="connection-point-global-functions"></a>Verbindungspunkt für globale Funktionen

Diese Funktionen bieten Unterstützung für Verbindungspunkte und Maps-Senke.

> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

|||
|-|-|
|[AtlAdvise](#atladvise)|Erstellt eine Verbindung zwischen dem Verbindungspunkt eines Objekts und der Senke eines Clients.|
|[AtlUnadvise](#atlunadvise)|Beendet die Verbindung mit `AtlAdvise`.|
|[AtlAdviseSinkMap](#atladvisesinkmap)|Weist oder hebt Anweisungen für Einträge in eine Senke-Event-Zuordnung.|

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="atladvise"></a>  AtlAdvise

Erstellt eine Verbindung zwischen dem Verbindungspunkt eines Objekts und der Senke eines Clients.

> [!IMPORTANT]
>  Diese Funktion kann nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

```
HRESULT    AtlAdvise(
    IUnknown* pUnkCP,
    IUnknown* pUnk,
    const IID& iid,
    LPDWORD pdw);
```

### <a name="parameters"></a>Parameter

*pUnkCP*<br/>
[in] Ein Zeiger auf die `IUnknown` des Objekts der Client eine Verbindung mit herstellen möchte.

*pUnk*<br/>
[in] Ein Zeiger auf des Clients `IUnknown`.

*iid*<br/>
[in] Die GUID des Verbindungspunkts. Dies ist normalerweise identisch mit der von den Verbindungspunkt verwalteten Ausgangsschnittstelle.

*pdw*<br/>
[out] Ein Zeiger auf das Cookie, das die Verbindung eindeutig identifiziert.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="remarks"></a>Hinweise

Die Senke implementiert die Ausgangsschnittstelle, die von den Verbindungspunkt unterstützt werden. Der Client verwendet die *Pdw* Cookies, das die Verbindung zu entfernen, indem Sie die Übergabe an [AtlUnadvise](#atlunadvise).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#91](../../atl/codesnippet/cpp/connection-point-global-functions_1.cpp)]

##  <a name="atlunadvise"></a>  AtlUnadvise

Beendet die Verbindung mit [AtlAdvise](#atladvise).

> [!IMPORTANT]
>  Diese Funktion kann nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

```
HRESULT    AtlUnadvise(
    IUnknown* pUnkCP,
    const IID& iid,
    DWORD dw);
```

### <a name="parameters"></a>Parameter

*pUnkCP*<br/>
[in] Ein Zeiger auf die `IUnknown` des Objekts, das mit der Client verbunden ist.

*iid*<br/>
[in] Die GUID des Verbindungspunkts. Dies ist normalerweise identisch mit der von den Verbindungspunkt verwalteten Ausgangsschnittstelle.

*dw*<br/>
[in] Das Cookie, das die Verbindung eindeutig identifiziert.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#96](../../atl/codesnippet/cpp/connection-point-global-functions_2.cpp)]

##  <a name="atladvisesinkmap"></a>  AtlAdviseSinkMap

Mit dieser Funktion melden Sie alle Einträge in der Senkereigniszuordnung des Objekts an oder ab.

> [!IMPORTANT]
>  Diese Funktion kann nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

```
HRESULT AtlAdviseSinkMap(T* pT, bool bAdvise);
```

### <a name="parameters"></a>Parameter

*pT*<br/>
[in] Ein Zeiger auf das Objekt, das die Sink-Zuordnung enthält.

*bAdvise*<br/>
[in] True, wenn alle Senke Einträge sind, darüber informiert zu werden. "False", wenn alle Einträge der Senke abzumelden werden sollen.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_ATL_Windowing#92](../../atl/codesnippet/cpp/connection-point-global-functions_3.h)]

## <a name="see-also"></a>Siehe auch

[Funktionen](../../atl/reference/atl-functions.md)<br/>
[Verbindungspunkt-Makros](../../atl/reference/connection-point-macros.md)
