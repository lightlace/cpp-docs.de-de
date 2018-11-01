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
ms.openlocfilehash: b59191eb739a94f305b656425ee2f3725815c7b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639997"
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

**Namespace:** Platform

**Metadaten:** platform.winmd

## <a name="see-also"></a>Siehe auch

[Platform::COMException-Klasse](../cppcx/platform-comexception-class.md)