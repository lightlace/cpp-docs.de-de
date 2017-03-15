---
title: "Gewusst wie: Auflisten von Datentypen in Assemblys mit Reflektion (C++/CLI)"
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
  - "Assemblys [C++]"
  - "Assemblys [C++], Auflisten von Datentypen in"
  - "Datentypen [C++], Auflisten"
  - "Öffentliche Member [C++]"
  - "Öffentliche Typen [C++]"
  - "Reflektion [C++], Externe Assemblys"
ms.assetid: c3578e6d-bb99-4599-80e1-ab795305f878
caps.latest.revision: 15
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Auflisten von Datentypen in Assemblys mit Reflektion (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Code wird die Enumeration von öffentlichen Typen und Membern mit <xref:System.Reflection> dargestellt.  
  
 Wenn der Name eines Assemblys im lokalen Verzeichnis oder im GAC vorhanden ist, wird mit dem folgenden Code versucht, die Assembly zu öffnen und Beschreibungen abzurufen.  Wenn der Vorgang erfolgreich abgeschlossen wird, wird jeder Typ mit seinen öffentlichen Membern angezeigt.  
  
 Beachten Sie, dass mit <xref:System.Reflection.Assembly.Load*?displayProperty=fullName> keine Dateierweiterung verwendet werden darf.  Aus diesem Grund schlägt die Verwendung von '"mscorlib.dll" als Befehlszeilenargument fehl, während "mscorlib" dazu führt, dass die .NET Framework\-Typen angezeigt werden.  Wenn kein Assemblyname verfügbar ist, werden vom Code die Typen in der aktuellen Assembly \(der von diesem Code erstellten EXE\) erkannt und ausgegeben.  
  
## Beispiel  
  
```  
// self_reflection.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
using namespace System::Collections;  
  
public ref class ExampleType {  
public:  
   ExampleType() {}  
   void Func() {}  
};  
  
int main() {  
   String^ delimStr = " ";  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ args = Environment::CommandLine->Split( delimiter );  
  
// replace "self_reflection.exe" with an assembly from either the local  
// directory or the GAC  
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");  
   Console::WriteLine(a);  
  
   int count = 0;  
   array<Type^>^ types = a->GetTypes();  
   IEnumerator^ typeIter = types->GetEnumerator();  
  
   while ( typeIter->MoveNext() ) {  
      Type^ t = dynamic_cast<Type^>(typeIter->Current);  
      Console::WriteLine("   {0}", t->ToString());  
  
      array<MemberInfo^>^ members = t->GetMembers();  
      IEnumerator^ memberIter = members->GetEnumerator();  
      while ( memberIter->MoveNext() ) {  
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);  
         Console::Write("      {0}", mi->ToString( ) );  
         if (mi->MemberType == MemberTypes::Constructor)  
            Console::Write("   (constructor)");  
  
         Console::WriteLine();  
      }  
      count++;  
   }  
   Console::WriteLine("{0} types found", count);  
}  
```  
  
## Siehe auch  
 [Reflektion](../dotnet/reflection-cpp-cli.md)