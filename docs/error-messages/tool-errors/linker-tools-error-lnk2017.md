---
title: Linkertoolfehler LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: ce5332c2812740ef0b8c7d8e9c64a095d20a4e2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641458"
---
# <a name="linker-tools-error-lnk2017"></a>Linkertoolfehler LNK2017

'Symbol'-Umsetzung zu "Segment" ist ohne/LARGEADDRESSAWARE: No ungültig.

Sie möchten eine 64-Bit-Image mit 32-Bit-Adressen zu erstellen. Zu diesem Zweck müssen Sie folgende Aktionen ausführen:

- Verwenden Sie eine feste Adresse an.

- Beschränken Sie die Anwendung auf 3 GB.

- Geben Sie [: No](../../build/reference/largeaddressaware-handle-large-addresses.md).