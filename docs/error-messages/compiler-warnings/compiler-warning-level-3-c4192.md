---
title: Compilerwarnung (Stufe 3) C4192 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4192
dev_langs:
- C++
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 671a8c83dcadcaa89372e53b6c3d677c5810b4a5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114409"
---
# <a name="compiler-warning-level-3-c4192"></a>Compilerwarnung (Stufe 3) C4192

automatischer Ausschluss von 'Name' während des Importierens der Typbibliothek "Library"

Ein `#import` -Bibliothek enthält ein Element *Namen*, d. h. auch in den Headern der Win32-System definiert. Aufgrund der Einschränkungen von Typbibliotheken, die Namen z. B. **IUnknown** oder GUID häufig definiert sind in einer Typbibliothek, duplizieren die Definition aus den Systemheadern. `#import` Diese Elemente erkennt und weigern, diese in die TLH und TLI-Header-Dateien zu integrieren.

Um dieses Verhalten überschreiben, verwenden `#import` Attribute [No_auto_exclude](../../preprocessor/no-auto-exclude.md) und [include()](../../preprocessor/include-parens.md).