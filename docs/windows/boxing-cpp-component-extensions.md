---
title: Boxing (C++ / CLI und C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- boxing, C++
ms.assetid: b5fd2c98-c578-4f83-8257-6dd663478665
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b11ac2f6b640e42c14522b45fe0c3da89036ae24
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328011"
---
# <a name="boxing--ccli-and-ccx"></a>Boxing (C++ / CLI und C++ / CX)

Die Konvertierung von Werttypen in Objekte heißt *Boxing*, und die Konvertierung von Objekten in Werttypen heißt *unboxing*.

## <a name="all-runtimes"></a>Alle Laufzeiten

(Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.)

## <a name="windows-runtime"></a>Windows-Runtime

C++ / CX unterstützt eine Kurzsyntax für Boxing-Werttypen und unboxing-Verweistypen. Ein Werttyp mittels Boxing konvertiert, wenn sie einer Variable des Typs `Object` zugewiesen wird. Eine `Object`-Variable wird mittels Unboxing konvertiert, wenn sie einer Werttypvariable zugeordnet ist und der Unboxing-Typ in Klammern angegeben wird; d. h., wenn die Objektvariable in einen Werttyp umgewandelt wird.

```cpp
  Platform::Object^
  object_variable  = value_variable;
value_variable = (value_type) object_variable;
```

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

### <a name="examples"></a>Beispiele

Im folgenden Beispiel wird ein `DateTime`-Wert mittels Boxing und Unboxing konvertiert. Zunächst das Beispiel ruft eine `DateTime` -Wert, der der aktuelle Datum und Uhrzeit darstellt, und weist sie einer `DateTime` Variable. Die `DateTime` geschachtelt ist, durch die Zuweisung zu einem `Object` Variable. Schließlich der geschachtelte Wert wird mittels Unboxing zurückkonvertiert durch Zuweisen einer anderen `DateTime` Variable.

Um das Beispiel zu testen, erstellen eine `BlankApplication` Projekt, ersetzen Sie die `BlankPage::OnNavigatedTo()` -Methode, und geben Sie dann Haltepunkte auf der schließenden geschweiften Klammer und die Zuweisung zur Variable `str1`. Überprüfen Sie im Beispiel wird die schließende Klammer erreicht, `str1`.

```cpp
void BlankPage::OnNavigatedTo(NavigationEventArgs^ e)  
{
    using namespace Windows::Globalization::DateTimeFormatting;

    Windows::Foundation::DateTime dt, dtAnother;
    Platform::Object^ obj1;

    Windows::Globalization::Calendar^ c =
        ref new Windows::Globalization::Calendar;
    c->SetToNow();
    dt = c->GetDateTime();
    auto dtf = ref new DateTimeFormatter(
                           YearFormat::Full,
                           MonthFormat::Numeric,
                           DayFormat::Default,
                           DayOfWeekFormat::None);
    String^ str1 = dtf->Format(dt);
    OutputDebugString(str1->Data());
    OutputDebugString(L"\r\n");

    // Box the value type and assign to a reference type.
    obj1 = dt;
    // Unbox the reference type and assign to a value type.
    dtAnother = (Windows::Foundation::DateTime) obj1;

    // Format the DateTime for display.
    String^ str2 = dtf->Format(dtAnother);
    OutputDebugString(str2->Data());
}
```

Weitere Informationen finden Sie unter [Boxing (C++ / CX)](https://msdn.microsoft.com/library/windows/apps/hh969554.aspx).

## <a name="common-language-runtime"></a>Common Language Runtime

Die Compiler-Felder von Werttypen zu <xref:System.Object>. Dies ist möglich durch eine compiler-definierte Konvertierung zur Konvertierung von Werttypen in <xref:System.Object>.

Mit Boxing und Unboxing können Werttypen wie Objekte behandelt werden. Werttypen, einschließlich Strukturtypen und integrierten Typen wie int, können in und aus dem Typ <xref:System.Object> konvertiert werden.

Weitere Informationen finden Sie unter:

- [Vorgehensweise: Explizites Anfordern von Boxing](../dotnet/how-to-explicitly-request-boxing.md)

- [Vorgehensweise: Verwenden von gcnew zum Erstellen von Werttypen und für implizites Boxing](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)

- [Vorgehensweise: Unboxing](../dotnet/how-to-unbox.md)

- [Standardumwandlungen und implizites Boxing](../dotnet/standard-conversions-and-implicit-boxing.md)

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Das folgende Beispiel zeigt wie implizites Boxing funktioniert.

```cpp
// vcmcppv2_explicit_boxing2.cpp
// compile with: /clr
using namespace System;

ref class A {
public:
   void func(System::Object^ o){Console::WriteLine("in A");}
};

value class V {};

interface struct IFace {
   void func();
};

value class V1 : public IFace {
public:
   virtual void func() {
      Console::WriteLine("Interface function");
   }
};

value struct V2 {
   // conversion operator to System::Object
   static operator System::Object^(V2 v2) {
      Console::WriteLine("operator System::Object^");
      return (V2^)v2;
   }
};

void func1(System::Object^){Console::WriteLine("in void func1(System::Object^)");}
void func1(V2^){Console::WriteLine("in func1(V2^)");}

void func2(System::ValueType^){Console::WriteLine("in func2(System::ValueType^)");}
void func2(System::Object^){Console::WriteLine("in func2(System::Object^)");}

int main() {
   // example 1 simple implicit boxing
   Int32^ bi = 1;
   Console::WriteLine(bi);

   // example 2 calling a member with implicit boxing
   Int32 n = 10;
   Console::WriteLine("xx = {0}", n.ToString());

   // example 3 implicit boxing for function calls
   A^ a = gcnew A;
   a->func(n);

   // example 4 implicit boxing for WriteLine function call
   V v;
   Console::WriteLine("Class {0} passed using implicit boxing", v);
   Console::WriteLine("Class {0} passed with forced boxing", (V^)(v));   // force boxing

   // example 5 casting to a base with implicit boxing
   V1 v1;
   IFace ^ iface = v1;
   iface->func();

   // example 6 user-defined conversion preferred over implicit boxing for function-call parameter matching
   V2 v2;
   func1(v2);   // user defined conversion from V2 to System::Object preferred over implicit boxing
                // Will call void func1(System::Object^);

   func2(v2);   // OK: Calls "static V2::operator System::Object^(V2 v2)"
   func2((V2^)v2);   // Using explicit boxing: calls func2(System::ValueType^)  
}
```

```Output
1

xx = 10

in A

Class V passed using implicit boxing

Class V passed with forced boxing

Interface function

in func1(V2^)

in func2(System::ValueType^)

in func2(System::ValueType^)  
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET- und UWP](../windows/component-extensions-for-runtime-platforms.md)