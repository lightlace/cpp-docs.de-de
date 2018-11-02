---
title: Platform::DisconnectedException-Klasse
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::DisconnectedException
- VCCORLIB/Platform::DisconnectedException::DisconnectedException
helpviewer_keywords:
- Platform::DisconnectedException
ms.assetid: c25e0d64-5bff-4c21-88e5-c4ec2776fa7f
ms.openlocfilehash: 2d4f8f4cb52fdb7e50c36eb3f0255bd85c15dbb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477141"
---
# <a name="platformdisconnectedexception-class"></a>Platform::DisconnectedException-Klasse

Wird ausgelöst, wenn ein COM-Proxyobjekt versucht, auf einen COM-Server zu verweisen, der nicht mehr vorhanden ist.

## <a name="syntax"></a>Syntax

```
public ref class DisconnectedException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>Hinweise

Wenn Klasse A auf eine andere Klasse verweist (Klasse B), die sich in einem gesonderten Prozess befindet, erfordert Klasse A ein Proxyobjekt für die Kommunikation mit dem prozessexternen COM-Server, der die Klasse B enthält. Manchmal kann der Server über keinen Arbeitsspeicher mehr verfügen, ohne dass Klasse A dies bemerkt. In diesem Fall wird die RPC_E_DISCONNECTED-Ausnahme ausgelöst, und sie wird in "Platform::DisconnectedException" übersetzt. Ein Szenario, in dem dies auftritt, ist, wenn eine Ereignisquelle einen Delegaten aufruft, der an sie übergeben wurde, wobei der Delegat aber zu einem Zeitpunkt, nachdem er das Ereignis abonniert hatte, zerstört wurde. Wenn es hierzu kommt, entfernt die Ereignisquelle diesen Delegaten aus ihrer Aufrufliste.

Weitere Informationen finden Sie unter der [COMException](../cppcx/platform-comexception-class.md) -Klasse.

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Platform

**Metadaten:** platform.winmd

## <a name="see-also"></a>Siehe auch

[Platform::COMException-Klasse](../cppcx/platform-comexception-class.md)