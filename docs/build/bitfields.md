---
title: Bitfelder | Microsoft-Dokumentation
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
ms.openlocfilehash: a7451ea6afee81cc296fb091705bde48041ef5d1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722487"
---
# <a name="bitfields"></a>Bitfelder

Struktur-Bitfelder sind auf 64-Bit beschränkt und kann vom Typ signiert Int "," unsigned Int "," int64 "oder" nicht-signierter int64. Bitfelder, die die Typgrenze überschreiten, werden Bits das Bitfeld der Ausrichtung der nächsten Typ ausrichten übersprungen. Beispielsweise können ganzzahlige Bitfeldern keine 32-Bit-überschreiten.

## <a name="see-also"></a>Siehe auch

[Typen und Speicher](../build/types-and-storage.md)