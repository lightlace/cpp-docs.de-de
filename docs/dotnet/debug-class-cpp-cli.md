---
title: Debug-Klasse (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Trace class, Visual C++
- .NET Framework [C++], Debug class
- Debug class
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: eecda10f2fd88b902a54fe9f4dc4de8edc4bc1b0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413561"
---
# <a name="debug-class-ccli"></a>Debug-Klasse (C++/CLI)

Bei Verwendung <xref:System.Diagnostics.Debug> in Visual C++-Anwendung, das Verhalten ändert nicht zwischen einem Debugbuild und ein Releasebuild erstellt.

## <a name="remarks"></a>Hinweise

Das Verhalten für <xref:System.Diagnostics.Trace> entspricht das Verhalten für die Debug-Klasse, aber richtet sich nach dem Symbol TRACE definiert. Dies bedeutet, dass Sie müssen `#ifdef` jeder ablaufverfolgungsbezogenen-Code für das Debugverhalten in einem Releasebuild zu verhindern.

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Im folgende Beispiel führt immer die ausgabeanweisungen, unabhängig davon, ob Sie die Kompilierung mit **DDEBUG** oder **/DTRACE**.

### <a name="code"></a>Code

```cpp
// mcpp_debug_class.cpp
// compile with: /clr
#using <system.dll>
using namespace System::Diagnostics;
using namespace System;

int main() {
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );
   Trace::AutoFlush = true;
   Trace::Indent();
   Trace::WriteLine( "Entering Main" );
   Console::WriteLine( "Hello World." );
   Trace::WriteLine( "Exiting Main" );
   Trace::Unindent();

   Debug::WriteLine("test");
}
```

### <a name="output"></a>Ausgabe

```Output
    Entering Main
Hello World.
    Exiting Main
test
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Um das erwartete Verhalten zu erhalten (d. h. keine Ausgabe von "test" gedruckt, für einen Releasebuild), müssen Sie verwenden die `#ifdef` und `#endif` Anweisungen. Im vorhergehenden Beispielcode gezeigt wird unten geändert, um diese Lösung zu veranschaulichen:

### <a name="code"></a>Code

```cpp
// mcpp_debug_class2.cpp
// compile with: /clr
#using <system.dll>
using namespace System::Diagnostics;
using namespace System;

int main() {
   Trace::Listeners->Add( gcnew TextWriterTraceListener( Console::Out ) );
   Trace::AutoFlush = true;
   Trace::Indent();

#ifdef TRACE   // checks for a debug build
   Trace::WriteLine( "Entering Main" );
   Console::WriteLine( "Hello World." );
   Trace::WriteLine( "Exiting Main" );
#endif
   Trace::Unindent();

#ifdef DEBUG   // checks for a debug build
   Debug::WriteLine("test");
#endif   //ends the conditional block
}
```

## <a name="see-also"></a>Siehe auch

[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)