---
title: '_com_error:: wcode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCode
dev_langs:
- C++
helpviewer_keywords:
- WCode method [C++]
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da4ad7d7f06c9cb6ae1a75a4c17cc63b377a9845
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036513"
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