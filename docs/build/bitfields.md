---
title: Bitfelder | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- bitfields
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85db49f138cc733326e47a3008e79bae5ab4b7cb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360779"
---
# <a name="bitfields"></a>Bitfelder
Struktur-Bitfelder sind auf 64 Bits beschränkt und kann vom Typ Int, Int ohne Vorzeichen, int64 oder ohne Vorzeichen int64 signiert. Bitfelder, die Typ-Anwendungsgrenze überschreiten, überspringt Bits das Bitfeld in die nächste Typ Ausrichtung ausrichten. Beispielsweise kann ganze Zahl Bitfelder keine 32-Bit-überschreiten.  
  
## <a name="see-also"></a>Siehe auch  
 [Typen und Speicher](../build/types-and-storage.md)