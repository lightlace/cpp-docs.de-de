---
title: Invalid_oversubscribe_operation-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation
- CONCRT/concurrency::invalid_oversubscribe_operation::invalid_oversubscribe_operation
dev_langs:
- C++
helpviewer_keywords:
- invalid_oversubscribe_operation class
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a1728053c7b42afedb4cda9b2dc96a089750a866
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161696"
---
# <a name="invalidoversubscribeoperation-class"></a>invalid_oversubscribe_operation-Klasse

Diese Klasse beschreibt eine Ausnahme wird ausgelöst, wenn die `Context::Oversubscribe` Methode wird aufgerufen, mit der `_BeginOversubscription` Parametersatz zu **"false"** ohne einen vorherigen Aufruf an die `Context::Oversubscribe` -Methode mit der `_BeginOversubscription` Parametersatz zu **"true"**.

## <a name="syntax"></a>Syntax

```
class invalid_oversubscribe_operation : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[invalid_oversubscribe_operation](#ctor)|Überladen. Erstellt ein `invalid_oversubscribe_operation`-Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`invalid_oversubscribe_operation`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h hinzu

**Namespace:** Parallelität

##  <a name="ctor"></a> invalid_oversubscribe_operation

Erstellt ein `invalid_oversubscribe_operation`-Objekt.

```
explicit _CRTIMP invalid_oversubscribe_operation(_In_z_ const char* _Message) throw();

invalid_oversubscribe_operation() throw();
```

### <a name="parameters"></a>Parameter

*_Nachricht*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
