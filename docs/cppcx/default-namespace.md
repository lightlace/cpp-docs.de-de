---
title: Standardnamespace
ms.date: 12/30/2016
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
ms.openlocfilehash: 60a47c9549ee40b419eb5f4aa84720f8dcd1c366
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739191"
---
# <a name="default-namespace"></a>Standardnamespace

Die `default` Namespace umfasst die integrierten Typen, die durch C++ unterstützt c++ / CX.

## <a name="syntax"></a>Syntax

```
namespace default;
```

### <a name="members"></a>Member

Alle integrierte Typen erben die folgenden Member.

|||
|-|-|
|[default::(type_name)::Equals](../cppcx/default-type-name-equals-method.md)|Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.|
|[default::(type_name)::GetHashCode](../cppcx/default-type-name-gethashcode-method.md)|Gibt den Hashcode für diese Instanz zurück.|
|[default::(type_name)::GetType](../cppcx/default-type-name-gettype-method.md)|Gibt eine Zeichenfolge zurück, die den aktuellen Typ darstellt.|
|[default::(type_name)::ToString](../cppcx/default-type-name-tostring-method.md)|Gibt eine Zeichenfolge zurück, die den aktuellen Typ darstellt.|

### <a name="built-in-types"></a>Integrierte Typen

|name|Beschreibung|
|----------|-----------------|
|`char16`|Ein nicht numerischer 16-Bit-Wert, der einen Unicode-Codepunkt (UTF-16) darstellt.|
|`float32`|Eine 32-Bit-IEEE 754-Gleitkommazahl.|
|`float64`|Eine 64-Bit-IEEE 754-Gleitkommazahl.|
|`int16`|Eine 16-Bit-Ganzzahl mit Vorzeichen.|
|`int32`|Eine 32-Bit-Ganzzahl mit Vorzeichen.|
|`int64`|Eine 64-Bit-Ganzzahl mit Vorzeichen.|
|`int8`|Eine numerischer 8-Bit-Wert mit Vorzeichen.|
|`uint16`|Eine 16-Bit-Ganzzahl ohne Vorzeichen.|
|`uint32`|Eine 32-Bit-Ganzzahl ohne Vorzeichen.|
|`uint64`|Eine 64-Bit-Ganzzahl ohne Vorzeichen.|
|`uint8`|Eine numerischer 8-Bit-Wert ohne Vorzeichen.|

### <a name="requirements"></a>Anforderungen

**Header:** vccorlib.h

## <a name="see-also"></a>Siehe auch

[Sprachreferenz zu Visual C++](../cppcx/visual-c-language-reference-c-cx.md)
