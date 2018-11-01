---
title: Platform::CallbackContext-Enumeration
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
ms.openlocfilehash: 7f4e020ab0b1e377456c27d3b4666e15b5a4f7a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441353"
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext-Enumeration

Gibt den Threadkontext an, in dem eine Rückruffunktion (Ereignishandler) ausgeführt wird.

## <a name="syntax"></a>Syntax

```cpp
enum class CallbackContext {};
```

### <a name="members"></a>Member

|Typcode|Beschreibung|
|---------------|-----------------|
|Beliebig|Die Rückruffunktion kann in jedem beliebigen Threadkontext ausgeführt werden.|
|Gleiche Voraussetzung|Die Rückruffunktion kann nur in dem Threadkontext ausgeführt werden, der den asynchronen Vorgang gestartet hat.|

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Platform

**Metadaten:** platform.winmd