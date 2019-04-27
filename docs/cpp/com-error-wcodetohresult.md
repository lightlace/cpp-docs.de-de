---
title: _com_error::WCodeToHRESULT
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCodeToHRESULT
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
ms.openlocfilehash: f2fc84be53d95754d21c30eaea8dd981447453d6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154928"
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

*wCode*<br/>
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