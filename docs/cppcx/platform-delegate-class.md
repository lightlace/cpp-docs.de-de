---
title: Platform::Delegate-Klasse
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Delegate
helpviewer_keywords:
- Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
ms.openlocfilehash: 6a509827b3b8e14b6d28995b5b4ca468ee9a662e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741171"
---
# <a name="platformdelegate-class"></a>Platform::Delegate-Klasse

Darstellen eines Funktionsobjekts.

## <a name="syntax"></a>Syntax

```cpp
public delegate void delegate_name();
```

### <a name="members"></a>Member

Die Delegate-Klasse umfasst die Methoden Equals(), GetHashCode() und ToString(), die von der [Platform::Object Class](../cppcx/platform-object-class.md)abgeleitet werden.

### <a name="remarks"></a>Hinweise

Verwenden Sie das Schlüsselwort [delegate](../windows/delegate-cpp-component-extensions.md) , um Delegaten zu erstellen. Verwenden Sie nicht explizit „Platform::Delegate“. Weitere Informationen finden Sie unter [Delegaten](../cppcx/delegates-c-cx.md). Ein Beispiel zum Erstellen und Verwenden eines Delegaten finden Sie unter [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Plattform

**Metadaten:** platform.winmd

## <a name="see-also"></a>Siehe auch

[Platform-namespace](../cppcx/platform-namespace-c-cx.md)
