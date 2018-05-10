---
title: Safe_cast (Komponentenerweiterungen für C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c889d39df4d900beba5c9b41015e62293fdbbcde
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="safecast-c-component-extensions"></a>safe_cast (Komponentenerweiterungen für C++)
Der `safe_cast`-Vorgang gibt im Erfolgsfall den angegebenen Ausdruck als den angegebenen Typ zurück, andernfalls wird `InvalidCastException` ausgegeben.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 (Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.)  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>Parameter  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 `safe_cast` ermöglicht Ihnen, den Typ des angegebenen Ausdrucks zu ändern. In Situationen, in denen Sie mit Sicherheit erwarten, dass eine Variable oder ein Parameter zu einem bestimmten Typ konvertiert werden kann, können Sie „safe_cast“ ohne einen „try-catch“-Block verwenden, um während der Entwicklung Programmierfehler zu ermitteln. Weitere Informationen finden Sie unter [umwandeln (C + c++ / CX)](http://msdn.microsoft.com/library/windows/apps/hh755802.aspx).  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
[default]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>Parameter  
 *Typ-id*  
 Der zu konvertierende Typ *Ausdruck* an. Ein Handle zu einem Verweis- oder Werttyp, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis- oder Werttyp.  
  
 *Ausdruck*  
 Ein Ausdruck, der als ein Handle zu einem Verweis oder Werttyp ausgewertet wird, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis- oder Werttyp.  
  
### <a name="remarks"></a>Hinweise  
 `safe_cast` löst `InvalidCastException` Wenn dies nicht *Ausdruck* in den vom angegebenen Typ *Typ-Id*. Zum Abfangen von `InvalidCastException`, geben Sie die [/EH (Ausnahmebehandlungsmodell)](../build/reference/eh-exception-handling-model.md) (Compileroption), und verwenden Sie eine Try/Catch-Anweisung.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie `safe_cast` mit der Windows-Runtime.  
  
```cpp#  
// safe_cast_ZW.cpp  
// compile with: /ZW /EHsc  
  
using namespace default;  
using namespace Platform;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main(Array<String^>^ args) {  
   I1^ i1 = ref new X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.  
   }   
   catch(InvalidCastException^ ic) {  
     wprintf(L"Caught expected exception: %s\n", ic->Message);  
   }  
}  
```  
  
 **Ausgabe**  
  
```Output  
Caught expected exception: InvalidCastException  
```  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 `safe_cast` ermöglicht Ihnen, den Ausdruckstyp zu ändern und einen überprüfbaren MISL-Code zu generieren.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
[cli]:: safe_cast<  
type-id  
>(  
expression  
)  
  
```  
  
### <a name="parameters"></a>Parameter  
 *Typ-id*  
 Ein Handle zu einem Verweis- oder Werttyp, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis- oder Werttyp.  
  
 *Ausdruck*  
 Ein Ausdruck, der als ein Handle zu einem Verweis oder Werttyp ausgewertet wird, ein Werttyp oder ein Nachverfolgungsverweis auf einen Verweis- oder Werttyp.  
  
### <a name="remarks"></a>Hinweise  
 Der Ausdruck `safe_cast<` *Typ-Id*`>(`*Ausdruck* `)` konvertiert den operandenausdruck zu einem Objekt vom Typ-Id-Typ.  
  
 Der Compiler akzeptiert eine [Static_cast](../cpp/static-cast-operator.md) in den meisten stellen, an denen er akzeptiert eine `safe_cast`.  Bei `safe_cast` ist das Generieren von überprüfbarer MSIL jedoch garantiert, wobei `static_cast` eine nicht überprüfbare MSIL generieren könnte.  Finden Sie unter [reiner und überprüfbarer Code (C + c++ / CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) und [Peverify.exe (PEVerify-Tool)](/dotnet/framework/tools/peverify-exe-peverify-tool) für Weitere Informationen zu überprüfbaren Code.  
  
 Analog zu `static_cast` ruft `safe_cast` benutzerdefinierte Konvertierungen auf.  
  
 Weitere Informationen zu Umwandlungen finden Sie unter [Umwandlungsoperatoren](../cpp/casting-operators.md).  
  
 `safe_cast` gilt nicht für eine **Const_cast** (umwandeln **const**).  
  
 `safe_cast` befindet sich im cli-Namespace.  Finden Sie unter [Plattform, Default- und Cli-Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) für Weitere Informationen.  
  
 Weitere Informationen zu **safe_cast**t, finden Sie unter:  
  
-   [C-stilartige Umwandlungen mit/CLR (C + c++ / CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)  
  
-   [Vorgehensweise: Verwenden von safe_cast in C++/CLI](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)  

### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Ein Beispiel, in dem der Compiler `static_cast` nicht akzeptiert, `safe_cast` jedoch akzeptiert, sind Umwandlungen zwischen nicht verknüpften Schnittstellentypen.  Mit `safe_cast` stellt der Compiler keinen Konvertierungsfehler aus und führt zur Laufzeit eine Überprüfung aus, um zu ermitteln, ob die Umwandlung möglich ist.  
  
```cpp  
// safe_cast.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I1 {};  
interface class I2 {};  
interface class I3 {};  
  
ref class X : public I1, public I2 {};  
  
int main() {  
   I1^ i1 = gcnew X;  
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X  
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead  
   try {  
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type  
   }   
   catch(InvalidCastException^) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 **Ausgabe**  
  
```Output  
Caught expected exception  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)