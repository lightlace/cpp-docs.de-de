---
title: Compilerfehler C2220
ms.date: 11/04/2016
f1_keywords:
- C2220
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
ms.openlocfilehash: 3ff730c6fea7d2c57c4ec3054fc627cdc6227e2d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311747"
---
# <a name="compiler-error-c2220"></a>Compilerfehler C2220

Warnung als Fehler behandelt - keine Objektdatei generiert

[/ WX](../../build/reference/compiler-option-warning-level.md) weist den Compiler alle Warnungen als Fehler behandelt. Da ein Fehler aufgetreten ist, wurde kein Objekt und keine ausführbare Datei generiert.

Dieser Fehler wird nur angezeigt, wenn die **/WX** -Flag festgelegt ist und eine Warnung ausgegeben wird, während der Kompilierung. Um diesen Fehler zu beheben, müssen Sie jede Warnung im Projekt ausschließen.

### <a name="to-fix-use-one-of-the-following-techniques"></a>So beheben Sie den Fehler mit einer der folgenden Methoden

- Korrigieren Sie die Probleme, die Warnungen im Projekt verursachen.

- Auf einer niedrigeren Warnungsebene kompilieren, verwenden Sie z. B. **/w3** anstelle von **/W4**.

- Verwenden einer [Warnung](../../preprocessor/warning.md) Pragma deaktivieren oder eine bestimmte Warnung zu unterdrücken.

- Verwenden Sie keine **/WX** kompiliert.