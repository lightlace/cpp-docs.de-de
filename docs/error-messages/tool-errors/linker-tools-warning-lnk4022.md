---
title: Linkertoolwarnung LNK4022 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4022
dev_langs:
- C++
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 644e7a9ba26dab15e2bfa2a269f62c04f0510180
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040998"
---
# <a name="linker-tools-warning-lnk4022"></a>Linkertoolwarnung LNK4022

eindeutige Übereinstimmung für Symbol 'Symbol' wurde nicht gefunden.

LINK oder LIB finden Sie mehrere übereinstimmt, für das angegebene Symbol für nicht ergänzte, und es konnte nicht die Mehrdeutigkeit aufzulösen. Keine Ausgabedatei (.exe, .dll, exp oder .lib) wird erstellt. Diese Warnung folgt eine Warnung [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) duplizieren Sie für jedes Symbol, und schließlich folgt Schwerwiegender Fehler [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).

Um diese Warnung zu vermeiden, geben Sie das Symbol in seiner ergänzten Form. Führen Sie [DUMPBIN](../../build/reference/dumpbin-options.md) für das Objekt anzeigen von ergänzten Namen.