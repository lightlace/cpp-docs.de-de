---
title: SOCKADDR-Struktur
ms.date: 11/04/2016
f1_keywords:
- SOCKADDR
helpviewer_keywords:
- SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
ms.openlocfilehash: 68d5261c6520b5baee8495b72a0b9d234a35a185
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543844"
---
# <a name="sockaddr-structure"></a>SOCKADDR-Struktur

Die `SOCKADDR`-Struktur wird verwendet, um die Adresse eines Internetprotokolls (IP) für einen Computer zu speichern, der an einer Windows Socket-Kommunikation teilnimmt.

## <a name="syntax"></a>Syntax

```
struct sockaddr {
    unsigned short sa_family;
    char sa_data[14];
};
```

#### <a name="parameters"></a>Parameter

*sa_family*<br/>
Socketadressenfamilie.

*sa_data*<br/>
Maximale Größe aller verschiedenen Socketadress-Strukturen.

## <a name="remarks"></a>Hinweise

Das Microsoft TCP/IP-Kit des Socket-Entwicklers unterstützt nur die Internetadressendomänen. Um Werte für jeden Teil einer Adresse zu füllen, verwenden Sie die Datenstruktur von `SOCKADDR_IN`, die speziell für dieses Adressenformat vorgesehen ist. Die Datenstrukturen `SOCKADDR` und `SOCKADDR_IN` haben die gleiche Größe. Sie müssen einfach nur umschalten, um zwischen den beiden Strukturtypen zu wechseln.

## <a name="requirements"></a>Anforderungen

**Header:** winsock2.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[SOCKADDR_IN-Struktur](../../mfc/reference/sockaddr-in-structure.md)<br/>
[CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)<br/>
[CSocket::Create](../../mfc/reference/csocket-class.md#create)

