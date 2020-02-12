---
title: invalid_operation-Klasse
ms.date: 11/04/2016
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
ms.openlocfilehash: e17d530569d16ba0084a58bf0be00d4a8423b7f6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140873"
---
# <a name="invalid_operation-class"></a>invalid_operation-Klasse

Diese Klasse beschreibt eine Ausnahme, die bei Ausführen einer ungültigen Operation ausgelöst wird, die nicht genauer von einem anderen von der Concurrency Runtime ausgelösten Ausnahmetyp beschrieben wird.

## <a name="syntax"></a>Syntax

```cpp
class invalid_operation : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[invalid_operation](#ctor)|Ist überladen. Erstellt ein `invalid_operation`-Objekt.|

## <a name="remarks"></a>Bemerkungen

Die verschiedenen Methoden, die diese Ausnahme auslösen, dokumentieren im Allgemeinen die Umstände, unter denen sie diese auslösen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_operation`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>invalid_operation

Erstellt ein `invalid_operation`-Objekt.

```cpp
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
