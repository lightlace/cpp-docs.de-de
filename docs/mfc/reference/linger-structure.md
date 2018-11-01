---
title: LINGER-Struktur
ms.date: 11/04/2016
f1_keywords:
- LINGER
helpviewer_keywords:
- LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
ms.openlocfilehash: 78f1a5ce993373ea9e477262f0779515c52dbd8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495316"
---
# <a name="linger-structure"></a>LINGER-Struktur

Die `LINGER` Struktur dient zum Bearbeiten der Optionen SO_LINGER und SO_DONTLINGER des `CAsyncSocket::GetSockOpt`.

## <a name="syntax"></a>Syntax

```
struct linger {
    u_short l_onoff;            // option on/off
    u_short l_linger;           // linger time
};
```

## <a name="remarks"></a>Hinweise

Festlegen der SO_DONTLINGER-Option wird verhindert, dass Blockierung auf Memberfunktion `Close` beim Warten auf nicht gesendeter Daten gesendet werden sollen. Das Festlegen dieser Option entspricht dem Festlegen von SO_LINGER mit `l_onoff` auf 0 festgelegt.

## <a name="requirements"></a>Anforderungen

**Header:** winsock2.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)<br/>
[CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)

