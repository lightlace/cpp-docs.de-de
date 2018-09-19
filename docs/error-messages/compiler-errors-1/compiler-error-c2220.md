---
title: Compilerfehler C2220 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2220
dev_langs:
- C++
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f4179b396e732ceeea20aeb9428d841a357a6d1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051320"
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