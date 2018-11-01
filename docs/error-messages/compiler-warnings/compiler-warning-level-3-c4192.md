---
title: Compilerwarnung (Stufe 3) C4192
ms.date: 11/04/2016
f1_keywords:
- C4192
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
ms.openlocfilehash: 56b27596296b87edcc6de406e7b6621d5723815d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519712"
---
# <a name="compiler-warning-level-3-c4192"></a>Compilerwarnung (Stufe 3) C4192

automatischer Ausschluss von 'Name' während des Importierens der Typbibliothek "Library"

Ein `#import` -Bibliothek enthält ein Element *Namen*, d. h. auch in den Headern der Win32-System definiert. Aufgrund der Einschränkungen von Typbibliotheken, die Namen z. B. **IUnknown** oder GUID häufig definiert sind in einer Typbibliothek, duplizieren die Definition aus den Systemheadern. `#import` Diese Elemente erkennt und weigern, diese in die TLH und TLI-Header-Dateien zu integrieren.

Um dieses Verhalten überschreiben, verwenden `#import` Attribute [No_auto_exclude](../../preprocessor/no-auto-exclude.md) und [include()](../../preprocessor/include-parens.md).