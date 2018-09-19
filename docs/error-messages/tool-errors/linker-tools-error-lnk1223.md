---
title: Linkertoolfehler Lnk1223 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1223
dev_langs:
- C++
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8639919c74559829367108b36d62594e2a83a91a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067980"
---
# <a name="linker-tools-error-lnk1223"></a>Linkertoolfehler LNK1223

Ungültige oder beschädigte Datei: Datei enthält unzulässige .pdata-Beiträge

Bei RISC-Plattformen, die Pdata verwenden, wird dieser Fehler auftreten, wenn der Compiler einen .pdata-Abschnitt mit unsortierten Einträgen ausgegeben hat.

Um dieses Problem zu beheben, versuchen Sie es ohne Kompilieren [/GL (Whole Program Optimization)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) aktiviert. Leere Funktionsbodys können in einigen Fällen diesen Fehler auch verursacht.