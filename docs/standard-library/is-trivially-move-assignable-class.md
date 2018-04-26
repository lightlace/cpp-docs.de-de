---
title: is_trivially_move_assignable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_move_assignable
ms.assetid: 374f7322-0706-4bc1-a1a5-4191d0315e28
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee7fb3e92064ebced6390c0eaf81fc68552381ca
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallymoveassignable-class"></a>is_trivially_move_assignable-Klasse

Testet, ob der Typ einen trivialen Verschiebezuweisungsoperator aufweist.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Parameter

`Ty` Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist „true“, wenn der `Ty`-Typ eine Klasse ist, die einen Verschiebungszuweisungsoperator aufweist; andernfalls „false“.

Ein Verschiebungszuweisungsoperator für eine `Ty`-Klasse ist in den folgenden Fällen trivial:

Er wird impliziert bereitgestellt

Die `Ty`-Klasse hat keine virtuellen Funktionen

Die `Ty`-Klasse hat keine virtuellen Basen

Die Klassen aller nicht statischen Datenmember des Klassentyps haben triviale Verschiebungszuweisungsoperatoren

Die Klassen aller nicht statischen Datenmember des Typarrays der Klasse haben triviale Verschiebungszuweisungsoperatoren

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
