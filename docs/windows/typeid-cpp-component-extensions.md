---
title: "typeid (Komponentenerweiterungen f&#252;r C++)"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "typeid-Schlüsselwort [C++]"
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
caps.latest.revision: 35
caps.handback.revision: "33"
ms.author: "mblome"
manager: "ghogen"
---
# typeid (Komponentenerweiterungen f&#252;r C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft einen Wert ab, der den Typ eines Objekts angibt.  
  
> [!WARNING]
>  Dieses Thema behandelt die C\+\+\-Komponentenerweiterungsversion von "typeid".  Die ISO C\+\+\-Version dieses Schlüsselworts finden Sie unter [typeid\-Operator](../cpp/typeid-operator.md).  
  
## Alle Laufzeiten  
  
### Syntax  
  
```cpp  
  
T::typeid  
```  
  
### Parameter  
 *T*  
 Ein Typname.  
  
## Windows\-Runtime  
  
### Syntax  
  
```cpp  
Platform::Type^ type = T::typeid;  
```  
  
### Parameter  
 `T`  
 Ein Typname.  
  
### Hinweise  
 In [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] gibt "typeid" einen [Platform::Type](../Topic/Platform::Type%20Class.md) zurück, der aus Laufzeittypinformationen erstellt wird.  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Syntax**  
  
```  
  
type::typeid  
```  
  
 **Parameter**  
  
 *type*  
 Der Name eines Typs \(abstrakter Deklarator\), für den das System::Type\-Objekt gelten soll.  
  
 **Hinweise**  
  
 `typeid` wird verwendet, um <xref:System.Type> für einen Typ zur Kompilierzeit abzurufen.  
  
 `typeid` entspricht dem Abruf von System::Type mithilfe von <xref:System.Type.GetType*> oder <xref:System.Object.GetType*> für einen Typ zur Laufzeit.  Jedoch akzeptiert typeid nur einen Typnamen als Parameter.  Wenn Sie eine Instanz eines Typs verwenden möchten, um den System::Type\-Namen abzurufen, verwenden Sie GetType.  
  
 `typeid` muss in der Lage sein, einen Typnamen \(type\) zur Kompilierungszeit auszuwerten, während GetType den Typ auswertet, der zur Laufzeit zurückgeben wird.  
  
 `typeid` kann einen systemeigenen Typenamen\- oder Common Language Runtime\-Alias für den systemeigenen Typnamen annehmen. Unter [.NET Framework\-Entsprechungen der systemeigenen Typen in C\+\+](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md) finden Sie weitere Informationen hierzu.  
  
 `typeid` funktioniert auch mit systemeigenen Typen, obwohl noch ein System::Type zurückgegeben wird.  Um eine type\_info\-Struktur abzurufen, verwenden Sie [typeid\-Operator](../cpp/typeid-operator.md).  
  
 `typeid` folgt in der vorherigen **\/clr**\-Syntax auf [\_\_typeof](../misc/typeof.md).  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel wird das typeid\-Schlüsselwort mit dem GetType\(\)\-Member verglichen.  
  
```  
// keyword__typeid.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   Type ^ pType = pG->GetType();  
   Type ^ pType2 = G::typeid;  
  
   if (pType == pType2)  
      Console::WriteLine("typeid and GetType returned the same System::Type");  
   Console::WriteLine(G::typeid);  
  
   typedef float* FloatPtr;  
   Console::WriteLine(FloatPtr::typeid);  
}  
```  
  
 **Ausgabe**  
  
  **"typeid" und "GetType" haben den gleichen "System::Type" zurückgegeben.**  
**G**  
 **System.Single\*** **Beispiel**  
  
 Das folgende Beispiel zeigt, dass eine Variable des Typs System::Type verwendet werden kann, um die Attribute für einen Typ abzurufen.  Außerdem wird veranschaulicht, dass Sie für einige Typen eine Typdefinition erstellen müssen, um `typeid` zu verwenden.  
  
```  
// keyword__typeid_2.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Security;  
using namespace System::Security::Permissions;  
  
typedef int ^ handle_to_int;  
typedef int * pointer_to_int;  
  
public ref class MyClass {};  
  
class MyClass2 {};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass {  
public:  
   AtClass(Type ^) {  
      Console::WriteLine("in AtClass Type ^ constructor");  
   }  
};  
  
[attribute(AttributeTargets::All)]  
ref class AtClass2 {  
public:  
   AtClass2() {  
      Console::WriteLine("in AtClass2 constructor");  
   }  
};  
  
// Apply the AtClass and AtClass2 attributes to class B  
[AtClass(MyClass::typeid), AtClass2]     
[AttributeUsage(AttributeTargets::All)]  
ref class B : Attribute {};  
  
int main() {  
   Type ^ MyType = B::typeid;  
  
   Console::WriteLine(MyType->IsClass);  
  
   array<Object^>^ MyArray = MyType -> GetCustomAttributes(true);  
   for (int i = 0 ; i < MyArray->Length ; i++ )  
      Console::WriteLine(MyArray[i]);  
  
   if (int::typeid != pointer_to_int::typeid)  
      Console::WriteLine("int::typeid != pointer_to_int::typeid, as expected");  
  
   if (int::typeid == handle_to_int::typeid)  
      Console::WriteLine("int::typeid == handle_to_int::typeid, as expected");  
}  
```  
  
 **Ausgabe**  
  
  **True**  
 **im AtClass2\-Konstructor**  
 **im AtClass Type ^\-Konstruktor**  
 **AtClass2**  
 **System.AttributeUsageAttribute**  
 **AtClass**  
 **int::typeid\! \= pointer\_to\_int::typeid, wie erwartet**  
 **int::typeid \=\= handle\_to\_int::typeid, as expected**   
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)