---
title: scheduler_interface-Struktur
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: 99a3ea8b6ad1f23b4f3d54b7f2f406a3d115b374
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283370"
---
# <a name="schedulerinterface-structure"></a>scheduler_interface-Struktur

Planerschnittstelle

## <a name="syntax"></a>Syntax

```
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[scheduler_interface::schedule](#schedule)||

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`scheduler_interface`

## <a name="requirements"></a>Anforderungen

**Header:** pplinterface.h

**Namespace:** Parallelität

##  <a name="schedule"></a>  scheduler_interface:: Schedule-Methode

```
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
