---
title: Compilerwarnung (Stufe 1) C4729
ms.date: 11/04/2016
f1_keywords:
- C4729
helpviewer_keywords:
- C4729
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
ms.openlocfilehash: f5f93cadd97eefe0d6c6da97be99ec5fd82ece24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386394"
---
# <a name="compiler-warning-level-1-c4729"></a>Compilerwarnung (Stufe 1) C4729

Die Funktion ist zu groß für auf Verlaufdiagrammen basierende Warnungen.

Diese Warnung wird ausgegeben, wenn eine Funktion zu groß ist, um sie während der Kompilierung zuverlässig auf Situationen zu überprüfen, in denen eine Warnung auftreten könnte. Diese Warnung wird nur bei Verwendung der [/Od](../../build/reference/od-disable-debug.md) -Compileroption generiert.

Unterteilen Sie die Funktion in kleinere Funktionen, um diese Warnung zu vermeiden.