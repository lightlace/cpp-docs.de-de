---
title: _com_ptr_t::Detach | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7f2f44df96ca339e5d8e4b251b5f2d259cb606b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092140"
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