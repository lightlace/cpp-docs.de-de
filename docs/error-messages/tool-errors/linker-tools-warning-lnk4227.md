---
title: Linkertoolwarnung LNK4227
ms.date: 11/04/2016
f1_keywords:
- LNK4227
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
ms.openlocfilehash: fb657719c69445ce23d36ccf04ac4a14db0955e4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558261"
---
# <a name="linker-tools-warning-lnk4227"></a>Linkertoolwarnung LNK4227

> Warnung bei Metadatenoperation (*HRESULT*): *Warning_message*

Der Linker entdeckt Unterschiede in den Metadaten beim Zusammenführen von:

- Eine oder mehrere referenzierten Assemblys mit der Assembly, die gerade erstellt wird.

- Eine oder mehrere Quellcodedateien in einer Kompilierung.

Z. B. LNK4227 kann verursacht werden, wenn Sie zwei globale Funktionen, mit dem gleichen Namen, aber Parameterinformationen unterschiedlich deklariert haben (d. h. Deklarationen sind nicht konsistent in allen Compilands Wert). Mithilfe von ildasm.exe/Text/Metadata *Object_file* in jeder OBJ-Datei, um festzustellen, wie die Typen unterscheiden.

LNK4227 dient auch zum Melden von Problemen, die mit einem anderen Tool stammen. Suchen Sie nach der Warnmeldung, dass weitere Informationen.

Die Metadaten-Probleme müssen behoben werden, um die Warnung zu beheben.

## <a name="example"></a>Beispiel

LNK4227 wird generiert, wenn es sich bei eine referenzierte Assembly anders als die Assembly signiert wurde, die darauf verweist.

Im folgende Beispiel wird die LNK4227 generiert:

```cpp
// LNK4227.cpp
// compile with: /clr
using namespace System::Reflection;

[assembly:AssemblyDelaySignAttribute(false)];

int main() {}
```

Und dann

```cpp
// LNK4227b.cpp
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe
using namespace System::Reflection;
using namespace System::Runtime::CompilerServices;

[assembly:AssemblyDelaySignAttribute(true)];
// Try the following line instead
// [assembly:AssemblyDelaySignAttribute(false)];

ref class MyClass
{
};
```

## <a name="example"></a>Beispiel

LNK4227 kann auch generiert werden, wenn die Versionsnummern im falschen Format zu Assemblyattributen übergeben werden.  Die ' *' Notation bezieht sich auf die `AssemblyVersionAttribute`.  Um diese Warnung zu beheben, verwenden nur Zahlen in der Version-Attribute als `AssemblyVersionAttribute`.

Im folgende Beispiel wird die LNK4227 generiert:

```cpp
// LNK4227e.cpp
// compile with: /clr /LD /W1
using namespace System::Reflection;
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227
// try the following line instead
// [assembly:AssemblyFileVersionAttribute("2.3")];
```