---
title: 'Ressourcencompiler: Fehler RC2151'
ms.date: 11/04/2016
f1_keywords:
- RC2151
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
ms.openlocfilehash: 8eaa50bc6080e37a4a74585eb03cbe4e40893bce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173443"
---
# <a name="resource-compiler-error-rc2151"></a>Ressourcencompiler: Fehler RC2151

Zeichenfolgenkonstanten können nicht erneut verwendet werden.

Sie verwenden den gleichen Wert, der zweimal in einem **STRINGTABLE** Anweisung. Stellen Sie sicher, dass Sie keine überlappenden dezimale und hexadezimale Werten.

Jede ID in einem **STRINGTABLE** muss eindeutig sein. Für maximale Effizienz bei Verwendung zusammenhängenden Konstanten, die auf ein Vielfaches von 16 zu starten.