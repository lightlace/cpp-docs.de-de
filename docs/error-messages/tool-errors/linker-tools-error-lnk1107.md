---
title: Linkertoolfehler LNK1107
ms.date: 11/04/2016
f1_keywords:
- LNK1107
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
ms.openlocfilehash: 68048d9f824283d002a4ea8b64d88f37bbeefc48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255391"
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