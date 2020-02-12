---
title: improper_lock-Klasse
ms.date: 11/04/2016
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
ms.openlocfilehash: 886444f3e856234be010715a8ee0c707cf919bb4
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142403"
---
# <a name="improper_lock-class"></a>improper_lock-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn eine Sperre nicht ordnungsgemäß abgerufen wird.

## <a name="syntax"></a>Syntax

```cpp
class improper_lock : public std::exception;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[improper_lock](#ctor)|Ist überladen. Konstruiert ein `improper_lock exception`.|

## <a name="remarks"></a>Bemerkungen

Normalerweise wird diese Ausnahme ausgelöst, wenn versucht wird, eine nicht wieder eintretende Sperre rekursiv im gleichen Kontext abzurufen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`improper_lock`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ConcRT. h

**Namespace:** Parallelität

## <a name="ctor"></a>improper_lock

Konstruiert ein `improper_lock exception`.

```cpp
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[critical_section-Klasse](critical-section-class.md)<br/>
[reader_writer_lock-Klasse](reader-writer-lock-class.md)
