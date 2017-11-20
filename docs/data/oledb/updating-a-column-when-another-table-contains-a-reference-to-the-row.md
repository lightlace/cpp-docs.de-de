---
title: "Aktualisieren Sie eine Spalte aus, wenn eine andere Tabelle einen Verweis auf die Zeile enthält | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cac57f2f4a1175fa1d9f4009e10fd3d0fae2a3b0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Aktualisieren einer Spalte, wenn eine andere Tabelle einen Verweis auf die Zeile enthält
Einige Anbieter können erkennen, welche Spalten in der Zeile geändert, jedoch nicht von vielen Anbietern. Folglich kann Aktualisieren einer Spalte zu einem Fehler führen, wenn es ist ein Verweis auf die Zeile, die Sie aktualisieren möchten. Um dieses Problem zu beheben, erstellen Sie einen separaten Accessor, enthält nur die Spalten, die Sie ändern möchten. Übergeben Sie die Anzahl dieser Accessortyps `SetData`.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)