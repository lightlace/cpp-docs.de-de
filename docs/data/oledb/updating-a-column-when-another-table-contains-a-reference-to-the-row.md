---
title: Aktualisieren Sie eine Spalte aus, wenn eine andere Tabelle einen Verweis auf die Zeile enthält.
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 46de5f54a3ec6525f779a6b55a700429a2a84fef
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039214"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Aktualisieren einer Spalte, wenn eine andere Tabelle einen Verweis auf die Zeile enthält

Einige Anbieter können erkennen, welche Spalten in der Zeile geändert, aber viele Anbieter können nicht aus. Daher kann Aktualisieren einer Spalte zu einem Fehler führen, wenn es ist ein Verweis auf die Zeile, die Sie aktualisieren möchten. Um dieses Problem zu beheben, erstellen Sie einen separaten Accessor enthält nur die Spalten, die Sie ändern möchten. Übergeben Sie die Anzahl der diesem Accessor `SetData`.

## <a name="see-also"></a>Siehe auch

[Verwenden von Accessoren](../../data/oledb/using-accessors.md)