---
title: Platform-, Default- und Cli-Namespaces (C++ / CLI und C++ / CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- lang
- cli
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
ms.openlocfilehash: fb7c9135051d790a488775451e1d333ce69d3dda
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598003"
---
# <a name="platform-default-and-cli-namespaces--ccli-and-ccx"></a>Platform-, Default- und Cli-Namespaces (C++ / CLI und C++ / CX)

Ein Namespace qualifiziert die Namen von Sprachelementen, sodass sie keinen Konflikt mit ansonsten identischen Namen an anderer Stelle im Quellcode verursachen. Z. B. ein Namenskonflikt möglicherweise verhindern, dass den Compiler erkennt [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md). Namespaces werden vom Compiler verwendet, jedoch nicht in der kompilierten Assembly beibehalten.

## <a name="all-runtimes"></a>Alle Laufzeiten

Visual Studio bietet einen Standardnamespace für das Projekt, wenn Sie das Projekt zu erstellen. Sie können den Namespace manuell umbenennen, obwohl in C++ / CX-der Name der winmd-Datei muss den Namen des Stammnamespace übereinstimmen.

## <a name="windows-runtime"></a>Windows-Runtime

Weitere Informationen finden Sie unter [Namespaces und typsichtbarkeit (C++ / CX)](https://msdn.microsoft.com/library/windows/apps/hh969551.aspx).

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

### <a name="syntax"></a>Syntax

```cpp
using namespace cli;
```

### <a name="remarks"></a>Hinweise

C++ / CLI unterstützt die **Cli** Namespace. Beim Kompilieren mit `/clr`, **mit** -Anweisung im Syntaxabschnitt wird impliziert.

Die folgenden Sprachfunktionen sind in der **Cli** Namespace:

- [Arrays](../windows/arrays-cpp-component-extensions.md)

- [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)

- [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)

- ["safe_cast"](../windows/safe-cast-cpp-component-extensions.md)

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Im folgenden Codebeispiel wird veranschaulicht, dass es möglich ist, verwenden Sie ein Symbol in der **Cli** Namespace als benutzerdefiniertes Symbol im Code.  Sobald Sie dies erledigt haben, Sie müssen jedoch explizit oder implizit qualifiziert die Verweise auf die **Cli** Language-Element mit dem gleichen Namen.

```cpp
// cli_namespace.cpp
// compile with: /clr
using namespace cli;
int main() {
   array<int> ^ MyArray = gcnew array<int>(100);
   int array = 0;

   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062

   // OK
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);
}
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](../windows/component-extensions-for-runtime-platforms.md)