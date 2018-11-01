---
title: Linkertoolfehler LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: 49fa7e7963d6bb561e1602b58fe1f26c5f3d54bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436230"
---
# <a name="linker-tools-error-lnk1312"></a>Linkertoolfehler LNK1312

Ungültige oder beschädigte Datei: Assembly konnte nicht importiert

Beim Erstellen einer Assembly, eine Datei als ein Modul oder eine Assembly, die mit kompiliert **"/ CLR"** übergebene der **ASSEMBLYMODULE** -Linkeroption.  Wenn Sie eine Objektdatei, damit übergeben **ASSEMBLYMODULE**, übergeben Sie das Objekt direkt an dem Linker, nicht an **ASSEMBLYMODULE**.

## <a name="example"></a>Beispiel

Das folgende Beispiel erstellt die OBJ-Datei.

```
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die LNK1312 generiert.

```
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```