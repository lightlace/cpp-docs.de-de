---
title: "Verwenden von C++-Interop (implizites PInvoke)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET [C++], Portieren von C++-eigenem auf"
  - "Blitfähige Typen [C++]"
  - "C++ COM-Interop"
  - "C++ Interop"
  - "C++, Interop"
  - "COM-Schnittstellen [C++]"
  - "Datenmarshalling [C++], C++ Interop-Features"
  - "Beispiele [C++], Interoperabilität"
  - "Impliziter Plattformaufruf"
  - "Interop [C++], Funktionen"
  - "Interoperabilität [C++]"
  - "Interoperabilität [C++], Implizites PInvoke"
  - "Marshaling [C++], C++ Interop-Features"
  - "Plattformaufruf [C++], Beispiele"
  - "Plattformaufruf [C++], Implizite"
  - "Portieren [C++], Von C++-eigenem auf .NET"
  - "Typen [C++], Blitfähig"
ms.assetid: 5f710bf1-88ae-4c4e-8326-b3f0b7c4c68a
caps.latest.revision: 27
caps.handback.revision: "25"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von C++-Interop (implizites PInvoke)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im Gegensatz zu anderen .NET\-Sprachen verfügt Visual C\+\+ über eine Interoperabilitätsunterstützung, dank der verwalteter und nicht verwalteter Code in derselben Anwendung und sogar in derselben Datei verwendet werden können \(mit den [managed, unmanaged](../preprocessor/managed-unmanaged.md)\-Pragmas\).  Auf diese Weise können Visual C\+\+\-Entwickler .NET\-Funktionalität in vorhandene Visual C\+\+\-Anwendungen integrieren, ohne den Rest der Anwendung zu beeinträchtigen.  
  
 Mit [dllexport, dllimport](../cpp/dllexport-dllimport.md) können Sie außerdem nicht verwaltete Funktionen aus einer verwalteten Kompiliereinheit aufrufen.  
  
 Implizites PInvoke ist sinnvoll, wenn Sie das Marshalling von Funktionsparametern oder andere Details, die bei einem expliziten Aufruf von DllImportAttribute angegeben werden können, nicht festlegen müssen.  
  
 Visual C\+\+ bietet zwei Möglichkeiten für die Interoperation von verwalteten und nicht verwalteten Funktionen:  
  
-   [Verwenden von explizitem PInvoke in C\+\+ \(DllImport\-Attribut\)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)  
  
 Explizites PInvoke wird von .NET Framework unterstützt und ist in den meisten .NET\-Sprachen verfügbar.  Doch wie der Name schon sagt, ist C\+\+\-Interop Visual C\+\+\-spezifisch.  
  
## C\+\+ Interop  
 C\+\+\-Interop wird gegenüber explizitem PInvoke empfohlen, da es bessere Typsicherheit bietet, normalerweise einfacher zu implementieren ist, sich bei Änderungen der nicht verwalteten API leichter handhaben lässt und Leistungsverbesserungen erlaubt, die mit explizitem PInvoke nicht möglich sind.  C\+\+\-Interop kann jedoch nicht verwendet werden, wenn der nicht verwaltete Quellcode nicht verfügbar ist oder die Kompilierung mit **\/clr:safe** durchgeführt wird \(weitere Informationen finden Sie unter [Reiner und überprüfbarer Code](../dotnet/pure-and-verifiable-code-cpp-cli.md)\).  
  
