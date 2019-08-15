---
title: Cautorevertimpersonations-Klasse
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
ms.openlocfilehash: f1941bfcd7689ab9d22f5094af0eb833a84dab6b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497682"
---
# <a name="cautorevertimpersonation-class"></a>Cautorevertimpersonations-Klasse

Diese Klasse kehrt [CAccessToken](../../atl/reference/caccesstoken-class.md) -Objekte in den Zustand "nicht Identitätswechsel" zurück, wenn Sie den Gültigkeitsbereich verlässt.

## <a name="syntax"></a>Syntax

```
class CAutoRevertImpersonation
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|Erstellt ein `CAutoRevertImpersonation` Objekt.|
|[CAutoRevertImpersonation::~CAutoRevertImpersonation](#dtor)|Zerstört das-Objekt und kehrt den Identitätswechsel des Zugriffs Tokens zurück.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CAutoRevertImpersonation::Attach](#attach)|Automatisiert die Neuversion des Identitäts Wechsels eines Zugriffs Tokens.|
|[CAutoRevertImpersonation::Detach](#detach)|Bricht die automatische Neuversion des Identitäts Wechsels ab.|
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Ruft das aktuelle Zugriffs Token ab, das diesem-Objekt zugeordnet ist.|

## <a name="remarks"></a>Hinweise

Ein [Zugriffs Token](/windows/win32/SecAuthZ/access-tokens) ist ein Objekt, das den Sicherheitskontext eines Prozesses oder Threads beschreibt und jedem Benutzer zugeordnet ist, der auf einem Windows NT-oder Windows 2000-System angemeldet ist. Diese Zugriffs Token können mit der `CAccessToken` -Klasse dargestellt werden.

Es ist manchmal notwendig, die Identität der Zugriffs Token anzunehmen. Diese Klasse wird zur einfacheren Bereitstellung bereitgestellt, aber der Identitätswechsel von Zugriffs Token wird nicht durchgeführt. die automatische Neuversion wird nur auf einen Zustand ohne Identitätswechsel durchgeführt. Dies liegt daran, dass der Identitätswechsel für den tokenzugriff auf verschiedene Arten ausgeführt werden kann.

Eine Einführung zum Zugriffs Steuerungsmodell in Windows finden Sie unter [Access Control](/windows/win32/SecAuthZ/access-control) in der Windows SDK.

## <a name="requirements"></a>Anforderungen

**Header:** ATLSecurity. h

##  <a name="attach"></a>Cautor evertimpersonations:: Attach

Automatisiert die Neuversion des Identitäts Wechsels eines Zugriffs Tokens.

```
void Attach(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parameter

*pAT*<br/>
Die Adresse des [CAccessToken](../../atl/reference/caccesstoken-class.md) -Objekts, das automatisch wieder hergestellt werden soll.

### <a name="remarks"></a>Hinweise

Diese Methode sollte nur verwendet werden, wenn das [cautorevertimpersonations](../../atl/reference/cautorevertimpersonation-class.md) -Objekt mit einem NULL `CAccessToken` -Zeiger erstellt wurde oder wenn " [Detach](#detach) " zuvor aufgerufen wurde. In einfachen Fällen ist es nicht erforderlich, diese Methode zu verwenden.

##  <a name="cautorevertimpersonation"></a>Cautor evertimpersonations:: cautor evertimpersonations

Erstellt ein `CAutoRevertImpersonation`-Objekt.

```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```

### <a name="parameters"></a>Parameter

*pAT*<br/>
Die Adresse des [CAccessToken](../../atl/reference/caccesstoken-class.md) -Objekts, das automatisch wieder hergestellt werden soll.

### <a name="remarks"></a>Hinweise

Der tatsächliche Identitätswechsel des Zugriffs Tokens sollte getrennt von und vorzugsweise vor der Erstellung `CAutoRevertImpersonation` eines-Objekts durchgeführt werden. Dieser Identitätswechsel wird automatisch wieder hergestellt, wenn das `CAutoRevertImpersonation` Objekt den Gültigkeitsbereich verlässt.

##  <a name="dtor"></a>Cautor evertimpersonations:: ~ cautor evertimpersonations

Zerstört das-Objekt und kehrt den Identitätswechsel des Zugriffs Tokens zurück.

```
~CAutoRevertImpersonation() throw();
```

### <a name="remarks"></a>Hinweise

Kehrt alle Identitätswechsel für das [CAccessToken](../../atl/reference/caccesstoken-class.md) -Objekt zurück, das entweder bei der Erstellung oder der [Attach](#attach) -Methode bereitgestellt wird. Wenn kein `CAccessToken` zugeordnet ist, hat der Dekonstruktor keine Auswirkung.

##  <a name="detach"></a>Cautor evertimpersonations::D Etach

Bricht die automatische Neuversion des Identitäts Wechsels ab.

```
const CAccessToken* Detach() throw();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des zuvor zugeordneten [CAccessToken](../../atl/reference/caccesstoken-class.md)oder NULL, wenn keine Zuordnung vorhanden ist.

### <a name="remarks"></a>Hinweise

Durch das Aufrufen von **Detach** wird verhindert, dass das `CAutoRevertImpersonation` Objekt einen Identitätswechsel wiederherstellt, der aktuell für das diesem Objekt zugeordnete [CAccessToken](../../atl/reference/caccesstoken-class.md) -Objekt wirksam ist. `CAutoRevertImpersonation`kann dann ohne Auswirkung zerstört oder dem gleichen oder einem anderen `CAccessToken` Objekt mithilfe von [Attach](#attach)erneut zugeordnet werden.

##  <a name="getaccesstoken"></a>Cautor evertimpersonations:: getaccesstoken

Ruft das aktuelle Zugriffs Token ab, das diesem-Objekt zugeordnet ist.

```
const CAccessToken* GetAccessToken() throw();
```

### <a name="return-value"></a>Rückgabewert

Die Adresse des zuvor zugeordneten [CAccessToken](../../atl/reference/caccesstoken-class.md)oder NULL, wenn keine Zuordnung vorhanden ist.

### <a name="remarks"></a>Hinweise

Wenn diese Methode für die Zwecke aufgerufen wird, die die Neuversion eines Identitäts Wechsels des `CAccessToken` Objekts einschließen, sollte stattdessen die [Detach](#detach) -Methode verwendet werden.

## <a name="see-also"></a>Siehe auch

[Beispiel für ATLSecurity](../../overview/visual-cpp-samples.md)<br/>
[Zugriffs Token](/windows/win32/SecAuthZ/access-tokens)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
