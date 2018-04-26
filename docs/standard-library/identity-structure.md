---
title: identity Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- utility/std::identity
dev_langs:
- C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
caps.latest.revision: 15
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 991333f279053d19ec27fda86ea0bf769371fd90
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
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
|`left`|Der zu identifizierende Wert.|

## <a name="remarks"></a>Hinweise

Die Klasse enthält die öffentliche Typdefinition `type`, was dem Vorlagenparametertyp entspricht. Es wird in Verbindung mit der Vorlagenfunktion [forward](../standard-library/utility-functions.md#forward) verwendet, um sicherzustellen, dass ein Funktionsparameter den gewünschten Typ aufweist.

Aufgrund der Kompatibilität mit älteren Codes definiert die Klasse auch die identity-Funktion `operator()`, welche deren Argument `left` zurückgibt.

## <a name="requirements"></a>Anforderungen

**Header:** \<utility>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[\<utility>](../standard-library/utility.md)<br/>
