---
title: is_trivially_copyable-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivially_copyable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c2e2792c93b477c6d6aac4350045a506eda206eb
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable-Klasse

Testet, ob der Typ ein trivialer Kopiertyp ist.

## <a name="syntax"></a>Syntax

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Parameter

`T` Der abzufragende Typ.

## <a name="remarks"></a>Hinweise

Eine Instanz des Typprädikats ist TRUE, wenn der Typ `T` ein trivialer Kopiertyp ist; andernfalls ist sie FALSE. Triviale Kopiertypen haben keine nicht trivialen Kopiervorgänge, Zuweisungsvorgänge oder Destruktoren. Im Allgemeinen wird ein Kopiervorgang als trivial angesehen, wenn er als eine bitweise Kopie implementiert werden kann. Integrierte Typen und Arrays trivialer Kopiertypen sind jeweils trivial kopierbar.

## <a name="requirements"></a>Anforderungen

**Header:** \<type_traits>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
