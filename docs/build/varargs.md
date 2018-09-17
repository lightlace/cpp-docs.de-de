---
title: Varargs | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8305eaddf87a2e67b797bedff1944dbcbbbdbd41
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713647"
---
# <a name="varargs"></a>VarArgs

Übergeben von Parametern über Varargs (z. B. mit den Auslassungspunkten Argumente) gilt im Wesentlichen die normale Parameter übergeben, einschließlich dem Zwischenspeichern die fünfte und nachfolgende Argumente. Es ist wieder die aufgerufene Dump-Argumente, die deren Adresse akzeptiert haben. Nur Gleitkommawerte enthält sowohl die ganze Zahl im Gleitkommaregister den Float-Wert und für den Fall, dass der aufgerufene den Wert in die Ganzzahlregister erwartet.

## <a name="see-also"></a>Siehe auch

[Aufrufkonvention](../build/calling-convention.md)