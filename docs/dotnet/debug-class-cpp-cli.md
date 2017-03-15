---
title: "Debug-Klasse (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
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
  - ".NET Framework [C++], Debug-Klasse"
  - "Debug-Klasse"
  - "Trace-Klasse, Visual C++"
ms.assetid: 076bd528-1b6f-4e8a-a372-eb5849cf969a
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Debug-Klasse (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei Verwendung von <xref:System.Diagnostics.Debug> in einer Visual C\+\+\-Anwendung gibt es zwischen einem Debugbuild und einem Releasebuild keinen Unterschied im Verhalten.  
  
## Hinweise  
 Das Verhalten von <xref:System.Diagnostics.Trace> ist mit dem Verhalten der Debug\-Klasse identisch, hängt jedoch davon ab, ob das Symbol TRACE definiert wurde.  Dies bedeutet, dass Sie für Trace\-bezogenen Code stets `#ifdef` verwenden müssen, um das Debugverhalten in einem Releasebuild zu verhindern.  
  
## Beispiel  
  
### **Beschreibung**  
 Im folgenden Beispiel werden immer die Ausgabeanweisungen ausgeführt, unabhängig davon, ob Sie mit **\/DDEBUG** oder **\/DTRACE** kompilieren.  
  
### Code  
  
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
  
### Ausgabe  
  
```  
    Entering Main  
Hello World.  
    Exiting Main  
test  
```  
  
## Beispiel  
  
### **Beschreibung**  
 Um das erwartete Verhalten zu erzielen \(d. h. keine Ausgabe von "test" im Releasebuild\), müssen Sie die `#ifdef`\-Direktive und die `#endif`\-Direktive verwenden.  Im Folgenden finden Sie zur Veranschaulichung dieser Korrektur das oben stehende Codebeispiel mit den entsprechenden Änderungen:  
  
### Code  
  
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
  
## Siehe auch  
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)