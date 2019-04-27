---
title: _com_error::Error
ms.date: 11/04/2016
f1_keywords:
- _com_error::Error
- Error
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
ms.openlocfilehash: 606f553060e71ece18b3d48159ec40133be28965
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155097"
---
# <a name="comerrorerror"></a>_com_error::Error

**Microsoft-spezifisch**

Ruft den HRESULT-Wert an den Konstruktor übergeben.

## <a name="syntax"></a>Syntax

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>Rückgabewert

Unformatierte HRESULT-Elemente, die an den Konstruktor übergeben werden.

## <a name="remarks"></a>Hinweise

Ruft das gekapselte HRESULT-Element in einem `_com_error` Objekt.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_com_error-Klasse](../cpp/com-error-class.md)