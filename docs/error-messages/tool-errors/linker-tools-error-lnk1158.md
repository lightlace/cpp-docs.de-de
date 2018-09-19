---
title: Linkertoolfehler Lnk1158 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1158
dev_langs:
- C++
helpviewer_keywords:
- LNK1158
ms.assetid: 45febf16-d9e1-42db-af91-532e2717fd6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ce319aa4529c74cad00342b09aa0ed98bb49ce7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094168"
---
# <a name="linker-tools-error-lnk1158"></a>Linkertoolfehler LNK1158

'Dateiname' kann nicht ausgeführt werden.

Die angegebene ausführbare Datei, die aufgerufen werden, indem [LINK](../../build/reference/linker-command-line-syntax.md) ist nicht in das Verzeichnis mit LINK noch in einem in der PATH-Umgebungsvariablen angegebenen Verzeichnis.

Beispielsweise erhalten Sie diesen Fehler, wenn Sie versuchen, den PGOPTIMIZE-Parameter, um die ["/ LTCG"](../../build/reference/ltcg-link-time-code-generation.md) Linkeroption auf einem Computer mit einem 32-Bit-Betriebssystem.