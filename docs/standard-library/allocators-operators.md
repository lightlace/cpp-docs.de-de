---
title: '&lt;Allocators&gt;-Operatoren'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: b7429e298cdf14d727fc481db6c4a3bf8574b5e7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430263"
---
# <a name="ltallocatorsgt-operators"></a>&lt;Allocators&gt;-Operatoren

Hierbei handelt es sich um die globale Operator Vorlagenfunktionen in definierten &lt;Zuweisungen&gt;. Operator Memberfunktionen von Klassen finden Sie in der Dokumentation der Klasse.

|||
|-|-|
|[Operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Es wird auf Ungleichheit zwischen Zuweisungsobjekten einer bestimmten Klasse getestet.

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Eines der Zuweisungsobjekte, die auf Ungleichheit geprüft werden sollen.|
|*right*|Eines der Zuweisungsobjekte, die auf Ungleichheit geprüft werden sollen.|

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Zuweisungsobjekte nicht gleich sind; **FALSE**, wenn die Zuweisungsobjekte gleich sind.

### <a name="remarks"></a>Hinweise

Der Vorlagenoperator gibt `!(left == right)` zurück.

## <a name="op_eq_eq"></a> operator==

Es wird auf Gleichheit zwischen Zuweisungsobjekten einer bestimmten Klasse getestet.

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Eines der Zuweisungsobjekte, die auf Gleichheit geprüft werden sollen.|
|*right*|Eines der Zuweisungsobjekte, die auf Gleichheit geprüft werden sollen.|

### <a name="return-value"></a>Rückgabewert

**TRUE**, wenn die Zuweisungsobjekte gleich sind; **FALSE**, wenn die Zuweisungsobjekte nicht gleich sind.

### <a name="remarks"></a>Hinweise

Dieser Vorlagenoperator gibt `left.equals(right)` zurück.

## <a name="see-also"></a>Siehe auch

[\<allocators>](../standard-library/allocators-header.md)
