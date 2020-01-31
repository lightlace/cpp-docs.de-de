---
title: Ccomsafedeletecriticalsection-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Init
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Lock
- ATLCORE/ATL::CComSafeDeleteCriticalSection::Term
- ATLCORE/ATL::m_bInitialized
helpviewer_keywords:
- CComSafeDeleteCriticalSection class
ms.assetid: 4d2932c4-ba8f-48ec-8664-1db8bed01314
ms.openlocfilehash: da83bc5d0c2ebb79aee07f30069144368169fc26
ms.sourcegitcommit: b8c22e6d555cf833510753cba7a368d57e5886db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821648"
---
# <a name="ccomsafedeletecriticalsection-class"></a>Ccomsafedeletecriticalsection-Klasse

Diese Klasse stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts Objekts bereit.

## <a name="syntax"></a>Syntax

```
class CComSafeDeleteCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|-Name|Beschreibung|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::CComSafeDeleteCriticalSection](#ccomsafedeletecriticalsection)|Der Konstruktor.|
|[CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|-Name|Beschreibung|
|----------|-----------------|
|[CComSafeDeleteCriticalSection::Init](#init)|Erstellt und initialisiert ein kritisches Abschnitts Objekt.|
|[CComSafeDeleteCriticalSection::Lock](#lock)|Ruft den Besitz des kritischen Abschnitts Objekts ab.|
|[CComSafeDeleteCriticalSection::Term](#term)|Gibt Systemressourcen frei, die vom Objekt des kritischen Abschnitts verwendet werden.|

### <a name="data-members"></a>Datenmember

|||
|-|-|
|[m_bInitialized](#m_binitialized)|Gibt an, ob das interne `CRITICAL_SECTION` Objekt initialisiert wurde.|

## <a name="remarks"></a>Hinweise

`CComSafeDeleteCriticalSection` wird von der [ccomcriticalsection](../../atl/reference/ccomcriticalsection-class.md)-Klasse abgeleitet. `CComSafeDeleteCriticalSection` bietet jedoch zusätzliche Sicherheitsmechanismen über [ccomcriticalsection](../../atl/reference/ccomcriticalsection-class.md).

Wenn eine Instanz von `CComSafeDeleteCriticalSection` den Gültigkeitsbereich verlässt oder explizit aus dem Arbeitsspeicher gelöscht wird, wird das zugrunde liegende kritische Abschnitts Objekt automatisch bereinigt, wenn es noch gültig ist. Außerdem wird die [ccomsafedeletecriticalsection:: Term](#term) -Methode ordnungsgemäß beendet, wenn das zugrunde liegende kritische Abschnitts Objekt noch nicht zugeordnet wurde oder bereits aus dem Arbeitsspeicher freigegeben wurde.

Weitere Informationen zu kritischen Abschnitts Hilfsklassen finden Sie unter [ccomcriticalsection](../../atl/reference/ccomcriticalsection-class.md) .

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComSafeDeleteCriticalSection`

## <a name="requirements"></a>-Anforderungen

**Header:** atlcore. h

##  <a name="ccomsafedeletecriticalsection"></a>Ccomsafedeletecriticalsection:: ccomsafedeletecriticalsection

Der Konstruktor.

```
CComSafeDeleteCriticalSection();
```

### <a name="remarks"></a>Hinweise

Legt den [m_bInitialized](#m_binitialized) Datenmember auf false fest.

##  <a name="dtor"></a>Ccomsafedeletecriticalsection:: ~ ccomsafedeletecriticalsection

Der Destruktor.

```
~CComSafeDeleteCriticalSection() throw();
```

### <a name="remarks"></a>Hinweise

Gibt das interne `CRITICAL_SECTION` Objekt aus dem Arbeitsspeicher frei, wenn der [m_bInitialized](#m_binitialized) Datenmember auf true festgelegt ist.

##  <a name="init"></a>Ccomsafedeletecriticalsection:: init

Ruft die Basisklassen Implementierung von [Init](/visualstudio/debugger/init) auf und legt [m_bInitialized](#m_binitialized) auf true fest, wenn erfolgreich.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Ergebnis von [ccomcriticalsection:: init](../../atl/reference/ccomcriticalsection-class.md#init)zurück.

##  <a name="lock"></a>Ccomsafedeletecriticalsection:: Lock

Ruft die Basisklassen Implementierung von [Lock](ccomcriticalsection-class.md#lock)auf.

```
HRESULT Lock();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Ergebnis von [ccomcriticalsection:: Lock](../../atl/reference/ccomcriticalsection-class.md#lock)zurück.

### <a name="remarks"></a>Hinweise

Bei dieser Methode wird davon ausgegangen, dass der [m_bInitialized](#m_binitialized) Datenmember beim Eintrag auf true festgelegt ist. Eine-Assertion wird in Debugbuilds generiert, wenn diese Bedingung nicht erfüllt wird.

Weitere Informationen zum Verhalten der Funktion finden Sie unter [ccomcriticalsection:: Lock](../../atl/reference/ccomcriticalsection-class.md#lock).

##  <a name="m_binitialized"></a>Ccomsafedeletecriticalsection:: m_bInitialized

Gibt an, ob das interne `CRITICAL_SECTION` Objekt initialisiert wurde.

```
bool m_bInitialized;
```

### <a name="remarks"></a>Hinweise

Der `m_bInitialized` Datenmember wird verwendet, um die Gültigkeit des zugrunde liegenden `CRITICAL_SECTION` Objekts zu verfolgen, das der [ccomsafedeletecriticalsection](../../atl/reference/ccomsafedeletecriticalsection-class.md) -Klasse zugeordnet ist. Wenn dieses Flag nicht auf true festgelegt ist, wird nicht versucht, das zugrunde liegende `CRITICAL_SECTION` Objekt aus dem Arbeitsspeicher freizugeben.

##  <a name="term"></a>Ccomsafedeletecriticalsection:: Term

Ruft die Basisklassen Implementierung von [ccomcriticalsection:: Term](../../atl/reference/ccomcriticalsection-class.md#term) auf, wenn das interne `CRITICAL_SECTION` Objekt gültig ist.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Ergebnis von [ccomcriticalsection:: Term](../../atl/reference/ccomcriticalsection-class.md#term)oder S_OK zurück, wenn [m_bInitialized](#m_binitialized) beim Eintrag auf false festgelegt wurde.

### <a name="remarks"></a>Hinweise

Es ist sicher, diese Methode auch dann aufzurufen, wenn das interne `CRITICAL_SECTION` Objekt ungültig ist. Der destrukturtor dieser Klasse ruft diese Methode auf, wenn das [m_bInitialized](#m_binitialized) Datenmember auf true festgelegt ist.

## <a name="see-also"></a>Siehe auch

[CComCriticalSection-Klasse](../../atl/reference/ccomcriticalsection-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
