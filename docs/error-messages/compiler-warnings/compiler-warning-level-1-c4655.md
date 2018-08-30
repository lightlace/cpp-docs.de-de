---
title: Compilerwarnung (Stufe 1) C4655 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4655
dev_langs:
- C++
helpviewer_keywords:
- C4655
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9600c0fb9b4f03112ebd9cf430e3f833899c5f3c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209100"
---
# <a name="compiler-warning-level-1-c4655"></a>Compilerwarnung (Stufe 1) C4655

> "*Symbol*': Variablentyp ist neuer als beim letzten Build oder wurde an anderer Stelle unterschiedlich definiert

## <a name="remarks"></a>Hinweise

Seit dem letzten erfolgreichen Build wurde ein Datentyp geändert oder hinzugefügt. „Bearbeiten und fortfahren“ unterstützt keine Änderungen an vorhandenen Datentypen.

Auf diese Warnung folgt ein [Schwerwiegender Fehler C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Weitere Informationen hierzu finden Sie unter [Unterstützte Codeänderungen](/visualstudio/debugger/supported-code-changes-cpp).

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>So entfernen Sie diese Warnung, ohne die aktuelle Debugsitzung zu beenden

1. Ändern Sie den Datentyp wieder in den Zustand, den er vor dem Fehler hatte.

2. Wählen Sie im Menü **Debuggen** den Befehl **Codeänderungen übernehmen**.

### <a name="to-remove-this-warning-without-changing-your-source-code"></a>So entfernen Sie diese Warnung, ohne den Quellcode zu ändern

1. Wählen Sie im Menü **Debuggen** die Option **Debuggen beenden**.

2. Wählen Sie im Menü **Erstellen** den Befehl **Erstellen**aus.