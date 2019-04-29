---
title: Aktualisieren Sie eine Spalte aus, wenn eine andere Tabelle einen Verweis auf die Zeile enthält.
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 46de5f54a3ec6525f779a6b55a700429a2a84fef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389072"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Aktualisieren einer Spalte, wenn eine andere Tabelle einen Verweis auf die Zeile enthält

Einige Anbieter können erkennen, welche Spalten in der Zeile geändert, aber viele Anbieter können nicht aus. Daher kann Aktualisieren einer Spalte zu einem Fehler führen, wenn es ist ein Verweis auf die Zeile, die Sie aktualisieren möchten. Um dieses Problem zu beheben, erstellen Sie einen separaten Accessor enthält nur die Spalten, die Sie ändern möchten. Übergeben Sie die Anzahl der diesem Accessor `SetData`.

## <a name="see-also"></a>Siehe auch

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)