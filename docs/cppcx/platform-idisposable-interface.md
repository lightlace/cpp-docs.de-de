---
title: Platform::IDisposable-Schnittstelle
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
ms.openlocfilehash: f114959321c0ed3879a089b944a5ff1b19843118
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257828"
---
# <a name="platformidisposable-interface"></a>Platform::IDisposable-Schnittstelle

Wird verwendet, um nicht verwaltete Ressourcen freizugeben.

## <a name="syntax"></a>Syntax

```cpp
public interface class IDisposable
```

## <a name="attributes"></a>Attribute

**GuidAttribute**("de0cbaea-8065-4a45-b196-c9d443f9bab3")

**VersionAttribute**(NTDDI_WIN8)

### <a name="members"></a>Member

Die IDisposable-Schnittstelle erbt von der IUnknown-Schnittstelle. IDisposable verfügt auch über die folgenden Membertypen:

**Methoden**

Die IDisposable-Schnittstelle verfügt über die folgenden Methoden.

|Methode|Beschreibung|
|------------|-----------------|
|Löschen|Wird verwendet, um nicht verwaltete Ressourcen freizugeben.|

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Plattform