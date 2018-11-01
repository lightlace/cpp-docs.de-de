---
title: _bstr_t::copy
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::copy
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
ms.openlocfilehash: 13ddf57e0bdbdbcc0c5b487e879e14b000de3ad0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506837"
---
# <a name="bstrtcopy"></a>_bstr_t::copy

**Microsoft-spezifisch**

Erstellt eine Kopie des gekapselten `BSTR`.

## <a name="syntax"></a>Syntax

```
BSTR copy( bool fCopy = true ) const;
```

#### <a name="parameters"></a>Parameter

*fCopy*<br/>
True gibt an, **Kopie** gibt eine Kopie des enthaltenen `BSTR`, andernfalls **Kopie** den tatsächlichen BSTR zurück.

## <a name="remarks"></a>Hinweise

Gibt eine neu zugeordnete Kopie des gekapselten `BSTR`-Objekts zurück.

## <a name="example"></a>Beispiel

```cpp
STDMETHODIMP CAlertMsg::get_ConnectionStr(BSTR *pVal){ //  m_bsConStr is _bstr_t
   *pVal = m_bsConStr.copy();
}
```

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_bstr_t-Klasse](../cpp/bstr-t-class.md)