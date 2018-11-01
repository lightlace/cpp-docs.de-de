---
title: Linkertoolwarnung LNK4219
ms.date: 11/04/2016
f1_keywords:
- LNK4219
helpviewer_keywords:
- LNK4219
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
ms.openlocfilehash: 7407537b55525bf622fc11cdbdb8e00244e51c18
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598249"
---
# <a name="linker-tools-warning-lnk4219"></a>Linkertoolwarnung LNK4219

Fixup Namen Fixup-Überlauf. Ziel "Zielsymbolname" ist außerhalb des gültigen Bereichs, Thunk wird eingefügt.

Der Linker eingefügt einen Thunk in einer Situation, in dem der Offset oder der Adresse konnte nicht in die angegebene Anweisung nicht finden, da das Zielsymbol zu weit entfernt von Zielsymbol und vorhanden ist.

Möglicherweise möchten Sie die Anwendung neu anordnen (mithilfe der [/ORDER](../../build/reference/order-put-functions-in-order.md) -Option verwenden, z. B.), das zusätzliche Maß an Dereferenzierung zu vermeiden.