---
title: Linkertoolwarnung Lnk4102 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4102
dev_langs: C++
helpviewer_keywords: LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 80efad60da9f6742110811a5cf4c12f07c7def67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4102"></a>Linkertoolwarnung LNK4102
Exportieren des Löschens Destruktor 'Name'; Abbild kann möglicherweise nicht ordnungsgemäß ausgeführt.  
  
 Das Programm hat versucht, einen Destruktor löschen zu exportieren. Der resultierende Löschvorgang kann über eine DLL-Grenze hinweg auftreten, so, dass ein Prozess Arbeitsspeicher freigeben kann, deren Besitzer er nicht ist. Stellen Sie sicher, dass das angegebene Symbol in der DEF-Datei nicht aufgeführt ist, und das Symbol als ein Argument nicht aufgeführt ist die **/importieren** oder **/EXPORT** -Option in der Linker-Befehlszeile.  
  
 Wenn Sie die C-Laufzeitbibliothek neu sind, können Sie diese Meldung ignorieren.