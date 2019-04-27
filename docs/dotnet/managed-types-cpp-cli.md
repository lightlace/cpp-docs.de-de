---
title: Verwaltete Typen (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], managed
- managed data types [C++]
- .NET Framework [C++], managed types
- data types [C++], .NET feature access
- main function, in managed applications
- managed code, main() function
- .NET Framework [C++], C++ equivalents
- __nogc type declarations
- __value keyword, issues when nesting
- equality, testing for
- versioning, diagnosing conflicts
- versioning
- exceptions, diagnosing odd behavior
- compatibility, between assemblies
ms.assetid: 679b8ed3-d966-4a0c-b627-2a3f3ec96b74
ms.openlocfilehash: b91918d526d83d4cf47436d02b7c67038576bafb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152769"
---
# <a name="managed-types-ccli"></a>Verwaltete Typen (C++/CLI)

Visual C++ können den Zugriff auf Features für .NET über verwaltete Typen, die bieten Unterstützung für Features der common Language Runtime bereitgestellt und unterliegen die Vorteile und Einschränkungen der Runtime.

## <a name="main_functions"></a> Verwaltete Typen und die main-Funktion

Beim Schreiben einer Anwendung mit **"/ CLR"**, die Argumente der **main()** Funktion kann nicht von einem verwalteten Typ sein.

Ein Beispiel für eine ordnungsgemäße Signatur ist:

```cpp
// managed_types_and_main.cpp
// compile with: /clr
int main(int, char*[], char*[]) {}
```

## <a name="dotnet"></a> .NET Framework-Entsprechungen der systemeigenen Typen in C++

Die folgende Tabelle zeigt die Schlüsselwörter für integrierte Visual C++-Typen, die Aliase der vordefinierten Typen sind in der **System** Namespace.

|Visual C++-Typ|.NET Framework-Typ|
|-----------------------|-------------------------|
|**void**|<xref:System.Void?displayProperty=nameWithType>|
|**bool**|<xref:System.Boolean?displayProperty=nameWithType>|
|**signed char** |<xref:System.SByte?displayProperty=nameWithType>|
|**unsigned char**|<xref:System.Byte?displayProperty=nameWithType>|
|**wchar_t**|<xref:System.Char?displayProperty=nameWithType>|
|**kurze** und **kurz signiert**|<xref:System.Int16?displayProperty=nameWithType>|
|**unsigned short**|<xref:System.UInt16?displayProperty=nameWithType>|
|**Int**, **signiert Int**, **lange**, und **lange signiert**|<xref:System.Int32?displayProperty=nameWithType>|
|**ganze Zahl ohne Vorzeichen** und **unsigned long**|<xref:System.UInt32?displayProperty=nameWithType>|
|**__int64** und **signiert __int64**|<xref:System.Int64?displayProperty=nameWithType>|
|**__int64 ohne Vorzeichen**|<xref:System.UInt64?displayProperty=nameWithType>|
|**float**|<xref:System.Single?displayProperty=nameWithType>|
|**doppelte** und **long double**|<xref:System.Double?displayProperty=nameWithType>|

Weitere Informationen zur Compileroption auf den Standardwert zu mit oder ohne Vorzeichen **Char**, finden Sie unter [/j (Standardzeichentyp ist vorzeichenlos)](../build/reference/j-default-char-type-is-unsigned.md).

## <a name="version_issues"></a> Versionsprobleme bei in systemeigenen Typen geschachtelten Werttypen

Beispiel: eine mit Vorzeichen (starker Name)-Assembly-Komponente verwendet, um eine Clientassembly zu erstellen. Die Komponente enthält, einen Werttyp, der auf dem Client als Typ für ein Mitglied aus einer systemeigenen Union, eine Klasse oder ein Array verwendet wird. Wenn die Größe oder das Layout des Werttyps eine zukünftige Version der Komponente geändert wird, muss der Client neu kompiliert werden.

