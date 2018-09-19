---
title: 'Platform:: IDisposable-Schnittstelle | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
dev_langs:
- C++
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c596e4054729855ea3c8caedf632ca8dd50b796a
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105067"
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

**Namespace:** Platform