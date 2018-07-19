---
title: independent_bits_engine-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::independent_bits_engine
dev_langs:
- C++
helpviewer_keywords:
- independent_bits_engine class
ms.assetid: 889e9a82-f457-49a7-9d2e-26e0fc3cd907
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f802dc91c3429ba718778d122d1a787aad0dec87
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964222"
---
# <a name="independentbitsengine-class"></a>independent_bits_engine-Klasse

Generiert eine zufällige Zahlensequenz mit einer angegebenen Anzahl von Bits, indem Bits aus von der Basis-Engine zurückgegebenen Werten erneut verpackt werden.

## <a name="syntax"></a>Syntax

```cpp
template <class Engine, size_t W, class UIntType>
class independent_bits_engine;
```

### <a name="parameters"></a>Parameter

*Engine* den Basis-Engine-Typ.

*W* **Wortgröße**. Größe jeder generierten Zahl in Bits. **Vorbedingung**:`0 < W ≤ numeric_limits<UIntType>::digits`

*UIntType* der Ergebnistyp für die ganze Zahl ohne Vorzeichen. Mögliche Typen finden Sie unter [\<random>](../standard-library/random.md).

## <a name="members"></a>Member

||||
|-|-|-|
|`independent_bits_engine::independent_bits_engine`|`independent_bits_engine::base`|`independent_bits_engine::discard`|
|`independent_bits_engine::operator()`|`independent_bits_engine::base_type`|`independent_bits_engine::seed`|

Weitere Informationen über Engine-Member finden Sie unter [\<random&gt;](../standard-library/random.md).

## <a name="remarks"></a>Hinweise

Diese Vorlagenklasse beschreibt ein *Moduladapter* , der Werte produziert, indem Sie die Rückgabewerte von seinem Moduladapter, wodurch Moduladapter *W*-bit-Werten.

## <a name="requirements"></a>Anforderungen

**Header:** \<random>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<random>](../standard-library/random.md)<br/>
