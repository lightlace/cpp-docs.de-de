---
title: SOCKADDR_IN-Struktur
ms.date: 11/04/2016
f1_keywords:
- SOCKADDR_IN
helpviewer_keywords:
- SOCKADDR_IN structure [MFC]
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
ms.openlocfilehash: 22d02b2e3c6fd7151e59cad0f3233539c04a16e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431225"
---
# <a name="sockaddrin-structure"></a>SOCKADDR_IN-Struktur

In der Internetadressenfamilie wird die `SOCKADDR_IN`-Struktur von Windows Sockets verwendet, um eine lokale oder Remoteendpunktadresse festlegen, mit der ein Socket verbunden werden soll.

## <a name="syntax"></a>Syntax

```
struct sockaddr_in{
    short sin_family;
    unsigned short sin_port;
struct in_addr sin_addr;
    char sin_zero[8];
};
```

#### <a name="parameters"></a>Parameter

*sin_family*<br/>
-Adressenfamilie (muss AF_INET sein).

*sin_port*<br/>
IP-Port.

*sin_addr*<br/>
IP-Adresse.

*sin_zero*<br/>
Auffüllung, um die Struktur ebenso groß wie `SOCKADDR` zu machen.

## <a name="remarks"></a>Hinweise

Dies ist die Form der `SOCKADDR`-Struktur speziell für die Internetadressenfamilie; sie kann in `SOCKADDR` umgewandelt werden.

Die IP-Adressenkomponente dieser Struktur ist vom Typ `IN_ADDR`. Die `IN_ADDR` Struktur wird in Windows Sockets-Headerdatei WINSOCK definiert. H wie folgt:

```
struct in_addr {
    union {
        struct {
            unsigned char s_b1, s_b2, s_b3, s_b4;
        } S_un_b;
        struct {
            unsigned short s_w1, s_w2;
        } S_un_w;
        unsigned long S_addr;
    } S_un;
};
```

## <a name="requirements"></a>Anforderungen

**Header:** winsock2.h

## <a name="see-also"></a>Siehe auch

[Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[SOCKADDR-Struktur](../../mfc/reference/sockaddr-structure.md)
