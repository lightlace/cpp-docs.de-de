---
title: Linkertoolfehler Lnk1312 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1312
dev_langs:
- C++
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 335a3976675f36e3da295bc23c8e17440a56a505
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088646"
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