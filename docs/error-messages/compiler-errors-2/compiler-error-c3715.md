---
title: Compilerfehler C3715
ms.date: 11/04/2016
f1_keywords:
- C3715
helpviewer_keywords:
- C3715
ms.assetid: ee5dce88-ddc4-4bdb-9464-47467ce1674f
ms.openlocfilehash: 94a451bbe936507ac3b33747065a9b6aac9edd02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660615"
---
# <a name="compiler-error-c3715"></a>Compilerfehler C3715

"Zeiger": muss ein Zeiger auf "Klasse"

Angabe ein Zeigers in [__hook](../../cpp/hook.md) oder [__unhook](../../cpp/unhook.md) zeigen, die Sie nicht auf eine gültige Klasse. Um diesen Fehler zu beheben, stellen sicher, dass Ihre `__hook` und `__unhook` Aufrufe geben Zeiger zu den gültigen Klassen.