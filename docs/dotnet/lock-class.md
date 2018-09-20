---
title: Lock-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs:
- C++
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7ef0887ca3eec7510717aab21ba4c6c7aba98d25
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380294"
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