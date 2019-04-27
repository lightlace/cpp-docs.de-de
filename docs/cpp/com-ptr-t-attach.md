---
title: _com_ptr_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Attach
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
ms.openlocfilehash: 4b4b7a21d12cc645c486dd93d555510c1e716563
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154889"
---
# <a name="comptrtattach"></a>_com_ptr_t::Attach

**Microsoft-spezifisch**

Kapselt einen unformatierten Schnittstellenzeiger vom Typ dieses intelligenten Zeigers.

## <a name="syntax"></a>Syntax

```
void Attach( Interface* pInterface ) throw( );
void Attach( Interface* pInterface, bool fAddRef ) throw( );
```

#### <a name="parameters"></a>Parameter

*pInterface*<br/>
Ein unformatierter Schnittstellenzeiger.

*fAddRef*<br/>
Wenn "true", dann ist `AddRef` aufgerufen wird. Wenn es auf "FALSE" ist die `_com_ptr_t` Objekt übernimmt den Besitz des unformatierten Schnittstellenzeigers, ohne `AddRef`.

## <a name="remarks"></a>Hinweise

- **Anfügen (***pInterface***)** `AddRef` wird nicht aufgerufen. Der Besitz der Schnittstelle wird an dieses `_com_ptr_t`-Objekt übergeben. `Release` wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern.

- **Anfügen (**  *pInterface*  **,**  *fAddRef*  **)** Wenn *fAddRef* ist "true", `AddRef`aufgerufen, um den Verweiszähler für den gekapselten Schnittstellenzeiger zu inkrementieren. Wenn *fAddRef* ist "false", dies `_com_ptr_t` Objekt übernimmt den Besitz des unformatierten Schnittstellenzeigers, ohne `AddRef`. `Release` wird aufgerufen, um den Verweiszähler für den zuvor gekapselten Zeiger zu verringern.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_ptr_t-Klasse](../cpp/com-ptr-t-class.md)