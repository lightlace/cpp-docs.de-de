---
title: Linkertoolfehler LNK1120
description: Beschreibt den Linkertoolfehler LNK1120 Linker-Fehler, der die Anzahl der nicht aufgelösten externen symbolfehler im Link meldet.
ms.date: 10/31/2019
f1_keywords:
- LNK1120
helpviewer_keywords:
- LNK1120
ms.assetid: 56aa7d36-921f-4daf-b44d-cca0d4fb1b51
ms.openlocfilehash: 21a1ede07a69cdc065dd897715e243115529600d
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626583"
---
# <a name="linker-tools-error-lnk1120"></a>Linkertoolfehler LNK1120

> *Anzahl* nicht aufgelöster externe

Fehler Linkertoolfehler LNK1120 meldet die Anzahl der nicht aufgelösten [externen Symbol](linker-tools-error-lnk2001.md#what-is-an-unresolved-external-symbol) Fehler im aktuellen Link.

Jedes nicht aufgelöste externe Symbol wird zuerst von einem [LNK2001](linker-tools-error-lnk2001.md) -oder [LNK2019](linker-tools-error-lnk2019.md) -Fehler gemeldet. Die Linkertoolfehler LNK1120-Nachricht wird zuletzt angezeigt und zeigt die Fehler Anzahl nicht aufgelöster Symbole an.

> [!IMPORTANT]
> **Dieser Fehler muss nicht behoben werden.** Dieser Fehler wird behoben, wenn Sie alle LNK2001-und LNK2019 Linker-Fehler vor der Ausgabe in der Buildausgabe korrigieren. Beheben Sie Probleme immer, beginnend beim ersten gemeldeten Fehler. Spätere Fehler werden möglicherweise durch frühere Fehler verursacht und gehen entfernt, wenn die vorherigen Fehler korrigiert wurden.
