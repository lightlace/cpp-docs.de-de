---
title: Linkertoolfehler Lnk1140 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1140
dev_langs:
- C++
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9f850360bc749a41e548cebae9f58f9fc7d3d420
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044703"
---
# <a name="linker-tools-error-lnk1140"></a>Linkertoolfehler LNK1140

zu viele Module für die Programmdatenbank; Link mit/PDB: NONE

Das Projekt enthält mehr als 4096 Module.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Verknüpfen Sie erneut mit [/PDB: NONE](../../build/reference/pdb-use-program-database.md).

1. Kompilieren Sie einige Module ohne Debuginformationen.

1. Reduzieren Sie die Anzahl der Module an.