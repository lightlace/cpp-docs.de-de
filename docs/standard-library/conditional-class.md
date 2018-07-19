---
title: conditional-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::conditional
dev_langs:
- C++
helpviewer_keywords:
- conditional class
- conditional
ms.assetid: ece9f539-fb28-4e26-a79f-3264bc984493
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57e01cbfd7cb291ff7d2651e3244b74ae96adbea
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962399"
---
# <a name="conditional-class"></a>conditional-Klasse

Wählt einen von zwei Typen, abhängig von der angegebenen Bedingung.

## <a name="syntax"></a>Syntax

```cpp
template <bool B, class T1, class T2>
struct conditional;

template <bool _Test, class _T1, class _T2>
using conditional_t = typename conditional<_Test, _T1, _T2>::type;
```

### <a name="parameters"></a>Parameter

*B* der Wert, der den ausgewählten Typ bestimmt.

*T1* das typergebnis, wenn B auf "true" festgelegt ist.

*T2* das typergebnis, wenn B "false" ist.

## <a name="remarks"></a>Hinweise

Der TypeDef-Member von Vorlage `conditional<B, T1, T2>::type` ergibt *T1* beim *B* ergibt **"true"**, und ergibt *T2* beim  *B* ergibt **"false"**.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
