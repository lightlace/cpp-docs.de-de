---
title: Linkertoolfehler Lnk2008 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2008
dev_langs:
- C++
helpviewer_keywords:
- LNK2008
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 18eda06e7f133ada4de1b7ec28ac21be205a71f7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086810"
---
# <a name="linker-tools-error-lnk2008"></a>Linkertoolfehler LNK2008

Das fixupziel ist nicht als 'Symbolname' ausgerichtete

LINK hat ein Fixup-Ziel in der Objektdatei, die nicht ordnungsgemäß ausgerichtet wurde gefunden.

Dieser Fehler kann verursacht werden, von der benutzerdefinierten Abschnitt Ausrichtung (z. B. #pragma [Pack](../../preprocessor/pack.md)), [ausrichten](../../cpp/align-cpp.md) Modifizierer oder mithilfe der Assemblysprache-Code, Abschnitt Ausrichtung ändert.

Wenn Ihr Code keine der oben genannten verwendet, kann dies durch den Compiler verursacht werden.