Erstellen Sie eine Schlüsseldatei mit [sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) (`sn -k mykey.snk`).

### <a name="example"></a>Beispiel

Im folgende Beispiel ist die Komponente.

```cpp
// nested_value_types.cpp
// compile with: /clr /LD
using namespace System::Reflection;
[assembly:AssemblyVersion("1.0.0.*"),
assembly:AssemblyKeyFile("mykey.snk")];

public value struct S {
   int i;
   void Test() {
      System::Console::WriteLine("S.i = {0}", i);
   }
};
```

### <a name="example"></a>Beispiel

In diesem Beispiel ist der Client:

```cpp
// nested_value_types_2.cpp
// compile with: /clr
#using <nested_value_types.dll>

struct S2 {
   S MyS1, MyS2;
};

int main() {
   S2 MyS2a, MyS2b;
   MyS2a.MyS1.i = 5;
   MyS2a.MyS2.i = 6;
   MyS2b.MyS1.i = 10;
   MyS2b.MyS2.i = 11;

   MyS2a.MyS1.Test();
   MyS2a.MyS2.Test();
   MyS2b.MyS1.Test();
   MyS2b.MyS2.Test();
}
```

### <a name="output"></a>Output

```Output
S.i = 5
S.i = 6
S.i = 10
S.i = 11
```

### <a name="comments"></a>Kommentare

Aber wenn Sie ein anderes Element hinzufügen `struct S` in nested_value_types.cpp, (z. B. `double d;`) und auf die Komponente neu kompilieren, ohne erneute Kompilierung des Clients, auf das Ergebnis ist eine nicht behandelte Ausnahme (vom Typ <xref:System.IO.FileLoadException?displayProperty=fullName>).

## <a name="test_equality"></a> Vorgehensweise: Test auf Gleichheit

Im folgenden Beispiel wird ein Test auf Gleichheit, die Managed Extensions for C++ verwendet hängt von was die Handles verweisen.

### <a name="example"></a>Beispiel

```cpp
// mcppv2_equality_test.cpp
// compile with: /clr /LD
using namespace System;

bool Test1() {
   String ^ str1 = "test";
   String ^ str2 = "test";
   return (str1 == str2);
}
```

Die IL für dieses Programm zeigt, dass der zurückgegebene Wert mit dem Aufruf von Op_Equality implementiert wird.

```MSIL
IL_0012:  call       bool [mscorlib]System.String::op_Equality(string,
                                                               string)
```

## <a name="diagnose_fix"></a> Vorgehensweise: Diagnostizieren und Beheben von Kompatibilitätsproblemen bei Assemblys

In diesem Thema wird erläutert, was passieren kann, wenn die Version einer Assembly, auf die verwiesen wird zum Zeitpunkt der Kompilierung nicht mit der Version der Assembly verwiesen wird, während der Laufzeit übereinstimmt und wie Sie das Problem zu vermeiden.

Wenn eine Assembly kompiliert wird, können andere Assemblys verwiesen werden, mit der `#using` Syntax. Diese Assemblys erfolgt während der Kompilierung vom Compiler verwendet wird. Informationen über diese Assemblys wird verwendet, um Entscheidungen zur Optimierung.

Wenn jedoch die referenzierte Assembly geändert und neu kompiliert wird und Sie werden nicht erneut kompilieren die verweisende Assembly, die davon abhängig ist, die Assemblys möglicherweise nicht immer noch kompatibel sein. Optimierungsentscheidungen, die bei gültig waren möglicherweise zuerst nicht richtig in Bezug auf die neue Version der Assembly sein. Aufgrund dieser Inkompatibilitäten können verschiedene Laufzeitfehler auftreten. Es ist keine spezifische Ausnahme, die in diesen Fällen erzeugt werden. Die Möglichkeit, die der Fehler zur Laufzeit gemeldet wird, hängt von der Art der die Änderung des Codes, die die Ursache des Problems ab.

