---
title: Linkertoolfehler LNK1312
ms.date: 11/04/2016
f1_keywords:
- LNK1312
helpviewer_keywords:
- LNK1312
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
ms.openlocfilehash: e462d24f2eb54718ba73617146aab96bb14a66df
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990909"
---
# <a name="linker-tools-error-lnk1312"></a>Linkertoolfehler LNK1312

Ungültige oder beschädigte Datei: die Assembly kann nicht importiert werden.

Beim Erstellen einer Assembly wurde eine andere Datei als ein Modul oder eine Assembly, die mit **/CLR** kompiliert wurde, an die **/ASSEMBLYMODULE** Linker-Option übermittelt.  Wenn Sie eine Objektdatei an **/ASSEMBLYMODULE**übergeben haben, übergeben Sie das Objekt einfach direkt an den Linker anstatt an **/ASSEMBLYMODULE**.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wurde die OBJ-Datei erstellt.

```cpp
// LNK1312.cpp
// compile with: /clr /LD
public ref class A {
public:
   int i;
};
```

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird Linkertoolfehler LNK1312 generiert.

```cpp
// LNK1312_b.cpp
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj
// LNK1312 error expected
public ref class M {};
```
