---
title: Linkertoolwarnung LNK4204
ms.date: 11/04/2016
f1_keywords:
- LNK4204
helpviewer_keywords:
- LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
ms.openlocfilehash: 790b0fa25bbf41c38b843e1a2ea757fdc0d10b9a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475164"
---
# <a name="linker-tools-warning-lnk4204"></a>Linkertoolwarnung LNK4204

'Dateiname' fehlen Debuginformationen für das Verweismodul; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären

Die PDB-Datei hat eine falsche Signatur. Der Linker wird fortgesetzt, um das Objekt ohne Debuginformationen zu verknüpfen. Möglicherweise möchten Sie das Objekt mit recompile der ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md) Option.

LNK4204 kann auftreten, wenn einige der Objekte in der Bibliothek in eine Datei verweisen, die nicht mehr vorhanden ist. Dies kann vorkommen, wenn die Projektmappe neu erstellen z. B.; eine Objektdatei möglicherweise gelöscht und nicht aufgrund eines Fehlers Kompilierung neu erstellt werden. Kompilieren Sie in diesem Fall mit **"/ Z7"**, oder **/FD**, um die Objekte, die auf eine einzelne Datei pro-Bibliothek zu verweisen (das nicht den Standardnamen der PDB-Datei) zu aktualisieren.  Weitere Informationen finden Sie unter [/Fd (Programmdatenbank-Dateiname)](../../build/reference/fd-program-database-file-name.md).  Stellen Sie sicher, dass die PDB-Datei mit der Bibliothek gespeichert wird, jedes Mal, wenn sie in das Quellcodeverwaltungssystem aktualisiert wird.