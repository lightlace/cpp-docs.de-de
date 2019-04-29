---
title: Linkertoolfehler LNK2008
ms.date: 11/04/2016
f1_keywords:
- LNK2008
helpviewer_keywords:
- LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
ms.openlocfilehash: 97bb2be18da5d166d1d5fba42e4ec8ce1f0439fe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386524"
---
# <a name="linker-tools-error-lnk2008"></a>Linkertoolfehler LNK2008

Das fixupziel ist nicht als 'Symbolname' ausgerichtete

LINK hat ein Fixup-Ziel in der Objektdatei, die nicht ordnungsgemäß ausgerichtet wurde gefunden.

Dieser Fehler kann verursacht werden, von der benutzerdefinierten Abschnitt Ausrichtung (z. B. #pragma [Pack](../../preprocessor/pack.md)), [ausrichten](../../cpp/align-cpp.md) Modifizierer oder mithilfe der Assemblysprache-Code, Abschnitt Ausrichtung ändert.

Wenn Ihr Code keine der oben genannten verwendet, kann dies durch den Compiler verursacht werden.