## C\+\+\-COM\-Interop  
 Die von Visual C\+\+ unterstützten Interoperabilitätsfunktionen bieten einen besonderen Vorteil gegenüber anderen .NET\-Sprachen, wenn es um die Interoperation mit COM\-Komponenten geht.  Da es nicht durch die Einschränkungen der .NET Framework\-[Tlbimp.exe \(Type Library Importer\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md) beschränkt ist, z. B. durch beschränkte Unterstützung für Datentypen und das obligatorische Verfügbarmachen jedes einzelnen Members der einzelnen COM\-Schnittstellen, kann mit C\+\+\-Interop beliebig auf COM\-Komponenten zugegriffen werden, ohne dass separate Interop\-Assemblys erforderlich sind.  Weitere Informationen finden Sie unter [Using COM from .NET](assetId:///03976661-6278-4227-a6c1-3b3315502c15).  
  
## Blitfähige Typen  
 Bei nicht verwalteten APIs, die einfache, systeminterne Typen verwenden \(siehe [Blittable and Non\-Blittable Types](../Topic/Blittable%20and%20Non-Blittable%20Types.md)\), ist keine spezielle Codierung erforderlich, da diese Datentypen im Arbeitsspeicher auf dieselbe Weise dargestellt werden, während komplexere Datentypen ein explizites Datenmarshalling erfordern.  Ein Beispiel finden Sie unter [Gewusst wie: Aufrufen von systemeigenen DLLs in verwaltetem Code mithilfe von PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md).  
  
## Beispiel  
  
```  
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
  
  **Signalton starten**  
**Fertig**   
## In diesem Abschnitt  
  
-   [Gewusst wie: Marshallen von ANSI\-Zeichenfolgen mit C\+\+\-Interop](../dotnet/how-to-marshal-ansi-strings-using-cpp-interop.md)  
  
-   [Gewusst wie: Marshallen von Unicode\-Zeichenfolgen mit C\+\+\-Interop](../dotnet/how-to-marshal-unicode-strings-using-cpp-interop.md)  
  
-   [Gewusst wie: Marshallen von COM\-Zeichenfolgen mit C\+\+\-Interop](../dotnet/how-to-marshal-com-strings-using-cpp-interop.md)  
  
-   [Gewusst wie: Marshallen von Strukturen mit C\+\+\-Interop](../dotnet/how-to-marshal-structures-using-cpp-interop.md)  
  
-   [Gewusst wie: Marshallen von Arrays mit C\+\+\-Interop](../dotnet/how-to-marshal-arrays-using-cpp-interop.md)  
  
-   [Gewusst wie: Marshallen von Rückrufen und Delegaten mit C\+\+\-Interop](../dotnet/how-to-marshal-callbacks-and-delegates-by-using-cpp-interop.md)  
  
-   [Gewusst wie: Marshallen von eingebetteten Zeigern mit C\+\+\-Interop](../dotnet/how-to-marshal-embedded-pointers-using-cpp-interop.md)  
  
-   [Gewusst wie: Zugriff auf Zeichen in einem System::String](../dotnet/how-to-access-characters-in-a-system-string.md)  
  
-   [Gewusst wie: Umwandeln von char \* String nach System::Byte Array](../dotnet/how-to-convert-char-star-string-to-system-byte-array.md)  
  
-   [Gewusst wie: Umwandeln von System::String nach wchar\_t\* oder char\*](../dotnet/how-to-convert-system-string-to-wchar-t-star-or-char-star.md)  
  
-   [Gewusst wie: Konvertieren von System::String zu Standardzeichenfolge](../dotnet/how-to-convert-system-string-to-standard-string.md)  
  
-   [Gewusst wie: Konvertieren einer Standardzeichenfolge nach System::String](../dotnet/how-to-convert-standard-string-to-system-string.md)  
  
-   [Gewusst wie: Abrufen eines Zeigers auf ein Byte\-Array](../dotnet/how-to-obtain-a-pointer-to-byte-array.md)  
  
-   [Gewusst wie: Laden von nicht verwalteten Ressourcen in ein Byte\-Array](../dotnet/how-to-load-unmanaged-resources-into-a-byte-array.md)  
  
-   [Gewusst wie: Ändern der Verweisklasse in einer systemeigenen Funktion](../dotnet/how-to-modify-reference-class-in-a-native-function.md)  
  
-   [Gewusst wie: Ermitteln, ob ein Bild systemeigen oder CLR ist](../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)  
  
-   [Gewusst wie: Hinzufügen einer systemeigenen DLL zum globalen Assemblycache](../dotnet/how-to-add-native-dll-to-global-assembly-cache.md)  
  
-   [Gewusst wie: Verweis auf Werttyp in systemeigenem Typ](../dotnet/how-to-hold-reference-to-value-type-in-native-type.md)  
  
-   [Gewusst wie: Objektverweis in nicht verwaltetem Arbeitsspeicher](../dotnet/how-to-hold-object-reference-in-unmanaged-memory.md)  
  
-   [Gewusst wie: Erkennen der \/clr\-Kompilierung](../dotnet/how-to-detect-clr-compilation.md)  
  
-   [Gewusst wie: Konvertieren zwischen System::Guid und \_GUID](../dotnet/how-to-convert-between-system-guid-and-guid.md)  
  
-   [Gewusst wie: Angeben eines out\-Parameters](../dotnet/how-to-specify-an-out-parameter.md)  
  
-   [Gewusst wie: Verwenden eines systemeigenen Typs in einer \/clr\-Kompilierung](../dotnet/how-to-use-a-native-type-in-a-clr-compilation.md)  
  
-   [Gewusst wie: Deklarieren von Handles in systemeigenen Typen](../dotnet/how-to-declare-handles-in-native-types.md)  
  
-   [Gewusst wie: Kapseln einer systemeigenen Klasse zur Verwendung in C\#](../dotnet/how-to-wrap-native-class-for-use-by-csharp.md)  
  
 Informationen über die Verwendung von Delegaten in einem Interop\-Szenario finden Sie unter [delegate](../windows/delegate-cpp-component-extensions.md).  
  
## Siehe auch  
 [Aufrufen systemeigener Funktionen aus verwaltetem Code](../dotnet/calling-native-functions-from-managed-code.md)