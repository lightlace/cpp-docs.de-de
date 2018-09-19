---
title: Linkertoolfehler Lnk1245 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef7bace5cec937399d7a2ed440e21b9b751f4141
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46041791"
---
# <a name="linker-tools-error-lnk1245"></a>Linkertoolfehler LNK1245

Es wurde ein ungültiges Subsystem "Subsystem" angegeben. / SUBSYSTEM muss WINDOWSCE oder CONSOLE WINDOWS sein.

["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) wurde verwendet, um das Objekt zu kompilieren und eine der folgenden Bedingungen gilt:

- Ein benutzerdefinierter Einstiegspunkt definiert wurde ([/Entry](../../build/reference/entry-entry-point-symbol.md)), sodass der Linker ein Subsystem keinen Entitätsschlüssel ableiten konnte.

- Ein Wert wurde übergeben, um die [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) -Linkeroption, die nicht für CLR-Objekte gültig ist.

Die Lösung werden in beiden Fällen geben Sie einen gültigen Wert für die/Subsystem (Linkeroption).