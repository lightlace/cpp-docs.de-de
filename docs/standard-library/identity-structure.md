---
title: identity Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- utility/std::identity
dev_langs:
- C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f065f7c00d3853d00c1063cd5b2838ec6d1d27b4
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38952996"
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
