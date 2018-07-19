---
title: Linkertoolfehler Lnk2013 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2013
dev_langs:
- C++
helpviewer_keywords:
- LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9320b9ead0276b6fb5e1b9773260049a01520e12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299850"
---
# <a name="linker-tools-error-lnk2013"></a>Linkertoolfehler LNK2013
Fixup-Typ Fixup-Überlauf. Ziel 'Symbolname' ist außerhalb des Bereichs  
  
 Der Linker kann die erforderliche Adresse bzw. den Offset in die angegebene Anweisung nicht finden, da die Entfernung zwischen Zielsymbol und Anweisung zu groß ist.  
  
 Sie können dieses Problem lösen, indem mehrere Abbilder erstellen oder indem die [/ORDER](../../build/reference/order-put-functions-in-order.md) option, damit der Anweisung und Ziel näher beieinander.  
  
 Wenn der Symbolname ein benutzerdefiniertes (und kein vom Compiler generiertes) Symbol ist, können Sie auch versuchen, den Fehler mithilfe der folgenden Maßnahmen zu beheben:  
  
-   Ändern Sie die statische Funktion in eine nicht statische Funktion.  
  
-   Benennen Sie den Codeabschnitt mit der statischen Funktion um, sodass er dem Namen des Aufrufers entspricht.  
  
 Überprüfen Sie mit `DUMPBIN /SYMBOLS`, ob eine Funktion statisch ist.