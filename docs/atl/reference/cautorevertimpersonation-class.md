---
title: CAutoRevertImpersonation-Klasse
ms.date: 11/04/2016
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
ms.openlocfilehash: c8ab7fed8f1560054eb023cbd4e47c43c4c6f0cc
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57299100"
---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation-Klasse

Diese Klasse setzt [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekte in einem nonimpersonating Zustand, wenn sie den Gültigkeitsbereich verlässt.

## <a name="syntax"></a>Syntax

```
class CAutoRevertImpersonation
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|Erstellt eine `CAutoRevertImpersonation` Objekt|
|[CAutoRevertImpersonation::~CAutoRevertImpersonation](#dtor)|Zerstört das Objekt, und setzt die Access-token-Identitätswechsel.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAutoRevertImpersonation::Attach](#attach)|Automatisiert die Zurücksetzung Identitätswechsel eines Zugriffstokens.|
|[CAutoRevertImpersonation::Detach](#detach)|Bricht den automatischen Identitätswechsel eine neue Version zuweisen.|
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Ruft die diesem Objekt zugeordneten aktuellen Access token ab.|

## <a name="remarks"></a>Hinweise

Ein [Zugriffstoken](/windows/desktop/SecAuthZ/access-tokens) ist ein Objekt, das beschreibt den Sicherheitskontext eines Prozesses oder Threads. zudem ist jeder Benutzer, die ein Windows NT oder Windows 2000-System angemeldet zugeordnet ist. Diese Zugriffstoken dargestellt werden können, mit der `CAccessToken` Klasse.

Manchmal ist es erforderlich, für den Identitätswechsel des Zugangs-Token. Diese Klasse wird zur Vereinfachung bereitgestellt, aber den Identitätswechsel des Zugangs-Token wird nicht ausgeführt; Sie führt nur die automatische Zurücksetzung zu einem nonimpersonated Zustand. Dies ist da tokenzugriff Identitätswechsel für verschiedene Arten ausgeführt werden kann.

Eine Einführung in das Zugriffssteuerungsmodell in Windows, finden Sie unter [Zugriffssteuerung](/windows/desktop/SecAuthZ/access-control) im Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** atlsecurity.h

##  <a name="attach"></a>  CAutoRevertImpersonation::Attach

Automatisiert die Zurücksetzung Identitätswechsel eines Zugriffstokens.

```
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parameter

*pAT*<br/>
Die Adresse der [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt, das automatisch rückgängig gemacht werden

### <a name="remarks"></a>Hinweise

Diese Methode sollte nur verwendet werden, wenn die [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) Objekt wurde erstellt, mit einer NULL- `CAccessToken` -Zeiger ist, oder wenn [trennen](#detach) wurde zuvor aufgerufen. In einfachen Fällen ist es nicht erforderlich, diese Methode verwenden.

##  <a name="cautorevertimpersonation"></a>  CAutoRevertImpersonation::CAutoRevertImpersonation

Erstellt ein `CAutoRevertImpersonation`-Objekt.

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parameter

*pAT*<br/>
Die Adresse der [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt, das automatisch rückgängig gemacht werden.

### <a name="remarks"></a>Hinweise

Der tatsächliche Identitätswechsel des Zugriffstokens separat aus, vorzugsweise vor dem Erstellen des ausgeführt werden soll eine `CAutoRevertImpersonation` Objekt. Dieser Identitätswechsel wird zurückgesetzt werden automatisch bei der `CAutoRevertImpersonation` Objekt den Gültigkeitsbereich verlässt.

##  <a name="dtor"></a>  CAutoRevertImpersonation:: ~ CAutoRevertImpersonation

Zerstört das Objekt, und setzt die Access-token-Identitätswechsel.

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>Hinweise

Setzt alle Identitätswechsel derzeit für die [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt bereitgestellt werden, entweder bei der Erstellung oder über die [Anfügen](#attach) Methode. Wenn kein `CAccessToken` wird zugeordnet, der Destruktor hat keine Auswirkungen.

##  <a name="detach"></a>  CAutoRevertImpersonation::Detach

Bricht den automatischen Identitätswechsel eine neue Version zuweisen.

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des zuvor zugeordneten [CAccessToken](../../atl/reference/caccesstoken-class.md), oder NULL, wenn keine Zuordnung vorhanden waren.

### <a name="remarks"></a>Hinweise

Aufrufen **trennen** wird verhindert, dass die `CAutoRevertImpersonation` Objekt aus der Wiederherstellung jeder Identitätswechsel, der derzeit für die [CAccessToken](../../atl/reference/caccesstoken-class.md) Objekt mit diesem Objekt verknüpft ist. `CAutoRevertImpersonation` hat keine Auswirkungen zerstört oder auf demselben oder einem anderen neu zugeordnet werden können `CAccessToken` -Objekt unter Verwendung der [Anfügen](#attach).

##  <a name="getaccesstoken"></a>  CAutoRevertImpersonation::GetAccessToken

Ruft die diesem Objekt zugeordneten aktuellen Access token ab.

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des zuvor zugeordneten [CAccessToken](../../atl/reference/caccesstoken-class.md), oder NULL, wenn keine Zuordnung vorhanden waren.

### <a name="remarks"></a>Hinweise

Wenn diese Methode für die Zwecke aufgerufen wird, die die Zurücksetzung eines Identitätswechsels des enthalten die `CAccessToken` -Objekt, das [trennen](#detach) Methode sollte stattdessen verwendet werden.

## <a name="see-also"></a>Siehe auch

[ATLSecurity-Beispiel](../../visual-cpp-samples.md)<br/>
[Zugriffstoken](/windows/desktop/SecAuthZ/access-tokens)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
