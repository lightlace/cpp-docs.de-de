---
title: _bstr_t::Copy | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _bstr_t::copy
dev_langs:
- C++
helpviewer_keywords:
- Copy method [C++]
- BSTR object [C++], copy
ms.assetid: 00ba7311-e82e-4a79-8106-5329fa2f869a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50f9a17c93849dec49c2c9a72825a5797d8c040c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068623"
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