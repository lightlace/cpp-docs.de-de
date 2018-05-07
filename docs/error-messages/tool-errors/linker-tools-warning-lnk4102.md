---
title: Linkertoolwarnung Lnk4102 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4102
dev_langs:
- C++
helpviewer_keywords:
- LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16d13dcbc6d15efd7cf3a7ea0a310de4ab7b0c93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4102"></a>Linkertoolwarnung LNK4102
Exportieren des Löschens Destruktor 'Name'; Abbild kann möglicherweise nicht ordnungsgemäß ausgeführt.  
  
 Das Programm hat versucht, einen Destruktor löschen zu exportieren. Der resultierende Löschvorgang kann über eine DLL-Grenze hinweg auftreten, so, dass ein Prozess Arbeitsspeicher freigeben kann, deren Besitzer er nicht ist. Stellen Sie sicher, dass das angegebene Symbol in der DEF-Datei nicht aufgeführt ist, und das Symbol als ein Argument nicht aufgeführt ist die **/importieren** oder **/EXPORT** -Option in der Linker-Befehlszeile.  
  
 Wenn Sie die C-Laufzeitbibliothek neu sind, können Sie diese Meldung ignorieren.