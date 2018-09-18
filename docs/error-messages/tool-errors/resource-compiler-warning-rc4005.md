---
title: 'Ressourcencompiler: Warnung RC4005 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC4005
dev_langs:
- C++
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 589fd008b3927887a8144b2fc63d2cbbde2af913
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028518"
---
# <a name="resource-compiler-warning-rc4005"></a>Ressourcencompiler: Warnung RC4005

'Bezeichner': Makro-Neudefinition

Der Bezeichner wurde zweimal definiert. Der Compiler verwendet die zweite Makrodefinition.

Diese Warnung kann verursacht werden, definieren Sie ein Makro aus, in der Befehlszeile und in den Code mit einem `#define` Richtlinie. Es kann auch von Makros, die aus der Include-Dateien importiert verursacht werden.

Um die Warnung zu vermeiden, entfernen Sie eine der Definitionen oder verwenden eine `#undef` Direktive, bevor Sie die zweite Definition.