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
ms.openlocfilehash: 8b971a12ff83753546cfea7b90288d1bc43400c0
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279684"
---
# <a name="invalidoperation-class"></a>invalid_operation-Klasse

Diese Klasse beschreibt eine Ausnahme, die bei Ausführen einer ungültigen Operation ausgelöst wird, die nicht genauer von einem anderen von der Concurrency Runtime ausgelösten Ausnahmetyp beschrieben wird.

## <a name="syntax"></a>Syntax

```
class invalid_operation : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[invalid_operation](#ctor)|Überladen. Erstellt ein `invalid_operation`-Objekt.|

## <a name="remarks"></a>Hinweise

Die verschiedenen Methoden, die diese Ausnahme auslösen, dokumentieren im Allgemeinen die Umstände, unter denen sie diese auslösen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_operation`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> invalid_operation

Erstellt ein `invalid_operation`-Objekt.

```
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
