---
title: Linkertoolfehler Lnk2031 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2031
dev_langs:
- C++
helpviewer_keywords:
- LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d86ea6da8a73d9ba2427e9455c4fca87cd32dd2b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34703664"
---
# <a name="linker-tools-error-lnk2031"></a>Linkertoolfehler LNK2031

> für p/invoke konnte nicht generiert "*Function_declaration*" *ergänzter_Name*; Aufrufkonvention, die in den Metadaten fehlt

## <a name="remarks"></a>Hinweise

Beim Versuch, eine systemeigene Funktion in einem reinen Image zu importieren, denken Sie daran, dass die impliziten Aufrufkonventionen zwischen systemeigenen und reinen Kompilierungen unterscheiden. Weitere Informationen zu reinen Bildern finden Sie unter [reiner und überprüfbarer Code (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

Die **/CLR: pure** -Compileroption in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt wird.

## <a name="example"></a>Beispiel

In diesem Codebeispiel wird eine Komponente mit einer exportierten, systemeigen Funktion, deren Aufrufkonvention implizit generiert [__cdecl](../../cpp/cdecl.md).

```cpp
// LNK2031.cpp
// compile with: /LD
extern "C" {
   __declspec(dllexport) int func() { return 3; }
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel erstellt einen reinen Client, der die systemeigene Funktion verwendet. Allerdings die Aufrufkonvention unter **/CLR: pure** ist [__clrcall](../../cpp/clrcall.md). Im folgende Beispiel wird LNK2031 generiert.

```cpp
// LNK2031_b.cpp
// compile with: /clr:pure LNK2031.lib
// LNK2031 expected
extern "C" int func();

int main() {
   return func();
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird gezeigt, wie die systemeigene Funktion in einem reinen Image genutzt wird. Beachten Sie den expliziten **__cdecl** Spezifizierer der Aufrufkonvention.

```cpp
// LNK2031_c.cpp
// compile with: /clr:pure LNK2031.lib
extern "C" int __cdecl func();

int main() {
   return func();
}
```