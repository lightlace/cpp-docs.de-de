---
title: Linkertoolfehler LNK1107
ms.date: 11/04/2016
f1_keywords:
- LNK1107
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
ms.openlocfilehash: c75966d9c6c22f1bd2123fb30282bb2bed467130
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991025"
---
# <a name="linker-tools-error-lnk1107"></a>Linkertoolfehler LNK1107

Ungültige oder beschädigte Datei: der Speicherort kann nicht gelesen werden.

Das Tool konnte die Datei nicht lesen. Erstellen Sie die Datei erneut.

Linkertoolfehler LNK1107 kann auch auftreten, wenn Sie versuchen, ein Modul (dll-oder NETMODULE-Erweiterung, das mit [/clr: noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) oder [/noAssembly](../../build/reference/noassembly-create-a-msil-module.md)erstellt wurde) an den Linker zu übergeben. übergeben Sie stattdessen die OBJ-Datei.

Wenn Sie das folgende Beispiel kompilieren:

```cpp
// LNK1107.cpp
// compile with: /clr /LD
public ref class MyClass {
public:
   void Test(){}
};
```

und geben Sie dann " **Link Linkertoolfehler LNK1107. dll** " in der Befehlszeile an. Sie erhalten Linkertoolfehler LNK1107.  Um den Fehler zu beheben, geben Sie stattdessen **Link Linkertoolfehler LNK1107. obj** an.
