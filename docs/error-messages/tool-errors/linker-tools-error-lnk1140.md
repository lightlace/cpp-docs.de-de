---
title: Linkertoolfehler LNK1140
ms.date: 11/04/2016
f1_keywords:
- LNK1140
helpviewer_keywords:
- LNK1140
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
ms.openlocfilehash: 48c735f29918c4d1caeb15123f7376276d116fb4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255065"
---
# <a name="linker-tools-error-lnk1140"></a>Linkertoolfehler LNK1140

zu viele Module für die Programmdatenbank; Link mit/PDB: NONE

Das Projekt enthält mehr als 4096 Module.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)

1. Verknüpfen Sie erneut mit [/PDB: NONE](../../build/reference/pdb-use-program-database.md).

1. Kompilieren Sie einige Module ohne Debuginformationen.

1. Reduzieren Sie die Anzahl der Module an.