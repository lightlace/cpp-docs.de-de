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
ms.openlocfilehash: c10a7f302b63c33869425c4e5bddb36a15373ea8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262592"
---
# <a name="improperlock-class"></a>improper_lock-Klasse

Diese Klasse beschreibt eine Ausnahme, die ausgelöst wird, wenn eine Sperre nicht ordnungsgemäß abgerufen wird.

## <a name="syntax"></a>Syntax

```
class improper_lock : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[improper_lock](#ctor)|Überladen. Konstruiert ein `improper_lock exception`.|

## <a name="remarks"></a>Hinweise

In der Regel wird diese Ausnahme ausgelöst, bei dem Versuch, eine nicht wiedereintretende Sperre rekursiv im gleichen Kontext abzurufen.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`improper_lock`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> improper_lock

Konstruiert ein `improper_lock exception`.

```
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[critical_section-Klasse](critical-section-class.md)<br/>
[reader_writer_lock-Klasse](reader-writer-lock-class.md)
