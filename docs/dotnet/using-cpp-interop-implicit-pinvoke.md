---
title: Verwenden von C++-Interop (implizites PInvoke)
ms.date: 11/04/2016
helpviewer_keywords:
- blittable types [C++]
- platform invoke [C++], implicit
- interop [C++], features
- data marshaling [C++], C++ Interop features
- porting [C++], C++ native to .NET
- COM interfaces [C++]
- implicit platform invoke
- examples [C++], interoperability
- types [C++], blittable
- marshaling [C++], C++ Interop features
- platform invoke [C++], examples
- interoperability [C++]
- C++ Interop
- interoperability [C++], Implicit PInvoke
- C++, interop
- C++ COM Interop
- .NET [C++], porting C++ native to
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
ms.openlocfilehash: aaa07373b7dd22807290ceefa9197b4013c61fe5
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58778233"
---
# <a name="using-c-interop-implicit-pinvoke"></a>Verwenden von C++-Interop (implizites PInvoke)

Im Gegensatz zu anderen .NET-Sprachen verfügt Visual C++ interoperabilitätsunterstützung, die verwalteten und nicht verwaltetem Code vorhanden sein, in der gleichen Anwendung und sogar in derselben Datei ermöglicht (mit der [verwaltete, unverwaltete](../preprocessor/managed-unmanaged.md) Pragmas). Auf diese Weise können Visual C++-Entwickler .NET-Funktionalität in vorhandene Visual C++-Anwendungen integrieren, ohne den Rest der Anwendung zu beeinträchtigen.

Sie können auch nicht verwaltete Funktionen aus einer verwalteten Kompiliereinheit Aufrufen [Dllexport, Dllimport](../cpp/dllexport-dllimport.md).

Implizites PInvoke ist sinnvoll, wenn Sie das Marshalling von Funktionsparametern oder andere Details, die bei einem expliziten Aufruf von DllImportAttribute angegeben werden können, nicht festlegen müssen.

Visual C++ bietet zwei Möglichkeiten für die Interoperation von verwalteten und nicht verwalteten Funktionen:

- [Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)

Explizites PInvoke wird von .NET Framework unterstützt und ist in den meisten .NET-Sprachen verfügbar. Doch wie der Name schon sagt, ist C++-Interop Visual C++-spezifisch.

## <a name="c-interop"></a>C++ Interop

C++-Interop wird gegenüber explizitem PInvoke empfohlen, da es bessere Typsicherheit bietet, normalerweise einfacher zu implementieren ist, sich bei Änderungen der nicht verwalteten API leichter handhaben lässt und Leistungsverbesserungen erlaubt, die mit explizitem PInvoke nicht möglich sind. C++-Interop ist jedoch nicht möglich, wenn der nicht verwaltete Quellcode nicht verfügbar ist.

## <a name="c-com-interop"></a>C++-COM-Interop

Die von Visual C++ unterstützten Interoperabilitätsfunktionen bieten einen besonderen Vorteil gegenüber anderen .NET-Sprachen, wenn es um die Interoperation mit COM-Komponenten geht. Nicht auf die Einschränkungen von .NET Framework beschränkt [Tlbimp.exe (Type Library Importer-Tool)](/dotnet/framework/tools/tlbimp-exe-type-library-importer), z. B. eingeschränkte Unterstützung für Datentypen und das obligatorische Verfügbarmachen jedes einzelnen Members der einzelnen COM-Schnittstellen, C++-Interop ermöglicht COM Komponenten am Zugriff auf und erfordert keine separate interop-Assemblys. Im Gegensatz zu Visual Basic und C#, Visual C++ können COM-Objekte, die direkt mit der üblichen COM-Mechanismen verwenden (z. B. **CoCreateInstance** und **QueryInterface**). Dies ist möglich, da die C++-Interop-Funktionen, die dazu führen, dass den Compiler zum automatischen Einfügen von Code für den Übergang zum Verschieben von verwaltetem zu nicht verwalteten Funktionen und wieder zurück.

C++-Interop können, COM-Komponenten verwendet werden, wie sie normalerweise verwendet werden, oder sie innerhalb von C++-Klassen eingebunden werden können. Diese Wrapperklassen werden als benutzerdefinierte Runtime callable Wrapper, oder CRCWs, und sie haben zwei Vorteile gegenüber der Verwendung von COM direkt im Anwendungscode:

- Die resultierende Klasse kann von anderen Sprachen als Visual C++ verwendet werden.

- Die Details der COM-Schnittstelle können aus dem verwalteten Clientcode ausgeblendet werden. .NET Datentypen anstelle von systemeigenen Typen verwendet werden können, und die Details des Marshalling von Daten in die CRCW transparent ausgeführt werden können.

