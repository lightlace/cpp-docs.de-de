---
title: Compilerwarnung (Stufe 3) C4622 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4622
dev_langs:
- C++
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d91e3c914d6c3feeb9d2326c94efe2bc54ac98f4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46023240"
---
# <a name="compiler-warning-level-3-c4622"></a>Compilerwarnung (Stufe 3) C4622

Überschreiben der Debuginformationen, die beim Erstellen des vorkompilierten Headers in der Objektdatei angelegt wurden: „file“

Die Codeansichtsinformationen in der angegebenen Datei sind bei der Kompilierung mit der [/Yu](../../build/reference/yu-use-precompiled-header-file.md) -Option (Vorkompilierte Header verwenden) verloren gegangen.

Benennen Sie die Objektdatei (mit [/Fo](../../build/reference/fo-object-file-name.md)) beim Erstellen oder Verwenden der vorkompilierten Headerdatei um, und stellen Sie eine Verknüpfung mit der neuen Objektdatei her.