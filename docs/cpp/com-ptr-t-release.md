---
title: _com_ptr_t::Release
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t.Release
- _com_ptr_t::Release
helpviewer_keywords:
- Release method [C++]
ms.assetid: db448b34-0efa-4f02-b701-ad1ca3ae6ca5
ms.openlocfilehash: cf4cea35386d1f781d6d2946c1730ba2e18dacea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399225"
---
# <a name="comptrtrelease"></a>_com_ptr_t::Release

**Microsoft-spezifisch**

Ruft die **Version** Memberfunktion `IUnknown` für den gekapselten Schnittstellenzeiger auf.

## <a name="syntax"></a>Syntax

```
void Release( );
```

## <a name="remarks"></a>Hinweise

Aufrufe `IUnknown::Release` für den gekapselten Schnittstellenzeiger, Auslösen einer `E_POINTER` Fehler, wenn dieser Schnittstellenzeiger NULL ist.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)