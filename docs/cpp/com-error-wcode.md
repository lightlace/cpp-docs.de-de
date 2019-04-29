---
title: _com_error::WCode
ms.date: 11/04/2016
f1_keywords:
- _com_error::WCode
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
ms.openlocfilehash: f33871634b516723c94fead847f64ef20d25513f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399316"
---
# <a name="comerrorwcode"></a>_com_error::WCode

**Microsoft-spezifisch**

Ruft ab, der 16-Bit-Fehlercode in der gekapselten HRESULT zugeordnet.

## <a name="syntax"></a>Syntax

```
WORD WCode ( ) const throw( );
```

## <a name="return-value"></a>Rückgabewert

Falls das HRESULT innerhalb des Bereichs 0 x 80040200 bis 0x8004ffff liegt, ist die `WCode` Methode gibt das HRESULT minus 0 x 80040200 zurück; andernfalls wird 0 (null) zurückgegeben.

## <a name="remarks"></a>Hinweise

Die `WCode` Methode wird verwendet, um eine Zuordnung rückgängig zu machen, die in COM-Unterstützungscode vorgenommen wird. Der Wrapper für eine `dispinterface` Eigenschaft oder Methode ruft eine unterstützungsroutine auf, die die Argumente und Aufrufe verpackt `IDispatch::Invoke`. Bei der Rückgabe, wenn ein Fehler-HRESULT von `DISP_E_EXCEPTION` zurückgegeben wird, wird die Fehlerinformationen abgerufen, von der `EXCEPINFO` Zeitstruktur `IDispatch::Invoke`. Der Fehlercode kann entweder ein 16-Bit-Wert, der in gespeicherten der `wCode` Mitglied der `EXCEPINFO` Struktur oder ein vollständiger 32-Bit-Wert in der `scode` Mitglied der `EXCEPINFO` Struktur. Wenn ein 16-Bit `wCode` zurückgegeben wird, müssen Sie zuerst auf einem 32-Bit-Fehler-HRESULT zugeordnet werden.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)<br/>
[_com_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)<br/>
[_com_error-Klasse](../cpp/com-error-class.md)