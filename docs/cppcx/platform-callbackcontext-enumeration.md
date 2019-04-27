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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161665"
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

**Namespace:** Plattform

**Metadaten:** platform.winmd