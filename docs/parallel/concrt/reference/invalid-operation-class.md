---
title: Invalid_operation-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_operation
- CONCRT/concurrency::invalid_operation
- CONCRT/concurrency::invalid_operation::invalid_operation
dev_langs:
- C++
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e903a3d5e269a273a191fd733ff8813b75b53a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416907"
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

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> invalid_operation

Erstellt ein `invalid_operation`-Objekt.

```
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
