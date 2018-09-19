---
title: CComFakeCriticalSection-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48b120b7be3e605b6ed2619cbd71011b0a693bdc
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757275"
---
# <a name="ccomfakecriticalsection-class"></a>CComFakeCriticalSection-Klasse

Diese Klasse stellt die gleichen Methoden wie [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) jedoch kein kritischen Abschnitts.

## <a name="syntax"></a>Syntax

```
class CComFakeCriticalSection
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComFakeCriticalSection::Init](#init)|Hat keine Auswirkungen, da keine kritischen Abschnitt vorhanden ist.|
|[CComFakeCriticalSection::Lock](#lock)|Hat keine Auswirkungen, da keine kritischen Abschnitt vorhanden ist.|
|[CComFakeCriticalSection::Term](#term)|Hat keine Auswirkungen, da keine kritischen Abschnitt vorhanden ist.|
|[CComFakeCriticalSection::Unlock](#unlock)|Hat keine Auswirkungen, da keine kritischen Abschnitt vorhanden ist.|

## <a name="remarks"></a>Hinweise

`CComFakeCriticalSection` spiegelt die in Methoden [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Allerdings `CComFakeCriticalSection` bietet kein kritischen Abschnitts; daher seine Methoden nichts Unternehmen.

Normalerweise verwenden Sie `CComFakeCriticalSection` über eine `typedef` Namen verwenden, entweder `AutoCriticalSection` oder `CriticalSection`. Bei Verwendung [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) oder [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), beide `typedef` Namen Verweis `CComFakeCriticalSection`. Bei Verwendung [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), die Ereignisse verweisen auf [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) und `CComCriticalSection`bzw.

## <a name="requirements"></a>Anforderungen

**Header:** atlcore.h

##  <a name="init"></a>  CComFakeCriticalSection::Init

Hat keine Auswirkungen, da keine kritischen Abschnitt vorhanden ist.

```
HRESULT Init() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="lock"></a>  CComFakeCriticalSection::Lock

Hat keine Auswirkungen, da keine kritischen Abschnitt vorhanden ist.

```
HRESULT Lock() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="term"></a>  CComFakeCriticalSection::Term

Hat keine Auswirkungen, da keine kritischen Abschnitt vorhanden ist.

```
HRESULT Term() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

##  <a name="unlock"></a>  CComFakeCriticalSection::Unlock

Hat keine Auswirkungen, da keine kritischen Abschnitt vorhanden ist.

```
HRESULT Unlock() throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt S_OK zurück.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
