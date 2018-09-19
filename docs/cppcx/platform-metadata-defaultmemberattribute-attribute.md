---
title: Platform::Metadata::DefaultMemberAttribute-Attribut | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata::DefaultMemberAttribute
dev_langs:
- C++
helpviewer_keywords:
- Platform::Metadata::DefaultMemberAttribute Attribute
ms.assetid: d8abda01-c257-4371-aec4-541d4825e0af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54959b293752ac0453ba383f86ab225e0b45e471
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106995"
---
# <a name="platformmetadatadefaultmemberattribute-attribute"></a>Platform::Metadata::DefaultMemberAttribute-Attribut

Gibt die bevorzugte Funktion an, um unter mehreren möglichen überladenen Funktionen aufzurufen.

## <a name="syntax"></a>Syntax

```cpp
public ref class DefaultMember abstract : Attribute
```

## <a name="inheritance"></a>Vererbung

[Platform::Object](../cppcx/platform-object-class.md)

[Platform::Metadata::Attribute](../cppcx/platform-metadata-attribute-attribute.md)

### <a name="remarks"></a>Hinweise

Wenden Sie das DefaultMember-Attribut auf eine Methode an, die von einer JavaScript-Anwendung verwendet wird.

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Platform::Metadata

**Metadaten:** platform.winmd

## <a name="see-also"></a>Siehe auch

[Platform::Metadata-Namespace](../cppcx/platform-metadata-namespace.md)