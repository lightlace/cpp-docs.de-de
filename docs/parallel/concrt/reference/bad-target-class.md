---
title: bad_target-Klasse
ms.date: 11/04/2016
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
ms.openlocfilehash: 04489151cedf1a47aeebd883e76b8d26b51031ef
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298619"
---
# <a name="badtarget-class"></a>bad_target-Klasse

Diese Klasse beschreibt eine Ausnahme, die dann ausgelöst wird, wenn einem Meldungsblock ein Zeiger auf ein Ziel zugeordnet wird, das für die auszuführende Operation ungültig ist.

## <a name="syntax"></a>Syntax

```
class bad_target : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[bad_target](#ctor)|Überladen. Erstellt ein `bad_target`-Objekt.|

## <a name="remarks"></a>Hinweise

Diese Ausnahme wird normalerweise aus Gründen, z. B. ein Ziel versucht, eine Nachricht zu verarbeiten, die für ein anderes Ziel reserviert ist, oder veröffentlichen eine Reservierung, die er nicht aufrechterhält.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`bad_target`

## <a name="requirements"></a>Anforderungen

**Header:** concrt.h

**Namespace:** Parallelität

##  <a name="ctor"></a> bad_target

Erstellt ein `bad_target`-Objekt.

```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine beschreibende Fehlermeldung.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)<br/>
[Asynchrone Nachrichtenblöcke](../../../parallel/concrt/asynchronous-message-blocks.md)
