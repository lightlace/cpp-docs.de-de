---
title: _com_error::HRESULTToWCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::HRESULTToWCode
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
ms.openlocfilehash: d89503e822d92bf6a1fcb2b6bb658d532af32c5d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581232"
---
# <a name="comerrorhresulttowcode"></a>_com_error::HRESULTToWCode

**Microsoft-spezifisch**

Ordnet 32-Bit-HRESULT 16-Bit- `wCode`.

## <a name="syntax"></a>Syntax

```
static WORD HRESULTToWCode(
   HRESULT hr
) throw( );
```

#### <a name="parameters"></a>Parameter

*HR*<br/>
Die 32-Bit-HRESULT in 16-Bit zugeordnet werden `wCode`.

## <a name="return-value"></a>Rückgabewert

16-Bit- `wCode` von 32-Bit-HRESULT zugeordnet.

## <a name="remarks"></a>Hinweise

Finden Sie unter [_com_error:: wcode](../cpp/com-error-wcode.md) für Weitere Informationen.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error-Klasse](../cpp/com-error-class.md)