---
title: Linkertoolfehler LNK2013
ms.date: 11/04/2016
f1_keywords:
- LNK2013
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
ms.openlocfilehash: 4d932a89f1b0bde27f6de2f84b2ed103dab1b1b0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62299067"
---
# <a name="linker-tools-error-lnk2013"></a>Linkertoolfehler LNK2013

Fixup-Typ Fixup-Überlauf. Ziel 'Symbolname' ist außerhalb des Bereichs

Der Linker kann die erforderliche Adresse bzw. den Offset in die angegebene Anweisung nicht finden, da die Entfernung zwischen Zielsymbol und Anweisung zu groß ist.

Sie können dieses Problem zu beheben, durch die Erstellung mehrerer Abbilder oder mithilfe der [/ORDER](../../build/reference/order-put-functions-in-order.md) option aus, damit die Anweisung und das Ziel näher beieinander.

Wenn der Symbolname ein benutzerdefiniertes (und kein vom Compiler generiertes) Symbol ist, können Sie auch versuchen, den Fehler mithilfe der folgenden Maßnahmen zu beheben:

- Ändern Sie die statische Funktion in eine nicht statische Funktion.

- Benennen Sie den Codeabschnitt mit der statischen Funktion um, sodass er dem Namen des Aufrufers entspricht.

Überprüfen Sie mit `DUMPBIN /SYMBOLS`, ob eine Funktion statisch ist.