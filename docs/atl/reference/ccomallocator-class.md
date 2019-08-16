---
title: Ccomzucator-Klasse
ms.date: 11/04/2016
f1_keywords:
- CComAllocator
- ATLBASE/ATL::CComAllocator
- ATLBASE/ATL::CComAllocator::Allocate
- ATLBASE/ATL::CComAllocator::Free
- ATLBASE/ATL::CComAllocator::Reallocate
helpviewer_keywords:
- CComAllocator class
ms.assetid: 0cd706fd-0c7b-42d3-9054-febe2966fc8e
ms.openlocfilehash: de302c7a58bf1b15e63e7cd391621ed9558e5a70
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497598"
---
# <a name="ccomallocator-class"></a>Ccomzucator-Klasse

Diese Klasse stellt Methoden zum Verwalten von Speicher mithilfe von com-Speicher Routinen bereit.

## <a name="syntax"></a>Syntax

```
class CComAllocator
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComAllocator::Allocate](#allocate)|Nennen Sie diese statische Methode, um Arbeitsspeicher zuzuweisen.|
|[CComAllocator::Free](#free)|Diese statische Methode zum Freigeben von zugewiesener Arbeitsspeicher aufzurufen.|
|[CComAllocator::Reallocate](#reallocate)|Diese statische Methode zum erneuten Zuweisen von Arbeitsspeicher verwenden.|

## <a name="remarks"></a>Hinweise

Diese Klasse wird von [ccomheapptr](../../atl/reference/ccomheapptr-class.md) verwendet, um die com-Speicher Belegungs Routinen bereitzustellen. Die gegen Klasse [ccrtallocator](../../atl/reference/ccrtallocator-class.md)stellt die gleichen Methoden mithilfe von CRT-Routinen bereit.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase. h

##  <a name="allocate"></a>Ccomallocator:: zuordnen

Rufen Sie diese statische Funktion auf, um Arbeitsspeicher zu belegen.

```
static void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*nBytes*<br/>
Die Anzahl der zu belegenden Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt einen void-Zeiger auf den belegten Speicherplatz oder NULL zurück, wenn nicht genügend Speicher verfügbar ist.

### <a name="remarks"></a>Hinweise

Belegt Arbeitsspeicher. Weitere Informationen finden Sie unter [cotaskmemzuweisung](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemalloc) .

##  <a name="free"></a>Ccomzucator:: Free

Diese statische Funktion zum Freigeben von zugewiesener Arbeitsspeicher aufzurufen.

```
static void Free(void* p) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Zeiger auf zugewiesenen Speicher.

### <a name="remarks"></a>Hinweise

Gibt den zugewiesenen Arbeitsspeicher frei. Weitere Informationen finden Sie unter " [CoTaskMemFree](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemfree) ".

##  <a name="reallocate"></a>Ccomallocator:: Neuzuordnung

Rufen Sie diese statischen Funktion auf, um Arbeitsspeicher neu zuzuordnen.

```
static void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parameter

*p*<br/>
Zeiger auf zugewiesenen Speicher.

*nBytes*<br/>
Die Anzahl der zuzuordnenden Bytes.

### <a name="return-value"></a>Rückgabewert

Gibt einen void-Zeiger auf den zugeordneten Speicherplatz oder NULL zurück, wenn nicht genügend Arbeitsspeicher vorhanden ist.

### <a name="remarks"></a>Hinweise

Ändert die Größe des belegten Speichers. Weitere Informationen finden Sie unter [cotaskmemrezuweisungen](/windows/win32/api/combaseapi/nf-combaseapi-cotaskmemrealloc) .

## <a name="see-also"></a>Siehe auch

[CComHeapPtr-Klasse](../../atl/reference/ccomheapptr-class.md)<br/>
[CCRTAllocator-Klasse](../../atl/reference/ccrtallocator-class.md)<br/>
[Klassen Übersicht](../../atl/atl-class-overview.md)
