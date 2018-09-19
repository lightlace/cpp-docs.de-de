---
title: Compilerwarnung (Stufe 1) C4657 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4657
dev_langs:
- C++
helpviewer_keywords:
- C4657
ms.assetid: eb750050-cea6-4ead-b80c-d5dcd4971cfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0eb3701496b2300aa52f4734cb2d1ea6e236ad0a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098828"
---
# <a name="compiler-warning-level-1-c4657"></a>Compilerwarnung (Stufe 1) C4657

Der Ausdruck bezieht einen Datentyp ein, der seit dem letzten Build neu hinzugekommen ist.

Sie haben einen Datentyp hinzugefügt oder geändert, der seit dem letzten erfolgreichen Build neu zum Quellcode hinzugekommen ist. „Bearbeiten und fortfahren“ unterstützt keine Änderungen an vorhandenen Datentypen.

Auf diese Warnung folgt immer [Schwerwiegender Fehler C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Weitere Informationen hierzu finden Sie unter [Unterstützte Codeänderungen](/visualstudio/debugger/supported-code-changes-cpp).

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>So entfernen Sie diese Warnung, ohne die aktuelle Debugsitzung zu beenden

1. Ändern Sie den Datentyp wieder in den Zustand, den er vor dem Fehler hatte.

1. Wählen Sie im Menü **Debuggen** den Befehl **Codeänderungen übernehmen**aus.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>So entfernen Sie diesen Fehler, ohne den Quellcode zu ändern

1. Wählen Sie im Menü **Debuggen** die Option **Debuggen beenden**.

1. Wählen Sie im Menü **Erstellen** den Befehl **Erstellen**aus.