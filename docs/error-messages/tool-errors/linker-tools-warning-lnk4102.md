---
title: Linkertoolwarnung LNK4102 | Microsoft-Dokumentation
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
ms.openlocfilehash: 9daaffc4ddfa9a869c2e60e2c05dc2b7e296d94b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46031853"
---
# <a name="linker-tools-warning-lnk4102"></a>Linkertoolwarnung LNK4102

Export des Löschdestruktors 'Name'; Image kann möglicherweise nicht ordnungsgemäß ausgeführt.

Die Anwendung hat versucht, so exportieren Sie einen Destruktor wird gelöscht. Das resultierende löschen kann über eine DLL-Grenze hinweg auftreten, so, dass ein Prozess Arbeitsspeicher freigeben kann, die er nicht besitzt. Stellen Sie sicher, dass das angegebene Symbol in der DEF-Datei nicht aufgeführt ist und das Symbol nicht aufgeführt ist, als Argument der **/IMPORT** oder **/EXPORT** -Option in der Befehlszeile des Linkers.

Wenn Sie die C-Laufzeitbibliothek neu sind, können Sie diese Meldung ignorieren.