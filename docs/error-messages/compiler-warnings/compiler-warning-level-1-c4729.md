---
title: Compilerwarnung (Stufe 1) C4729 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4729
dev_langs:
- C++
helpviewer_keywords:
- C4729
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d1f5b4fe452937ce74e56886a5214ff92f44af7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096079"
---
# <a name="compiler-warning-level-1-c4729"></a>Compilerwarnung (Stufe 1) C4729

Die Funktion ist zu groß für auf Verlaufdiagrammen basierende Warnungen.

Diese Warnung wird ausgegeben, wenn eine Funktion zu groß ist, um sie während der Kompilierung zuverlässig auf Situationen zu überprüfen, in denen eine Warnung auftreten könnte. Diese Warnung wird nur bei Verwendung der [/Od](../../build/reference/od-disable-debug.md) -Compileroption generiert.

Unterteilen Sie die Funktion in kleinere Funktionen, um diese Warnung zu vermeiden.