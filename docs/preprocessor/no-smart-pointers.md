---
title: no_smart_pointers
ms.date: 11/04/2016
f1_keywords:
- no_search_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: ed4950b9e90ef968fcf0c42e4f0a9775c58ea7ec
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030166"
---
# <a name="nosmartpointers"></a>no_smart_pointers
**C++-spezifisch**

Unterdrückt die Erstellung von intelligenten Zeigern für alle Schnittstellen in der Typbibliothek.

## <a name="syntax"></a>Syntax

```
no_smart_pointers
```

## <a name="remarks"></a>Hinweise

Wenn Sie `#import` verwenden, rufen Sie standardmäßig die Deklaration eines intelligenten Zeigers für alle Schnittstellen in der Typbibliothek ab. Diese intelligenten Zeiger sind vom Typ [_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md).

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)