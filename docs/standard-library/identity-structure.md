---
title: identity-Struktur
ms.date: 11/04/2016
f1_keywords:
- utility/std::identity
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
ms.openlocfilehash: 49b2c1eb3ca03f9bf9199bdbca49348866ff0a7e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246165"
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

*Links*\
Der zu identifizierende Wert.

## <a name="remarks"></a>Hinweise

Die Klasse enthält die öffentliche Typdefinition `type`, was dem Vorlagenparametertyp entspricht. Es wird in Verbindung mit der Vorlagenfunktion [forward](../standard-library/utility-functions.md#forward) verwendet, um sicherzustellen, dass ein Funktionsparameter den gewünschten Typ aufweist.

Für die Kompatibilität mit älteren Codes, definiert die Klasse auch die Identity-Funktion `operator()` Arguments zurückgegeben *linken*.
