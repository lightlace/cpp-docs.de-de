---
title: 'Vorgehensweise: Auflisten von Datentypen mithilfe von Reflektion (C + c++ / CLI) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: c3578e6d-bb99-4599-80e1-ab795305f878
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d89324e49cb08014892d08a046221b9a1e28d2e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-enumerate-data-types-in-assemblies-using-reflection-ccli"></a>Gewusst wie: Auflisten von Datentypen in Assemblys mit Reflektion (C++/CLI)
Der folgende Code veranschaulicht die Enumeration von öffentlichen Typen und Member, die mit <xref:System.Reflection>.  
  
 Erhält den Namen einer Assembly im lokalen Verzeichnis oder im GAC, versucht, der folgenden Code öffnen Sie die Assembly und Beschreibungen abgerufen. Im Erfolgsfall wird jeder Typ mit die öffentlichen Member angezeigt.  
  
 Beachten Sie, dass <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> erfordert, dass keine Dateierweiterung verwendet wird. Aus diesem Grund wird mithilfe von "mscorlib.dll" als Befehlszeilenargument ausfallen, obwohl nur "Mscorlib" mit der Anzeige von .NET Framework-Typen führt. Wenn kein Assemblyname bereitgestellt wird, der Code erkennt, und melden die Typen in der gleichen Assembly (die EXE-Datei von diesem Code erstellten).  
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Reflexion (C++/CLI)](../dotnet/reflection-cpp-cli.md)