---
title: lock-Klasse
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
ms.openlocfilehash: 8876810b15a7d2736f2c8ab0ca1f4c6011918a5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547133"
---
# <a name="lock-class"></a>lock-Klasse

Diese Klasse automatisiert die Verwendung einer Sperre für den Zugriff auf ein Objekt von mehreren Threads zu synchronisieren.  Bei der Erstellung Ruft die Sperre, und wenn es sich um Versionen zerstört die Sperre.

## <a name="syntax"></a>Syntax

```
ref class lock;
```

## <a name="remarks"></a>Hinweise

`lock` ist nur für CLR-Objekte verfügbar und kann nur in CLR-Code verwendet werden.

Intern wird die Lock-Klasse verwendet <xref:System.Threading.Monitor> zum Synchronisieren des Zugriffs. Finden Sie dieses Thema enthält weitere ausführliche Informationen zur Synchronisierung aus.

## <a name="requirements"></a>Anforderungen

**Headerdatei** \<msclr\lock.h >

**Namespace** Msclr

## <a name="see-also"></a>Siehe auch

[lock](../dotnet/lock.md)<br/>
[lock-Members](../dotnet/lock-members.md)