---
title: 'Platform:: accessdeniedexception-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
dev_langs:
- C++
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c87cdc55359fbdd4855a062a3b1b56384c3be574
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104185"
---
# <a name="platformaccessdeniedexception-class"></a>Platform::AccessDeniedException-Klasse

Wird ausgelöst, wenn der Zugriff auf eine Ressource oder eine Funktion verweigert wird.

## <a name="syntax"></a>Syntax

```cpp
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable
```

### <a name="remarks"></a>Hinweise

Wenn Sie diese Ausnahme erreicht haben, stellen Sie sicher, dass Sie die entsprechende Funktion angefordert und die erforderlichen Deklarationen im Paketmanifest der App angegeben haben. Weitere Informationen finden Sie unter [COMException](../cppcx/platform-comexception-class.md) .

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Platform

**Metadaten:** platform.winmd

## <a name="see-also"></a>Siehe auch

[Platform::COMException-Klasse](../cppcx/platform-comexception-class.md)