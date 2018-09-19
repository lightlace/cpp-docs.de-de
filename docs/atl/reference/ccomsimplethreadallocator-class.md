---
title: CComSimpleThreadAllocator-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1538d5148eeb1eb95c51150a43ef5dd7b107cae3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033549"
---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator-Klasse

Diese Klasse verwaltet die threadauswahl für die Klasse `CComAutoThreadModule`.

## <a name="syntax"></a>Syntax

```
class CComSimpleThreadAllocator
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComSimpleThreadAllocator::GetThread](#getthread)|Wählt einen Thread.|

## <a name="remarks"></a>Hinweise

`CComSimpleThreadAllocator` verwaltet die threadauswahl für [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread` einfach durch jeden Thread und gibt das nächste in der Sequenz zurück.

## <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

##  <a name="getthread"></a>  CComSimpleThreadAllocator::GetThread

Wählt einen Thread durch Angabe des nächsten Threads in der Sequenz.

```
int GetThread(CComApartment* /* pApt */, int nThreads);
```

### <a name="parameters"></a>Parameter

*pApt*<br/>
In der Standardimplementierung des ATL verwendet nicht.

*nThreads*<br/>
Die maximale Anzahl von Threads in der EXE-Modul.

### <a name="return-value"></a>Rückgabewert

Eine ganze Zahl zwischen 0 (null) und (*nThreads* - 1). Identifiziert einen der Threads in der EXE-Modul.

### <a name="remarks"></a>Hinweise

Sie können außer Kraft setzen `GetThread` Geben Sie eine andere Methode der Auswahl oder vornehmen möchten verwenden die *pApt* Parameter.

`GetThread` wird aufgerufen, indem [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).

## <a name="see-also"></a>Siehe auch

[CComApartment-Klasse](../../atl/reference/ccomapartment-class.md)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
