---
title: Debug-Klasse (C + c++ / CLI) | Microsoft Docs
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
ms.openlocfilehash: fddf192b21b878c82ca663da657c55e32fd9173d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="debug-class-ccli"></a>Debug-Klasse (C++/CLI)
Bei Verwendung <xref:System.Diagnostics.Debug> in einer Visual C++-Anwendung, das Verhalten ändert sich nicht zwischen einem Debugbuild und ein Releasebuild erstellt werden.  
  
## <a name="remarks"></a>Hinweise  
 Das Verhalten für <xref:System.Diagnostics.Trace> entspricht das Verhalten für die Debug-Klasse, aber ist abhängig von das Symbol TRACE definiert wird. Dies bedeutet, dass Sie müssen `#ifdef` ablaufverfolgungsbezogenen Code Debugverhalten in einem Releasebuild zu verhindern.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgende Beispiel führt immer die Ausgabe-Anweisungen, unabhängig davon, ob beim Kompilieren mit **DDEBUG** oder **/DTRACE**.  
  
### <a name="code"></a>Code  
  
```  
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
  
```  
    Entering Main  
Hello World.  
    Exiting Main  
test  
```  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Um das erwartete Verhalten zu erzielen (d. h. keine Ausgabe von "test" gedruckt, für einen Releasebuild), müssen Sie verwenden die `#ifdef` und `#endif` Direktiven. Im vorhergehenden Beispielcode gezeigt wird unten veranschaulicht diesen Fix geändert:  
  
### <a name="code"></a>Code  
  
```  
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