Unabhängig davon, ob COM direkt oder über eine CRCW verwendet wird müssen die Argumenttypen einfach, blitfähige Typen gemarshallt werden.

## <a name="blittable-types"></a>Blitfähige Typen

Für nicht verwaltete APIs, die einfache, systeminterne Typen verwenden (finden Sie unter [blitfähige und nicht blitfähige Typen](/dotnet/framework/interop/blittable-and-non-blittable-types)), keine besondere Codierung ist erforderlich, da diese Datentypen die gleiche Darstellung im Arbeitsspeicher haben, während komplexere Datentypen erfordern explizite Daten-Marshalling. Ein Beispiel finden Sie unter [Gewusst wie: Aufrufen von systemeigenen DLLs in verwaltetem Code mithilfe von PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md).

## <a name="example"></a>Beispiel

```cpp
// vcmcppv2_impl_dllimp.cpp
// compile with: /clr:pure user32.lib
using namespace System::Runtime::InteropServices;

// Implicit DLLImport specifying calling convention
extern "C" int __stdcall MessageBeep(int);

// explicit DLLImport needed here to use P/Invoke marshalling because
// System::String ^ is not the type of the first parameter to printf
[DllImport("msvcrt.dll", EntryPoint = "printf", CallingConvention = CallingConvention::Cdecl,  CharSet = CharSet::Ansi)]
// or just
// [DllImport("msvcrt.dll")]
int printf(System::String ^, ...);

int main() {
   // (string literals are System::String by default)
   printf("Begin beep\n");
   MessageBeep(100000);
   printf("Done\n");
}
```

```Output
Begin beep
Done
```

## <a name="in-this-section"></a>In diesem Abschnitt

- [Vorgehensweise: Marshallen von ANSI-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)

- [Vorgehensweise: Marshallen von Unicode-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)

- [Vorgehensweise: Marshallen von COM-Zeichenfolgen mit C++-Interop](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)

- [Vorgehensweise: Marshallen von Strukturen mit C++-Interop](../dotnet/how-to-marshal-structures-using-cpp-interop.md)

- [Vorgehensweise: Marshallen von Arrays mit C++-Interop](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)

- [Vorgehensweise: Marshallen von Rückrufen und Delegaten mit C++-Interop](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)

- [Vorgehensweise: Marshallen von eingebetteten Zeigern mit C++-Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)

- [Vorgehensweise: Zugriff auf Zeichen in einem System::String](../dotnet/how-to-access-characters-in-a-system-string.md)

- [Vorgehensweise: Umwandeln von char * String nach System::Byte Array](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)

- [Vorgehensweise: Konvertieren von System:: String in Wchar_t * oder char\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)

- [Vorgehensweise: Konvertieren von System::String zu Standardzeichenfolge](../dotnet/how-to-convert-system-string-to-standard-string.md)

- [Vorgehensweise: Konvertieren einer Standardzeichenfolge nach System::String](../dotnet/how-to-convert-standard-string-to-system-string.md)

- [Vorgehensweise: Abrufen eines Zeigers auf ein Byte-Array](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)

- [Vorgehensweise: Laden von nicht verwalteten Ressourcen in ein Byte-Array](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)

- [Vorgehensweise: Ändern der Verweisklasse in einer nativen Funktion](../dotnet/how-to-modify-reference-class-in-a-native-function.md)

- [Vorgehensweise: Ermitteln, ob ein Bild nativ oder CLR ist](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)

- [Vorgehensweise: Hinzufügen einer nativen DLL zum globalen Assemblycache](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)

- [Vorgehensweise: Verweis auf Werttyp in nativem Typ](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)

- [Vorgehensweise: Objektverweis in nicht verwaltetem Arbeitsspeicher](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)

- [Vorgehensweise: Erkennen von/CLR-Kompilierung](../dotnet/how-to-detect-clr-compilation.md)

- [Vorgehensweise: Konvertieren zwischen System::Guid und _GUID](../dotnet/how-to-convert-between-system-guid-and-guid.md)

- [Vorgehensweise: Angeben eines out-Parameters](../dotnet/how-to-specify-an-out-parameter.md)

- [Vorgehensweise: Verwenden eines nativen Typs in einer/CLR-Kompilierung](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)

- [Vorgehensweise: Deklarieren von Handles in nativen Typen](../dotnet/how-to-declare-handles-in-native-types.md)

- [Vorgehensweise: Kapseln einer nativen Klasse zur Verwendung in C#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)

Informationen zum Verwenden von Delegaten in einem Interop-Szenario finden Sie unter [Delegate (Komponentenerweiterungen)](../extensions/delegate-cpp-component-extensions.md).

## <a name="see-also"></a>Siehe auch

- [Aufrufen nativer Funktionen aus verwaltetem Code](../dotnet/calling-native-functions-from-managed-code.md)
