---
title: Linkertoolfehler LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: ce5332c2812740ef0b8c7d8e9c64a095d20a4e2b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299054"
---
# <a name="linker-tools-error-lnk2017"></a>Linkertoolfehler LNK2017

'Symbol'-Umsetzung zu "Segment" ist ohne/LARGEADDRESSAWARE: No ungültig.

Sie möchten eine 64-Bit-Image mit 32-Bit-Adressen zu erstellen. Zu diesem Zweck müssen Sie folgende Aktionen ausführen:

- Verwenden Sie eine feste Adresse an.

- Beschränken Sie die Anwendung auf 3 GB.

- Geben Sie [: No](../../build/reference/largeaddressaware-handle-large-addresses.md).