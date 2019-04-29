---
title: Linkertoolfehler LNK1179
ms.date: 11/04/2016
f1_keywords:
- LNK1179
helpviewer_keywords:
- LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
ms.openlocfilehash: 71aba1f20cfaf5b6b9ec33d43ebde594e381921f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391412"
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