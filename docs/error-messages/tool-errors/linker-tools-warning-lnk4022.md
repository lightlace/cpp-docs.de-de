---
title: Linkertoolwarnung LNK4022
ms.date: 11/04/2016
f1_keywords:
- LNK4022
helpviewer_keywords:
- LNK4022
ms.assetid: 890f487e-db98-45dd-a226-c7ccead82b1e
ms.openlocfilehash: 1c9ccfe6ca201ae4deed69c7d01429c67cce4bda
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552476"
---
# <a name="linker-tools-warning-lnk4022"></a>Linkertoolwarnung LNK4022

eindeutige Übereinstimmung für Symbol 'Symbol' wurde nicht gefunden.

LINK oder LIB finden Sie mehrere übereinstimmt, für das angegebene Symbol für nicht ergänzte, und es konnte nicht die Mehrdeutigkeit aufzulösen. Keine Ausgabedatei (.exe, .dll, exp oder .lib) wird erstellt. Diese Warnung folgt eine Warnung [LNK4002](../../error-messages/tool-errors/linker-tools-warning-lnk4002.md) duplizieren Sie für jedes Symbol, und schließlich folgt Schwerwiegender Fehler [LNK1152](../../error-messages/tool-errors/linker-tools-error-lnk1152.md).

Um diese Warnung zu vermeiden, geben Sie das Symbol in seiner ergänzten Form. Führen Sie [DUMPBIN](../../build/reference/dumpbin-options.md) für das Objekt anzeigen von ergänzten Namen.