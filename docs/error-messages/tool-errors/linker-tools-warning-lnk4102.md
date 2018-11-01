---
title: Linkertoolwarnung LNK4102
ms.date: 11/04/2016
f1_keywords:
- LNK4102
helpviewer_keywords:
- LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
ms.openlocfilehash: 0f9c8649988dd3056e98730ac4b02022a8c9dd51
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643091"
---
# <a name="linker-tools-warning-lnk4102"></a>Linkertoolwarnung LNK4102

Export des Löschdestruktors 'Name'; Image kann möglicherweise nicht ordnungsgemäß ausgeführt.

Die Anwendung hat versucht, so exportieren Sie einen Destruktor wird gelöscht. Das resultierende löschen kann über eine DLL-Grenze hinweg auftreten, so, dass ein Prozess Arbeitsspeicher freigeben kann, die er nicht besitzt. Stellen Sie sicher, dass das angegebene Symbol in der DEF-Datei nicht aufgeführt ist und das Symbol nicht aufgeführt ist, als Argument der **/IMPORT** oder **/EXPORT** -Option in der Befehlszeile des Linkers.

Wenn Sie die C-Laufzeitbibliothek neu sind, können Sie diese Meldung ignorieren.