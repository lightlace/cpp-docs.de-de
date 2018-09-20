---
title: 'Vorgehensweise: Marshallen von Zeichenfolgen mit PInvoke | Microsoft-Dokumentation'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], strings
- marshaling [C++], strings
- data marshaling [C++], strings
- platform invoke [C++], strings
ms.assetid: bcc75733-7337-4d9b-b1e9-b95a98256088
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d917228b1972715c291d84625cc684fc9de5b998
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396375"
---
# <a name="how-to-marshal-strings-using-pinvoke"></a>Gewusst wie: Marshallen von Zeichenfolgen mit PInvoke

In diesem Thema wird erläutert, wie native Funktionen, akzeptieren die Zeichenfolgen im C-Stil können aufgerufen werden, mithilfe der CLR-Zeichenfolge, mit Unterstützung für .NET Framework Plattformaufrufe System:: String zu geben. Visual C++-Programmierer werden empfohlen, stattdessen die C++-Interop-Funktionen (wenn möglich), da der P/Invoke bietet wenig Fehler während der Kompilierung, berichterstellung, ist nicht typsicher, und kann einfacher zu implementieren. Wenn die nicht verwaltete API als DLL verpackt wird und der Quellcode nicht verfügbar ist, anschließend P/Invoke ist die einzige Option, aber andernfalls [mithilfe C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md).

Verwaltete und nicht verwaltete Zeichenfolgen sind anders als im Arbeitsspeicher angeordnet, also die Übergabe von Zeichenfolgen aus verwaltetem zu nicht verwalteten Funktionen erfordert die <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut, um den Compiler anzuweisen, die erforderliche Konvertierung Mechanismen für das Marshalling von Daten der Zeichenfolge einfügen ordnungsgemäß und sicher.

Wie bei Funktionen, die nur systeminterne Datentypen verwenden <xref:System.Runtime.InteropServices.DllImportAttribute> verwendet, um verwaltete Einstiegspunkte in die systemeigenen Funktionen, aber – für die Übergabe von Zeichenfolgen – anstelle von definieren übernehmen die Zeichenfolgen im C-Stil, ein Handle für diese Einstiegspunkte deklarieren die <xref:System.String> Typ Stattdessen verwendet werden können. Dadurch wird den Compiler Code einfügen, die die erforderliche Konvertierung ausführt. Für jedes Funktionsargument in eine nicht verwaltete Funktion, die eine Zeichenfolge akzeptiert die <xref:System.Runtime.InteropServices.MarshalAsAttribute> Attribut sollte verwendet werden, um anzugeben, dass das String-Objekt an die systemeigene Funktion als Zeichenfolge im C-Stil gemarshallt werden sollen.

## <a name="example"></a>Beispiel

Der folgende Code besteht aus einem verwalteten und ein verwaltetes Modul. Das nicht verwaltete Modul handelt es sich um eine DLL, die eine Funktion namens TakesAString, die eine C-Stil ANSI-Zeichenfolge in Form von Char * akzeptiert definiert. Das verwaltete Modul ist eine befehlszeilenanwendung, die die Funktion TakesAString importiert, aber definiert es als das Erstellen einer verwalteten System.String "statt" Char\*. Die <xref:System.Runtime.InteropServices.MarshalAsAttribute> -Attribut wird verwendet, um anzugeben, wie die verwaltete Zeichenfolge gemarshallt werden sollen, wenn TakesAString aufgerufen wird.

```
// TraditionalDll2.cpp
// compile with: /LD /EHsc
#include <windows.h>
#include <stdio.h>
#include <iostream>

using namespace std;

#define TRADITIONALDLL_EXPORTS
#ifdef TRADITIONALDLL_EXPORTS
#define TRADITIONALDLL_API __declspec(dllexport)
#else
#define TRADITIONALDLL_API __declspec(dllimport)
#endif

extern "C" {
   TRADITIONALDLL_API void TakesAString(char*);
}

void TakesAString(char* p) {
   printf_s("[unmanaged] %s\n", p);
}
```

```
// MarshalString.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value struct TraditionalDLL
{
   [DllImport("TraditionalDLL2.dll")]
      static public void
      TakesAString([MarshalAs(UnmanagedType::LPStr)]String^);
};

int main() {
   String^ s = gcnew String("sample string");
    Console::WriteLine("[managed] passing managed string to unmanaged function...");
   TraditionalDLL::TakesAString(s);
   Console::WriteLine("[managed] {0}", s);
}
```

Diese Methode bewirkt, dass eine Kopie der Zeichenfolge, die auf dem nicht verwalteten Heap erstellt werden, sodass Änderungen an der Zeichenfolge durch die systemeigene Funktion in der verwalteten Kopie der Zeichenfolge nicht widergespiegelt werden.

Beachten Sie, dass kein Teil der DLL verfügbar, auf den verwalteten Code über die herkömmliche gemacht wird #include-Anweisung. In der Tat ist die DLL nur zur Laufzeit zugegriffen, damit Probleme mit Funktionen mit importiert `DllImport` zum Zeitpunkt der Kompilierung nicht erkannt.

## <a name="see-also"></a>Siehe auch

[Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)