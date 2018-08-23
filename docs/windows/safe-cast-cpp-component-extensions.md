---
title: Safe_cast (Komponentenerweiterungen für C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b09bbb831218c073b590233c572d5a5453659ed
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595331"
---
# <a name="safecast-c-component-extensions"></a>safe_cast (Komponentenerweiterungen für C++)

Die **"safe_cast"** Vorgang gibt den angegebenen Ausdruck als den angegebenen Typ zurück, wenn erfolgreich; andernfalls löst `InvalidCastException`.

## <a name="all-runtimes"></a>Alle Laufzeiten

(Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.)

### <a name="syntax"></a>Syntax

```cpp
[default]:: safe_cast<
type-id
>(
expression
)  
```

## <a name="windows-runtime"></a>Windows-Runtime

**Safe_cast** können Sie den Typ des angegebenen Ausdrucks zu ändern. In Situationen, in dem Sie vollständig erwarten, dass eine Variable oder Parameter, um zu einem bestimmten Typ konvertiert werden können, können Sie **"safe_cast"** ohne eine **Try / Catch** Block, um während der Entwicklung Programmierfehler zu erkennen. Weitere Informationen finden Sie unter [Umwandlung (C++ / CX)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx).

### <a name="syntax"></a>Syntax

```cpp
[default]:: safe_cast<
type-id
>(
expression
)  
```

### <a name="parameters"></a>Parameter

*Typ-id*  
Der zu konvertierende Typ *Ausdruck* auf. Ein Handle zu einem Verweis- oder Werttyp, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis- oder Werttyp.

*Ausdruck*  
Ein Ausdruck, der als ein Handle zu einem Verweis oder Werttyp ausgewertet wird, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis- oder Werttyp.

### <a name="remarks"></a>Hinweise

**Safe_cast** löst `InvalidCastException` , wenn sie nicht konvertieren kann *Ausdruck* in den vom angegebenen Typ *Typ-Id*. Zum Abfangen von `InvalidCastException`, geben Sie die [/EH (Ausnahmebehandlungsmodell)](../build/reference/eh-exception-handling-model.md) -Compileroption, und Verwenden einer **Try/Catch-** Anweisung.

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

### <a name="examples"></a>Beispiele

Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit **"safe_cast"** mit der Windows-Runtime.

```cpp
// safe_cast_ZW.cpp
// compile with: /ZW /EHsc

using namespace default;
using namespace Platform;

interface class I1 {};
interface class I2 {};
interface class I3 {};

ref class X : public I1, public I2 {};

int main(Array<String^>^ args) {
   I1^ i1 = ref new X;
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead
   try {
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.
   }
   catch(InvalidCastException^ ic) {
   wprintf(L"Caught expected exception: %s\n", ic->Message);
   }
}
```

```Output
Caught expected exception: InvalidCastException
```

## <a name="common-language-runtime"></a>Common Language Runtime

**Safe_cast** ermöglicht es Ihnen, ändern Sie den Typ eines Ausdrucks und überprüfbaren MISL-Code zu generieren.

### <a name="syntax"></a>Syntax

```cpp
[cli]:: safe_cast<
type-id
>(
expression
)  
```

### <a name="parameters"></a>Parameter

*Typ-id*  
Ein Handle zu einem Verweis- oder Werttyp, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis- oder Werttyp.

*Ausdruck*  
Ein Ausdruck, der als ein Handle zu einem Verweis oder Werttyp ausgewertet wird, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis- oder Werttyp.

### <a name="remarks"></a>Hinweise

Der Ausdruck `safe_cast<` *Typ-Id*`>(`*Ausdruck* `)` konvertiert den operandenausdruck zu einem Objekt vom Typ-Id-Typ.

Der Compiler akzeptiert eine ["static_cast"](../cpp/static-cast-operator.md) in den meisten stellen, die sie akzeptieren ein **"safe_cast"**.  Allerdings **"safe_cast"** überprüfbare MSIL generiert auf jeden Fall Where als eine **"static_cast"** konnte nicht überprüfbare MSIL erzeugen.  Finden Sie unter [reiner und überprüfbarer Code (C++ / CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) und [Peverify.exe (PEVerify-Tool)](/dotnet/framework/tools/peverify-exe-peverify-tool) für Weitere Informationen über überprüfbaren Code.

Wie **"static_cast"**, **"safe_cast"** benutzerdefinierte Konvertierungen aufruft.

Weitere Informationen zu Umwandlungen finden Sie unter [Umwandlungsoperatoren](../cpp/casting-operators.md).

**Safe_cast** gilt nicht, eine **"const_cast"** (umwandeln **const**).

**Safe_cast** befindet sich in der Cli-Namespace.  Finden Sie unter [Platform-, Default- und Cli-Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) für Weitere Informationen.

Weitere Informationen zu **"safe_cast"**, finden Sie unter:

- [C-stilartige Umwandlungen mit/CLR (C++ / CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)

- [Vorgehensweise: Verwenden von safe_cast in C++/CLI](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)  

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Ein Beispiel, wo der Compiler nicht akzeptiert eine **"static_cast"** jedoch akzeptiert eine **"safe_cast"** sind Umwandlungen zwischen nicht verknüpften Schnittstellentypen.  Mit **"safe_cast"**, der Compiler wird keine Konvertierungsfehler und führt eine Überprüfung zur Laufzeit, um festzustellen, ob die Umwandlung möglich ist

```cpp
// safe_cast.cpp
// compile with: /clr
using namespace System;

interface class I1 {};
interface class I2 {};
interface class I3 {};

ref class X : public I1, public I2 {};

int main() {
   I1^ i1 = gcnew X;
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead
   try {
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type
   }
   catch(InvalidCastException^) {
      Console::WriteLine("Caught expected exception");
   }
}
```

```Output
Caught expected exception
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)