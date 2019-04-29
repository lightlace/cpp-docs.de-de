---
title: Platform::Metadata-Namespace
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata
helpviewer_keywords:
- Platform::Metadata Namespace
ms.assetid: e3e114d8-a4b0-47f0-865a-9ce9d7212e86
ms.openlocfilehash: 9626b3a9d28d28fd52a0d2295af8fda8855cd90c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387603"
---
# <a name="platformmetadata-namespace"></a>Platform::Metadata-Namespace

Dieser Namespace enthält Attribute, die die Deklarationen von Typen ändern.

## <a name="syntax"></a>Syntax

```cpp
namespace Platform {
   namespace Metadata {
}}
```

### <a name="members"></a>Member

Obwohl dieser Namespace für die interne Verwendung vorgesehen ist, können Browser die folgenden Member dieses Namespace anzeigen.

|Name|Hinweis|
|----------|------------|
|Attribut|Die Basisklasse für Attribute.|
|[Platform::Metadata::DefaultMemberAttribute-Attribut](../cppcx/platform-metadata-defaultmemberattribute-attribute.md)|Gibt die bevorzugte Funktion an, um unter mehreren möglichen überladenen Funktionen aufzurufen.|
|[Platform::Metadata::FlagsAttribute-Attribute](../cppcx/platform-metadata-flagsattribute-attribute.md)-Flags|Deklariert eine Enumeration als Enumeration von Bitfeldern.<br /><br /> Im folgenden Beispiel wird gezeigt, wie das `Flags` -Attribut auf eine Enumeration angewendet wird.<br /><br /> `[Flags] enum class MyEnumeration { enumA = 1, enumB = 2, enumC = 3}`|
|[Platform::Metadata::RuntimeClassNameAttribute](../cppcx/platform-metadata-runtimeclassname.md)|Stellt sicher, dass eine private Verweisklasse einen gültigen Laufzeitklasse-Namen hat.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`Platform`

### <a name="requirements"></a>Anforderungen

**Metadaten:** platform.winmd

**Namespace:** Platform::Metadata

## <a name="see-also"></a>Siehe auch

[Plattform-Namespace](platform-namespace-c-cx.md)
