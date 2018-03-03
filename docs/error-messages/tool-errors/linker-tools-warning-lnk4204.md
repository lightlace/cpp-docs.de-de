---
title: Linkertoolwarnung Lnk4204 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4204
dev_langs:
- C++
helpviewer_keywords:
- LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f9b2d9611192fe4afe01d178ac3af5fcc8ccc42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4204"></a>Linkertoolwarnung LNK4204
'Dateiname' fehlen Debuginformationen für das Verweismodul; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären  
  
 Die PDB-Datei hat eine falsche Signatur. Der Linker wird fortgesetzt, um das Objekt ohne Debuginformationen zu verknüpfen. Sie sollten so kompilieren Sie das Objekt mit dem [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) Option.  
  
 LNK4204 kann auftreten, wenn einige der Objekte in der Bibliothek in eine Datei zu verweisen, die nicht mehr vorhanden ist. Dies kann vorkommen, wenn die Projektmappe neu erstellen z. B.; eine Objektdatei möglicherweise gelöscht und nicht aufgrund eines Fehlers bei Kompilierung neu erstellt werden. Kompilieren Sie in diesem Fall mit **"/ Z7"**, oder **/FD**, um die Objekte zum Verweisen auf eine einzelne Datei pro-Bibliothek (die nicht den Standardnamen für die PDB-Datei ist) zu aktualisieren.  Weitere Informationen finden Sie unter [/Fd (Programmdatenbank-Dateiname)](../../build/reference/fd-program-database-file-name.md).  Stellen Sie sicher, dass die PDB-Datei mit der Bibliothek gespeichert ist, jedes Mal, wenn sie in das Quellcodeverwaltungssystem aktualisiert wird.