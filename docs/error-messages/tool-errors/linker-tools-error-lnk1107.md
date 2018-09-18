---
title: Linkertoolfehler Lnk1107 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1107
dev_langs:
- C++
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73a1643d10ea9adc6ac6979eb2de023593ba8d01
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060706"
---
# <a name="linker-tools-error-lnk1107"></a>Linkertoolfehler LNK1107

Ungültige oder beschädigte Datei: kann nicht gelesen, am Speicherort

Das Tool konnte die Datei nicht gelesen werden. Erstellen Sie die Datei neu.

LNK1107 kann auch auftreten, wenn Sie versuchen, ein Modul übergeben (DLL- oder netmodule-Erweiterung, die mit erstellt [/CLR: noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) oder [/noAssembly](../../build/reference/noassembly-create-a-msil-module.md)) an den Linker; die OBJ-Datei stattdessen übergeben werden.

Wenn Sie im folgende Beispiel kompilieren:

```
// LNK1107.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

und geben Sie dann **verknüpfen LNK1107.dll** erhalten Sie in der Befehlszeile LNK1107.  Geben Sie den Fehler zu beheben, **verknüpfen LNK1107.obj** stattdessen.