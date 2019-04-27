---
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: affaefd8af4802836733587af62977171ba01410
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154960"
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach

**Microsoft-spezifisch**

Extrahiert den gekapselten Schnittstellenzeiger und gibt ihn zurück.

## <a name="syntax"></a>Syntax

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>Hinweise

Extrahiert und gibt den gekapselten Schnittstellenzeiger zurück, und löscht dann den Speicher des gekapselten Zeigers auf NULL. Dadurch wird der Schnittstellenzeiger aus der Kapselung entfernt. Es liegt bei Ihnen Aufrufen `Release` für den zurückgegebenen Schnittstellenzeiger auf.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)