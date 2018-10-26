---
title: CComAutoCriticalSection-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 40fa13ecf743bf8e6aa0cd75b16bec65131fe267
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061078"
---
# <a name="ccomautocriticalsection-class"></a>CComAutoCriticalSection-Klasse

`CComAutoCriticalSection` Stellt Methoden zum Abrufen und Freigeben des Besitzes von einem kritischen Abschnittsobjekt bereit.

## <a name="syntax"></a>Syntax

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|Der Konstruktor.|
|[CComAutoCriticalSection:: ~ CComAutoCriticalSection](#dtor)|Der Destruktor.|

## <a name="remarks"></a>Hinweise

`CComAutoCriticalSection` ist vergleichbar mit der Klasse [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), mit Ausnahme von `CComAutoCriticalSection` automatisch initialisiert das Objekt des kritischen Abschnitts im Konstruktor.

Normalerweise verwenden Sie `CComAutoCriticalSection` über die `typedef` Namen [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Dieser Name verweist auf `CComAutoCriticalSection` beim [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) verwendet wird.

Die `Init` und `Term` Methoden [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) sind nicht verfügbar, wenn Sie diese Klasse verwenden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>Anforderungen

**Header:** atlcore.h

##  <a name="ccomautocriticalsection"></a>  CComAutoCriticalSection::CComAutoCriticalSection

Der Konstruktor.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>Hinweise

Ruft die Win32-Funktion [InitializeCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsection), die Objekt des kritischen Abschnitts initialisiert.

##  <a name="dtor"></a>  CComAutoCriticalSection:: ~ CComAutoCriticalSection

Der Destruktor.

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>Hinweise

Der Destruktor ruft [DeleteCriticalSection](/windows/desktop/api/synchapi/nf-synchapi-deletecriticalsection), die alle vom Objekt kritischen Abschnitts verwendete Systemressourcen frei.

## <a name="see-also"></a>Siehe auch

[CComFakeCriticalSection-Klasse](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)<br/>
[CComCriticalSection-Klasse](../../atl/reference/ccomcriticalsection-class.md)
