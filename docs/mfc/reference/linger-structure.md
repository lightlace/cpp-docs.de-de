---
title: LINGER-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LINGER
dev_langs:
- C++
helpviewer_keywords:
- LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2dda3aab3c4a967c82a699058868edc8fc183984
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46386378"
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

