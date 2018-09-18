---
title: Linkertoolfehler Lnk2017 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2017
dev_langs:
- C++
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80af2bb6475fc37b7feba5b29bfe9c1292740286
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022449"
---
# <a name="linker-tools-error-lnk2017"></a>Linkertoolfehler LNK2017

'Symbol'-Umsetzung zu "Segment" ist ohne/LARGEADDRESSAWARE: No ungültig.

Sie möchten eine 64-Bit-Image mit 32-Bit-Adressen zu erstellen. Zu diesem Zweck müssen Sie folgende Aktionen ausführen:

- Verwenden Sie eine feste Adresse an.

- Beschränken Sie die Anwendung auf 3 GB.

- Geben Sie [: No](../../build/reference/largeaddressaware-handle-large-addresses.md).