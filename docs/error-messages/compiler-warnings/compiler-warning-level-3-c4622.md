---
title: Compilerwarnung (Stufe 3) C4622
ms.date: 11/04/2016
f1_keywords:
- C4622
helpviewer_keywords:
- C4622
ms.assetid: d3c879f0-4492-4f4b-b26d-230993f3a933
ms.openlocfilehash: 88a41c7f9edb1d2a9f6d4547336a77bd5e362882
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401747"
---
# <a name="compiler-warning-level-3-c4622"></a>Compilerwarnung (Stufe 3) C4622

Überschreiben der Debuginformationen, die beim Erstellen des vorkompilierten Headers in der Objektdatei angelegt wurden: „file“

Die Codeansichtsinformationen in der angegebenen Datei sind bei der Kompilierung mit der [/Yu](../../build/reference/yu-use-precompiled-header-file.md) -Option (Vorkompilierte Header verwenden) verloren gegangen.

Benennen Sie die Objektdatei (mit [/Fo](../../build/reference/fo-object-file-name.md)) beim Erstellen oder Verwenden der vorkompilierten Headerdatei um, und stellen Sie eine Verknüpfung mit der neuen Objektdatei her.