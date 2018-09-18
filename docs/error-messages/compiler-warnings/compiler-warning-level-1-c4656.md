---
title: Compilerwarnung (Stufe 1) C4656 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4656
dev_langs:
- C++
helpviewer_keywords:
- C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3334b9448dd6e9d47ed0b3ee3e4dfb9dfc57b57f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032409"
---
# <a name="compiler-warning-level-1-c4656"></a>Compilerwarnung (Stufe 1) C4656

'Symbol': Datentyp ist neu oder seit dem letzten Build geändert wurde oder wird an anderer Stelle unterschiedlich definiert

Sie haben einen Datentyp hinzugefügt oder geändert, der seit dem letzten erfolgreichen Build neu zum Quellcode hinzugekommen ist. „Bearbeiten und fortfahren“ unterstützt keine Änderungen an vorhandenen Datentypen.

Auf diese Warnung folgt immer [Schwerwiegender Fehler C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Weitere Informationen hierzu finden Sie unter [Unterstützte Codeänderungen](/visualstudio/debugger/supported-code-changes-cpp).

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>So entfernen Sie diese Warnung, ohne die aktuelle Debugsitzung zu beenden

1. Ändern Sie den Datentyp wieder in den Zustand, den er vor dem Fehler hatte.

1. Wählen Sie im Menü **Debuggen** den Befehl **Codeänderungen übernehmen**aus.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>So entfernen Sie diesen Fehler, ohne den Quellcode zu ändern

1. Wählen Sie im Menü **Debuggen** die Option **Debuggen beenden**.

1. Wählen Sie im Menü **Erstellen** den Befehl **Erstellen**aus.