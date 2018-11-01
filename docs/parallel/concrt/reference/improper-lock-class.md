---
title: Improper_lock-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
dev_langs:
- C++
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 655776543a0c368bf5d13719d10b507c941a0fa9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404695"
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

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> improper_lock

Konstruiert ein `improper_lock exception`.

```
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[critical_section-Klasse](critical-section-class.md)<br/>
[reader_writer_lock-Klasse](reader-writer-lock-class.md)
