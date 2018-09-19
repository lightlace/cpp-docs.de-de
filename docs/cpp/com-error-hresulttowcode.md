---
title: _com_error::HRESULTToWCode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::HRESULTToWCode
dev_langs:
- C++
helpviewer_keywords:
- HRESULTToWCode method [C++]
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c39b638451aa8ea89191e323eae5f2c140563990
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082065"
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