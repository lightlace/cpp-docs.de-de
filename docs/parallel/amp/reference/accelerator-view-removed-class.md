---
title: accelerator_view_removed-Klasse
ms.date: 03/27/2019
f1_keywords:
- accelerator_view_removed
- AMPRT/accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed::get_view_removed_reason
helpviewer_keywords:
- AMPRT/Concurrency::accelerator_view_removed::accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
ms.openlocfilehash: 9a3f6f349fc3103893639fe209dcf23a07ffec56
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127123"
---
# <a name="accelerator_view_removed-class"></a>accelerator_view_removed-Klasse

Die Ausnahme, die ausgelöst wird, wenn ein zugrunde liegender DirectX-Aufruf aufgrund des Windows-TDR-Mechanismus (Timeout Detection and Recovery) fehlschlägt.

## <a name="syntax"></a>Syntax

```cpp
class accelerator_view_removed : public runtime_exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[accelerator_view_removed-Konstruktor](#ctor)|Initialisiert eine neue Instanz der Klasse `accelerator_view_removed`.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[get_view_removed_reason](#get_view_removed_reason)|Gibt einen HRESULT-Fehlercode zurück, der die Ursache für das Entfernen des `accelerator_view` Objekts angibt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`runtime_exception`

`out_of_memory`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** amprt. h

**Namespace:** Parallelität

## <a name="ctor"></a>accelerator_view_removed

Initialisiert eine neue Instanz der [accelerator_view_removed](accelerator-view-removed-class.md) -Klasse.

### <a name="syntax"></a>Syntax

```cpp
explicit accelerator_view_removed(
    const char * message,
    HRESULT view_removed_reason ) throw();

explicit accelerator_view_removed(
    HRESULT view_removed_reason ) throw();
```

### <a name="parameters"></a>Parameter

*Nachricht*<br/>
Eine Beschreibung des Fehlers.

*view_removed_reason*<br/>
Ein HRESULT-Fehlercode, der die Ursache für das Entfernen des `accelerator_view` Objekts angibt.

### <a name="return-value"></a>Rückgabewert

Eine neue Instanz der `accelerator_view_removed`-Klasse.

## <a name="get_view_removed_reason"></a>get_view_removed_reason

Gibt einen HRESULT-Fehlercode zurück, der die Ursache für das Entfernen des `accelerator_view` Objekts angibt.

### <a name="syntax"></a>Syntax

```cpp
HRESULT get_view_removed_reason() const throw();
```

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
