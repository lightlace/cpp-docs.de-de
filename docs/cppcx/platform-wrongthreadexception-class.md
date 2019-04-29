---
title: Platform::WrongThreadException-Klasse
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WrongThreadException
- VCCORLIB/Platform::WrongThreadException::WrongThreadException
helpviewer_keywords:
- Platform::WrongThreadException
ms.assetid: c193f97e-0392-4535-a4c4-0711e4e4a836
ms.openlocfilehash: dde8c9afff6be083580042a958f59e057bc44350
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396079"
---
# <a name="platformwrongthreadexception-class"></a>Platform::WrongThreadException-Klasse

Wird ausgelöst, wenn ein Thread über einen Schnittstellenzeiger einen Aufruf für ein Proxyobjekt tätigt, das nicht zu dem Apartment des Threads gehört.

## <a name="syntax"></a>Syntax

```cpp
public ref class WrongThreadException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [COMException](../cppcx/platform-comexception-class.md).

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Plattform

**Metadaten:** platform.winmd

## <a name="see-also"></a>Siehe auch

[Platform::COMException-Klasse](../cppcx/platform-comexception-class.md)
