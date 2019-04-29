---
title: Compilerfehler C3715
ms.date: 11/04/2016
f1_keywords:
- C3715
helpviewer_keywords:
- C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
ms.openlocfilehash: 94a451bbe936507ac3b33747065a9b6aac9edd02
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328327"
---
# <a name="compiler-error-c3715"></a>Compilerfehler C3715

"Zeiger": muss ein Zeiger auf "Klasse"

Angabe ein Zeigers in [__hook](../../cpp/hook.md) oder [__unhook](../../cpp/unhook.md) zeigen, die Sie nicht auf eine gültige Klasse. Um diesen Fehler zu beheben, stellen sicher, dass Ihre `__hook` und `__unhook` Aufrufe geben Zeiger zu den gültigen Klassen.