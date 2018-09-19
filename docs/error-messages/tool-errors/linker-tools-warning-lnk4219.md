---
title: Linkertoolwarnung LNK4219 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4219
dev_langs:
- C++
helpviewer_keywords:
- LNK4219
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: daf097cd8715a7c523e6e8a2ea46714481ca7d2a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46105207"
---
# <a name="linker-tools-warning-lnk4219"></a>Linkertoolwarnung LNK4219

Fixup Namen Fixup-Überlauf. Ziel "Zielsymbolname" ist außerhalb des gültigen Bereichs, Thunk wird eingefügt.

Der Linker eingefügt einen Thunk in einer Situation, in dem der Offset oder der Adresse konnte nicht in die angegebene Anweisung nicht finden, da das Zielsymbol zu weit entfernt von Zielsymbol und vorhanden ist.

Möglicherweise möchten Sie die Anwendung neu anordnen (mithilfe der [/ORDER](../../build/reference/order-put-functions-in-order.md) -Option verwenden, z. B.), das zusätzliche Maß an Dereferenzierung zu vermeiden.