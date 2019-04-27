---
title: Linkertoolfehler LNK1264
ms.date: 11/04/2016
f1_keywords:
- LNK1264
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
ms.openlocfilehash: ca17b6946b9e988507af2786825223e042356d0e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160587"
---
# <a name="linker-tools-error-lnk1264"></a>Linkertoolfehler LNK1264

/ LTCG: PGINSTRUMENT angegeben, aber keine codegenerierung ist erforderlich; Fehler bei der Instrumentation

**/ LTCG: PGINSTRUMENT** wurde angegeben, jedoch keine OBJ-Dateien gefunden, die mit kompiliert wurden ["/ GL"](../../build/reference/gl-whole-program-optimization.md). Instrumentation kann nicht stattfinden, und der Fehler bei Verknüpfung ausführen. Es muss mindestens eine OBJ-Datei in der Befehlszeile, die die Kompilierung mit **"/ GL"** , damit die Instrumentierung auftreten kann.

Profilgesteuerte Optimierung (PGO) ist nur in 64-Bit-Compilern verfügbar.