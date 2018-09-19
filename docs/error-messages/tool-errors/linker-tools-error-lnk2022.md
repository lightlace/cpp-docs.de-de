---
title: Linkertoolfehler Lnk2022 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2022
dev_langs:
- C++
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b28e9f31c9ce4a7659891698feff48b16450944
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118348"
---
# <a name="linker-tools-error-lnk2022"></a>Linkertoolfehler LNK2022

> Fehler beim Metadatenvorgang (*HRESULT*): *Error_message*

Der Linker hat einen Fehler beim Zusammenführen von Metadaten. Die Metadatenfehler müssen behoben werden, um erfolgreich zu verknüpfen.

Eine Möglichkeit zur diagnose dieses Problems ist die Ausführung **Ildasm-Token** auf die Objektdateien zu ermitteln, welche Typen enthält die Token in aufgeführten `error_message`, und suchen Sie nach der Unterschiede.  In den Metadaten zwei verschiedene Typen mit demselben Namen ist ungültig, selbst wenn das nur LayoutType-Attribut unterscheidet.

Einen Grund für LNK2022 ist, wenn ein Typ (z. B. eine Struktur) in mehrere Compilands, mit dem gleichen Namen, jedoch mit in Konflikt stehende Definitionen vorhanden ist und beim Kompilieren mit ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md).  In diesem Fall stellen Sie sicher, dass der Typ eine identische Definition in jeder Kompiliereinheit aufweist.  Der Typname finden `error_message`.

Eine weitere mögliche Ursache LNK2022 der Linker wird eine Datei mit Metadaten in einem anderen Speicherort für den Compiler angegeben wurde (mit [#using](../../preprocessor/hash-using-directive-cpp.md) ). Stellen Sie sicher, dass die Metadaten-Datei (DLL- oder NETMODULE-Datei) am gleichen Speicherort, an den Linker übergeben wird, wie wurde zuvor für den Compiler übergeben wurde.

Beim Erstellen von ATL-Anwendungen, die Verwendung des Makros `_ATL_MIXED` ist in jeder Kompiliereinheit erforderlich, wenn er in mindestens einer verwendet wird.

## <a name="example"></a>Beispiel

Im folgende Beispiel wird einen leeren Typ definiert.

```cpp
// LNK2022_a.cpp
// compile with: /clr /c
public ref class Test {};
```

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, dass Sie zwei Quellcodedateien, die Typen, von dem gleichen Namen, aber unterschiedliche Definitionen enthalten keine Verknüpfung möglich.

Im folgende Beispiel wird die LNK2022 generiert.

```cpp
// LNK2022_b.cpp
// compile with: LNK2022_a.cpp /clr /LD
// LNK2022 expected
public ref class Test {
   void func() {}
   int var;
};
```