Dieser Fehler sollte kein Problem in der endgültigen Produktionscode, solange die gesamte Anwendung für die veröffentlichte Version des Produkts neu erstellt wird. Assemblys, die für die Öffentlichkeit freigegeben werden sollte mit einer offiziellen Versionsnummer, markiert werden, um sicherzustellen, dass diese Probleme vermieden werden. Weitere Informationen dazu finden Sie unter [Assemblyversionen](/dotnet/framework/app-domains/assembly-versioning).

### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>Diagnostizieren und Beheben eines Inkompatibilitätsfehlers

1. Wenn Sie auftreten, Common Language Runtime-Ausnahmen oder andere fehlerbedingungen, die im Code auftreten, die eine andere Assembly verweist, und keine anderen identifizierten Ursache haben, können Sie mit einer Assembly nicht mehr aktuell zu tun.

1. Zunächst zu isolieren und die Ausnahme oder anderen Fehlerzustand zu reproduzieren. Ein Problem, aufgrund einer veralteten Ausnahme auftritt, sollten reproduziert werden.

1. Überprüfen Sie den Zeitstempel aller Assemblys, die in Ihrer Anwendung verwiesen wird.

1. Wenn die Zeitstempel der alle referenzierten Assemblys höher als der Zeitstempel der letzten Kompilierung Ihrer Anwendung sind, ist Ihre Anwendung nicht mehr aktuell. In diesem Fall kompilieren Sie die Anwendung mit der neuesten Assembly neu, und stellen Sie codeänderungen erforderlich.

1. Führen Sie die Anwendung erneut aus, führen Sie die Schritte, die das Problem reproduzieren, und stellen Sie sicher, dass die Ausnahme nicht auftritt.

### <a name="example"></a>Beispiel

Das folgende Programm veranschaulicht das Problem durch reduzieren den Zugriff auf eine Methode, und diese Methode in einer anderen Assembly ohne erneute Kompilierung zugreifen möchten. Kompilieren Sie `changeaccess.cpp` erste. Dies ist die referenzierte Assembly, die geändert wird. Kompilieren Sie dann `referencing.cpp`. Die Kompilierung erfolgreich ist. Nun, verringern Sie den Zugriff auf die aufgerufene Methode. RECOMPILE `changeaccess.cpp` mit dem Flag `/DCHANGE_ACCESS`. Dadurch wird die Methode geschützt, und nicht als "private", damit mehr gesetzlich aufgerufen werden kann. Ohne erneute Kompilierung `referencing.exe`, führen Sie die Anwendung erneut aus. Eine Ausnahme <xref:System.MethodAccessException> führt.

```cpp
// changeaccess.cpp
// compile with: /clr:safe /LD
// After the initial compilation, add /DCHANGE_ACCESS and rerun
// referencing.exe to introduce an error at runtime. To correct
// the problem, recompile referencing.exe

public ref class Test {
#if defined(CHANGE_ACCESS)
protected:
#else
public:
#endif

  int access_me() {
    return 0;
  }

};
```

```cpp
// referencing.cpp
// compile with: /clr:safe
#using <changeaccess.dll>

// Force the function to be inline, to override the compiler's own
// algorithm.
__forceinline
int CallMethod(Test^ t) {
  // The call is allowed only if access_me is declared public
  return t->access_me();
}

int main() {
  Test^ t = gcnew Test();
  try
  {
    CallMethod(t);
    System::Console::WriteLine("No exception.");
  }
  catch (System::Exception ^ e)
  {
    System::Console::WriteLine("Exception!");
  }
  return 0;
}
```

## <a name="see-also"></a>Siehe auch

[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[Interoperabilität mit anderen .NET-Sprachen (C++/CLI)](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)<br/>
[Verwaltete Typen (C++/CLI)](../dotnet/managed-types-cpp-cli.md)<br/>
[#using-Direktive](../preprocessor/hash-using-directive-cpp.md)
