---
title: Ccomautocriticalsection-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
helpviewer_keywords:
- CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
ms.openlocfilehash: 116c550f45bf622e7620b3a6f552339b4bcc24a7
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497932"
---
# <a name="ccomautocriticalsection-class"></a>Ccomautocriticalsection-Klasse

`CComAutoCriticalSection`stellt Methoden zum Abrufen und Freigeben des Besitzes eines kritischen Abschnitts Objekts bereit.

## <a name="syntax"></a>Syntax

```
class CComAutoCriticalSection : public CComCriticalSection
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|Der Konstruktor.|
|[CComAutoCriticalSection::~CComAutoCriticalSection](#dtor)|Der Destruktor.|

## <a name="remarks"></a>Hinweise

`CComAutoCriticalSection`ähnelt der Klasse [ccomcriticalsection](../../atl/reference/ccomcriticalsection-class.md), mit der `CComAutoCriticalSection` Ausnahme, dass das kritische Abschnitts Objekt im Konstruktor automatisch initialisiert wird.

Normalerweise verwenden `CComAutoCriticalSection` Sie den `typedef` Namen [autocriticalsection](ccommultithreadmodel-class.md#autocriticalsection). Dieser Name verweist `CComAutoCriticalSection` auf den Fall, dass [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) verwendet wird.

Die `Init` - `Term` Methode und die-Methode aus [ccomcriticalsection](../../atl/reference/ccomcriticalsection-class.md) sind nicht verfügbar, wenn diese Klasse verwendet wird.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)

`CComAutoCriticalSection`

## <a name="requirements"></a>Anforderungen

**Header:** atlcore. h

##  <a name="ccomautocriticalsection"></a>Ccomautocriticalsection:: ccomautocriticalsection

Der Konstruktor.

```
CComAutoCriticalSection();
```

### <a name="remarks"></a>Hinweise

Ruft die Win32-Funktion [InitializeCriticalSection](/windows/win32/api/synchapi/nf-synchapi-initializecriticalsection)auf, die das kritische Abschnitts Objekt initialisiert.

##  <a name="dtor"></a>Ccomautocriticalsection:: ~ ccomautocriticalsection

Der Destruktor.

```
~CComAutoCriticalSection() throw();
```

### <a name="remarks"></a>Hinweise

Der Dekonstruktor Ruft den [DeleteCriticalSection](/windows/win32/api/synchapi/nf-synchapi-deletecriticalsection)auf, der alle vom kritischen Abschnitts Objekt verwendeten Systemressourcen freigibt.

## <a name="see-also"></a>Siehe auch

[CComFakeCriticalSection-Klasse](../../atl/reference/ccomfakecriticalsection-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)<br/>
[CComCriticalSection-Klasse](../../atl/reference/ccomcriticalsection-class.md)
