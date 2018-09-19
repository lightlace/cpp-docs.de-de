---
title: Linkertoolfehler Lnk1179 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1179
dev_langs:
- C++
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d22ebb329d390d44aea44ff9dc6f3bf2f86a1d26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117453"
---
# <a name="linker-tools-error-lnk1179"></a>Linkertoolfehler LNK1179

Ungültige oder beschädigte Datei: COMDAT "Filename" doppelt

Ein Objektmodul enthält mindestens zwei COMDATs mit dem gleichen Namen.

Dieser Fehler kann verursacht werden, mithilfe von [/h](../../build/reference/h-restrict-length-of-external-names.md), die die Länge externer Namen beschränken und [/Gy](../../build/reference/gy-enable-function-level-linking.md), welche Funktionen in COMDATs Pakete.

## <a name="example"></a>Beispiel

In den folgenden Code `function1` und `function2` in den ersten acht Zeichen identisch sind. Beim Kompilieren mit **/Gy** und **/H8** entsteht ein Bindungsfehler.

```
void function1(void);
void function2(void);

int main() {
    function1();
    function2();
}

void function1(void) {}
void function2(void) {}
```