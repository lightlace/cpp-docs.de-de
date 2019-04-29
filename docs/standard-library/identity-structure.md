---
title: identity-Struktur
ms.date: 11/04/2016
f1_keywords:
- utility/std::identity
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
ms.openlocfilehash: 722eb9c0579d0c07765434127d0a7c43718fbc37
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404997"
---
# <a name="identity-structure"></a>identity-Struktur

Eine Struktur, die eine Typdefinition als den Vorlagenparameter bereitstellt.

## <a name="syntax"></a>Syntax

```cpp
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
   };
```

### <a name="parameters"></a>Parameter

|Parameter|Beschreibung|
|---------------|-----------------|
|*left*|Der zu identifizierende Wert.|

## <a name="remarks"></a>Hinweise

Die Klasse enthält die öffentliche Typdefinition `type`, was dem Vorlagenparametertyp entspricht. Es wird in Verbindung mit der Vorlagenfunktion [forward](../standard-library/utility-functions.md#forward) verwendet, um sicherzustellen, dass ein Funktionsparameter den gewünschten Typ aufweist.

Für die Kompatibilität mit älteren Codes, definiert die Klasse auch die Identity-Funktion `operator()` Arguments zurückgegeben *linken*.

## <a name="requirements"></a>Anforderungen

**Header:** \<utility>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<utility>](../standard-library/utility.md)<br/>
