---
title: 'Ressourcencompiler: Warnung RC4005'
ms.date: 11/04/2016
f1_keywords:
- RC4005
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
ms.openlocfilehash: 571c4ac285e9477b017dbc21cf9ff733539759d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613602"
---
# <a name="resource-compiler-warning-rc4005"></a>Ressourcencompiler: Warnung RC4005

'Bezeichner': Makro-Neudefinition

Der Bezeichner wurde zweimal definiert. Der Compiler verwendet die zweite Makrodefinition.

Diese Warnung kann verursacht werden, definieren Sie ein Makro aus, in der Befehlszeile und in den Code mit einem `#define` Richtlinie. Es kann auch von Makros, die aus der Include-Dateien importiert verursacht werden.

Um die Warnung zu vermeiden, entfernen Sie eine der Definitionen oder verwenden eine `#undef` Direktive, bevor Sie die zweite Definition.