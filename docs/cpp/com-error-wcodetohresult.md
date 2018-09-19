---
title: _com_error::WCodeToHRESULT | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCodeToHRESULT
dev_langs:
- C++
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5b6712734cd7283558ad5776444586f8c0b3fa6e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077567"
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT

**Microsoft-spezifisch**

Ordnet die 16-Bit- *wCode* in 32-Bit-HRESULT.

## <a name="syntax"></a>Syntax

```
static HRESULT WCodeToHRESULT(
   WORD wCode
) throw( );
```

#### <a name="parameters"></a>Parameter

*WCode*<br/>
Die 16-Bit- *wCode* , 32-Bit-HRESULT zugeordnet werden soll.

## <a name="return-value"></a>Rückgabewert

zugeordnet aus dem 16-Bit-32-Bit-HRESULT *wCode*.

## <a name="remarks"></a>Hinweise

Finden Sie unter den [WCode](../cpp/com-error-wcode.md) Member-Funktion.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error::WCode](../cpp/com-error-wcode.md)<br/>
[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error-Klasse](../cpp/com-error-class.md)