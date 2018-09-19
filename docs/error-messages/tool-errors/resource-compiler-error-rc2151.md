---
title: 'Ressourcencompiler: Fehler RC2151 | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2151
dev_langs:
- C++
helpviewer_keywords:
- RC2151
ms.assetid: 3c47e535-c78d-4338-aab9-9b47e2c34728
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a15f3f1237df9e4b706a2c2048dddd6d5db395d5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109781"
---
# <a name="resource-compiler-error-rc2151"></a>Ressourcencompiler: Fehler RC2151

Zeichenfolgenkonstanten können nicht erneut verwendet werden.

Sie verwenden den gleichen Wert, der zweimal in einem **STRINGTABLE** Anweisung. Stellen Sie sicher, dass Sie keine überlappenden dezimale und hexadezimale Werten.

Jede ID in einem **STRINGTABLE** muss eindeutig sein. Für maximale Effizienz bei Verwendung zusammenhängenden Konstanten, die auf ein Vielfaches von 16 zu starten.