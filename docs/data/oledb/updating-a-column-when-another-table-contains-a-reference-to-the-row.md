---
title: Aktualisieren Sie eine Spalte aus, wenn eine andere Tabelle einen Verweis auf die Zeile enthält | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 17d260f522432a78729c9998c518398dfa41275a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102884"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Aktualisieren einer Spalte, wenn eine andere Tabelle einen Verweis auf die Zeile enthält
Einige Anbieter können erkennen, welche Spalten in der Zeile geändert, jedoch nicht von vielen Anbietern. Folglich kann Aktualisieren einer Spalte zu einem Fehler führen, wenn es ist ein Verweis auf die Zeile, die Sie aktualisieren möchten. Um dieses Problem zu beheben, erstellen Sie einen separaten Accessor, enthält nur die Spalten, die Sie ändern möchten. Übergeben Sie die Anzahl dieser Accessortyps `SetData`.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)