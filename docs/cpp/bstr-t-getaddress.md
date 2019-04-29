---
title: _bstr_t::GetAddress
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.assetid: 09bc9180-867e-4ee5-b22a-8339dc663142
ms.openlocfilehash: 4d51539d2afbb2fbcc860b6c4d821df119aca418
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393895"
---
# <a name="bstrtgetaddress"></a>_bstr_t::GetAddress

**Microsoft-spezifisch**

Setzt etwaig vorhandene Zeichenfolgen frei und gibt die Adresse einer neu zugeordneten Zeichenfolge zurück.

## <a name="syntax"></a>Syntax

```
BSTR* GetAddress( );
```

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf den `BSTR` umschlossen von `_bstr_t`.

## <a name="remarks"></a>Hinweise

**GetAddress** wirkt sich auf alle `_bstr_t` Objekte die Freigabe einer `BSTR`. Mehr als eine `_bstr_t` können Freigeben einer `BSTR` durch die Verwendung des Kopierkonstruktors und **Operator =**.

## <a name="example"></a>Beispiel

Finden Sie unter [_bstr_t:: Assign](../cpp/bstr-t-assign.md) ein mit **GetAddress**.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_bstr_t-Klasse](../cpp/bstr-t-class.md)