---
title: Linkertoolfehler LNK1245
ms.date: 11/04/2016
f1_keywords:
- LNK1245
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
ms.openlocfilehash: 4cf9a6c4356872b727a10a360396e51e38928b29
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160561"
---
# <a name="linker-tools-error-lnk1245"></a>Linkertoolfehler LNK1245

Es wurde ein ungültiges Subsystem "Subsystem" angegeben. / SUBSYSTEM muss WINDOWSCE oder CONSOLE WINDOWS sein.

["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) wurde verwendet, um das Objekt zu kompilieren und eine der folgenden Bedingungen gilt:

- Ein benutzerdefinierter Einstiegspunkt definiert wurde ([/Entry](../../build/reference/entry-entry-point-symbol.md)), sodass der Linker ein Subsystem keinen Entitätsschlüssel ableiten konnte.

- Ein Wert wurde übergeben, um die [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) -Linkeroption, die nicht für CLR-Objekte gültig ist.

Die Lösung werden in beiden Fällen geben Sie einen gültigen Wert für die/Subsystem (Linkeroption).