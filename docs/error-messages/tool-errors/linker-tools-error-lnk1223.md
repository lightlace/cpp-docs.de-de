---
title: Linkertoolfehler LNK1223
ms.date: 11/04/2016
f1_keywords:
- LNK1223
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
ms.openlocfilehash: 331521c357389c2f7c1aa786969154a2b747ffe5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242824"
---
# <a name="linker-tools-error-lnk1223"></a>Linkertoolfehler LNK1223

Ungültige oder beschädigte Datei: Datei enthält unzulässige .pdata-Beiträge

Bei RISC-Plattformen, die Pdata verwenden, wird dieser Fehler auftreten, wenn der Compiler einen .pdata-Abschnitt mit unsortierten Einträgen ausgegeben hat.

Um dieses Problem zu beheben, versuchen Sie es ohne Kompilieren [/GL (Whole Program Optimization)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) aktiviert. Leere Funktionsbodys können in einigen Fällen diesen Fehler auch verursacht.