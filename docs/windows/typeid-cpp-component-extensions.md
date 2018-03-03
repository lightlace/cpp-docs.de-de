---
title: "Typeid (Komponentenerweiterungen für C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- typeid keyword [C++]
ms.assetid: e9706cae-e7c4-4d6d-b474-646d73df3e70
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 20a3b1153bbb8a8502a54aa74998817abf191860
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="typeid--c-component-extensions"></a>typeid (Komponentenerweiterungen für C++)
Ruft einen Wert ab, der den Typ eines Objekts angibt.  
  
> [!WARNING]
>  Dieses Thema behandelt die C++-Komponentenerweiterungsversion von "typeid". Die ISO C++-Version dieses Schlüsselwort, finden Sie unter [Typeid-Operator](../cpp/typeid-operator.md).  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
T::typeid  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Ein Typname.  
  
## <a name="windows-runtime"></a>Windows-Runtime  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
Platform::Type^ type = T::typeid;  
```  
  
### <a name="parameters"></a>Parameter  
 `T`  
 Ein Typname.  
  
### <a name="remarks"></a>Hinweise  
 In C + c++ / CX können Typeid gibt eine [Platform:: Type](../cppcx/platform-type-class.md) , der aus Laufzeittypinformationen erstellt wird.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Syntax**  
  
```  
  
type::typeid  
```  
  
 **Parameter**  
  
 *Typ*  
 Der Name eines Typs (abstrakter Deklarator), für den das System::Type-Objekt gelten soll.  
  
 **Hinweise**  
  
 `typeid` wird verwendet, um <xref:System.Type> für einen Typ zur Kompilierzeit abzurufen.  
  
 `typeid` entspricht dem Abruf von System::Type mithilfe von <xref:System.Type.GetType%2A> oder <xref:System.Object.GetType%2A> für einen Typ zur Laufzeit. Jedoch akzeptiert typeid nur einen Typnamen als Parameter.  Wenn Sie eine Instanz eines Typs verwenden möchten, um den System::Type-Namen abzurufen, verwenden Sie GetType.  
  
 `typeid` muss in der Lage sein, einen Typnamen (type) zur Kompilierungszeit auszuwerten, während GetType den Typ auswertet, der zur Laufzeit zurückgeben wird.  
  
 `typeid`Hierbei kann es sich um einen systemeigenen Typ-Namen oder die common Language Runtime-Alias für den systemeigenen Typ dauern; finden Sie unter [.NET Framework-Entsprechungen in systemeigenen C++-Typen (C + c++ / CLI)](../dotnet/dotnet-framework-equivalents-to-cpp-native-types-cpp-cli.md) für Weitere Informationen.  
  
 `typeid` funktioniert auch mit systemeigenen Typen, obwohl noch ein System::Type zurückgegeben wird.  Verwenden Sie zum Abrufen einer Struktur Type_info [Typeid-Operator](../cpp/typeid-operator.md).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel wird das typeid-Schlüsselwort mit dem GetType()-Member verglichen.  
  
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
  
```Output  
typeid and GetType returned the same System::Type  
G  
  
System.Single*  
  
```  
  
 **Beispiel**  
  
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
  
```Output  
True  
  
in AtClass2 constructor  
  
in AtClass Type ^ constructor  
  
AtClass2  
  
System.AttributeUsageAttribute  
  
AtClass  
  
int::typeid != pointer_to_int::typeid, as expected  
  
int::typeid == handle_to_int::typeid, as expected  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)