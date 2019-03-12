---
title: Platform::FailureException-Klasse
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::FailureException::FailureException
- VCCORLIB/Platform::FailureException
helpviewer_keywords:
- Platform::FailureException
ms.assetid: 1729cd07-bfc2-448e-9db5-185d5cbf5b81
ms.openlocfilehash: f527271b50382a9aec1585e139a0083135315473
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750323"
---
# <a name="platformfailureexception-class"></a>Platform::FailureException-Klasse

Wird ausgelöst, wenn bei dem Vorgang ein Fehler aufgetreten ist. Dies entspricht dem E_FAIL HRESULT.

## <a name="syntax"></a>Syntax

```cpp
public ref class FailureException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter der [COMException](../cppcx/platform-comexception-class.md) -Klasse.

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Plattform

**Metadaten:** platform.winmd

## <a name="see-also"></a>Siehe auch

[Platform::COMException-Klasse](../cppcx/platform-comexception-class.md)
