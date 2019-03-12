---
title: Platform::ChangedStateException-Klasse
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ChangedStateException
- VCCORLIB/Platform::ChangedStateException::ChangedStateException
helpviewer_keywords:
- Platform::ChangedStateException
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
ms.openlocfilehash: 79181702c95f8c666b06bdb26319ccb06e55db0a
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749294"
---
# <a name="platformchangedstateexception-class"></a>Platform::ChangedStateException-Klasse

Wird ausgelöst, wenn der interne Zustand eines Objekts geändert wurde und damit die Ergebnisse der Methode ungültig wurden.

## <a name="syntax"></a>Syntax

```cpp
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Hinweise

Ein Beispiel, in dem diese Ausnahme ausgelöst wird, ist, wenn Methoden eines Auflistungsiterators oder einer Auflistungsansicht aufgerufen werden, nachdem die übergeordnete Auflistung geändert wurde, wodurch die Ergebnisse der Methode ungültig werden.

Weitere Informationen finden Sie unter der [COMException](../cppcx/platform-comexception-class.md) -Klasse.

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Plattform

**Metadaten:** platform.winmd

## <a name="see-also"></a>Siehe auch

[Platform::COMException-Klasse](../cppcx/platform-comexception-class.md)
