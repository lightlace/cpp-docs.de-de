---
title: Linkertoolwarnung LNK4204 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4204
dev_langs:
- C++
helpviewer_keywords:
- LNK4204
ms.assetid: 14adda20-0cbe-407b-90f6-9f81c93530e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee6164f20bbf91a8cb0b88d8a1333107f239d3f2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136232"
---
# <a name="linker-tools-warning-lnk4204"></a>Linkertoolwarnung LNK4204

'Dateiname' fehlen Debuginformationen für das Verweismodul; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären

Die PDB-Datei hat eine falsche Signatur. Der Linker wird fortgesetzt, um das Objekt ohne Debuginformationen zu verknüpfen. Möglicherweise möchten Sie das Objekt mit recompile der ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md) Option.

LNK4204 kann auftreten, wenn einige der Objekte in der Bibliothek in eine Datei verweisen, die nicht mehr vorhanden ist. Dies kann vorkommen, wenn die Projektmappe neu erstellen z. B.; eine Objektdatei möglicherweise gelöscht und nicht aufgrund eines Fehlers Kompilierung neu erstellt werden. Kompilieren Sie in diesem Fall mit **"/ Z7"**, oder **/FD**, um die Objekte, die auf eine einzelne Datei pro-Bibliothek zu verweisen (das nicht den Standardnamen der PDB-Datei) zu aktualisieren.  Weitere Informationen finden Sie unter [/Fd (Programmdatenbank-Dateiname)](../../build/reference/fd-program-database-file-name.md).  Stellen Sie sicher, dass die PDB-Datei mit der Bibliothek gespeichert wird, jedes Mal, wenn sie in das Quellcodeverwaltungssystem aktualisiert wird.