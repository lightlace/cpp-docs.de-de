---
title: CAtlException-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
dev_langs:
- C++
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56038ffe4c6062422ea34a439e73b0d90a37cfb8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097730"
---
# <a name="catlexception-class"></a>CAtlException-Klasse

Diese Klasse definiert eine ATL-Ausnahme.

## <a name="syntax"></a>Syntax

```
class CAtlException
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlException::CAtlException](#catlexception)|Der Konstruktor.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CAtlException::operator HRESULT](#operator_hresult)|Wandelt das aktuelle Objekt in ein HRESULT-Wert.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CAtlException::m_hr](#m_hr)|Die Variable vom Typ HRESULT vom Objekt erstellt und verwendet, um den Fehlerzustand zu speichern.|

## <a name="remarks"></a>Hinweise

Ein `CAtlException` Objekt stellt eine Ausnahmebedingung, die im Zusammenhang mit einem ATL-Vorgang dar. Die `CAtlException` Klasse enthält einen öffentlichen Datenmember, die den Statuscode, der angibt, des Grund für die Ausnahme, und ein Cast-Operator, der Ihnen die Möglichkeit, die Ausnahme zu behandeln, als handele es sich um ein HRESULT speichert.

Rufen Sie in der Regel `AtlThrow` anstatt zu erstellen einen `CAtlException` direkt.

## <a name="requirements"></a>Anforderungen

**Header:** atlexcept.h

##  <a name="catlexception"></a>  CAtlException::CAtlException

Der Konstruktor.

```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```

### <a name="parameters"></a>Parameter

*HR*<br/>
Der HRESULT-Fehlercode.

##  <a name="operator_hresult"></a>  CAtlException::operator HRESULT

Wandelt das aktuelle Objekt in ein HRESULT-Wert.

```
operator HRESULT() const throw ();
```

##  <a name="m_hr"></a>  CAtlException::m_hr

Der HRESULT-Datenmember.

```
HRESULT m_hr;
```

### <a name="remarks"></a>Hinweise

Der Datenmember, die die fehlerbedingung speichert. Der HRESULT-Wert wird festgelegt, durch den Konstruktor [CAtlException::CAtlException](#catlexception).

## <a name="see-also"></a>Siehe auch

["Atlthrow"](debugging-and-error-reporting-global-functions.md#atlthrow)<br/>
[Übersicht über die Klasse](../../atl/atl-class-overview.md)
