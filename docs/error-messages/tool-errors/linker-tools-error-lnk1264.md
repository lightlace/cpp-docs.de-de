---
title: Linkertoolfehler Lnk1264 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1264
dev_langs:
- C++
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8232e83774dc53755b77ad9c8b3bbb2a0bcc6ae6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46102741"
---
# <a name="linker-tools-error-lnk1264"></a>Linkertoolfehler LNK1264

/ LTCG: PGINSTRUMENT angegeben, aber keine codegenerierung ist erforderlich; Fehler bei der Instrumentation

**/ LTCG: PGINSTRUMENT** wurde angegeben, jedoch keine OBJ-Dateien gefunden, die mit kompiliert wurden ["/ GL"](../../build/reference/gl-whole-program-optimization.md). Instrumentation kann nicht stattfinden, und der Fehler bei Verknüpfung ausführen. Es muss mindestens eine OBJ-Datei in der Befehlszeile, die die Kompilierung mit **"/ GL"** , damit die Instrumentierung auftreten kann.

Profilgesteuerte Optimierung (PGO) ist nur in 64-Bit-Compilern verfügbar.