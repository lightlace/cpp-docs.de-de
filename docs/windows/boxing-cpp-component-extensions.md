---
title: "Boxing  (C++ Component Extensions)"
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
  - "boxing, Visual C++"
ms.assetid: b5fd2c98-c578-4f83-8257-6dd663478665
caps.latest.revision: 27
caps.handback.revision: "25"
ms.author: "mblome"
manager: "ghogen"
---
# Boxing  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der Visual C\+\+ Compiler kann Werttypen in einem Vorgang mit der Bezeichnung *Boxing* in Objekte und Objekte in einem Vorgang namens *Unboxing* in Werttypen konvertieren.  
  
## Alle Laufzeiten  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.\)  
  
## Windows\-Runtime  
 [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] unterstützt eine Kurzsyntax für Boxing\-Werttypen und Unboxing\-Verweistypen.  Ein Werttyp mittels Boxing konvertiert, wenn sie einer Variable des Typs `Object` zugewiesen wird.  Eine `Object`\-Variable wird mittels Unboxing konvertiert, wenn sie einer Werttypvariable zugeordnet ist und der Unboxing\-Typ in Klammern angegeben wird; d. h., wenn die Objektvariable in einen Werttyp umgewandelt wird.  
  
```  
  
Platform::Object^ object_variable  = value_variable;  
value_variable = (value_type) object_variable;  
  
```  
  
### Anforderungen  
 Compileroption: **\/ZW**  
  
### Beispiele  
 Im folgenden Beispiel wird ein `DateTime`\-Wert mittels Boxing und Unboxing konvertiert.  Zunächst ruft das Beispiel einen DateTime\-Wert ab, der das aktuelle Datum und die Uhrzeit darstellt, und weist ihm eine DateTime\-Variable zu.  Anschließend wird die DateTime durch Zuweisen einer Objektvariabler mittels Boxing konvertiert.  Schließlich wird der Boxing\-Wert mittels Unboxing zurückkonvertiert, indem ihm eine andere DateTime\-Variable zugewiesen wird.  
  
 Um das Beispiel zu testen, erstellen Sie ein BlankApplication\-Projekt, ersetzen Sie die BlankPage::OnNavigatedTo\(\)\-Methode und geben Sie dann bei der schließenden Klammer Haltepunkte und die Zuweisung zur Variable str1 an.  Im Beispiel wird die schließende Klammer erreicht, untersuchen Sie str1.  
  
```  
  
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
  
 Weitere Informationen finden Sie unter [Boxing \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh969554.aspx).  
  
## Common Language Runtime  
 Visual C\+\+\-Compiler konvertiert nun Boxing\-Werttypen in  <xref:System.Object>.  Dies ist möglich durch eine compiler\-definierte Konvertierung zur Konvertierung von Werttypen in <xref:System.Object>.  
  
 Mit Boxing und Unboxing können Werttypen wie Objekte behandelt werden.  Werttypen, einschließlich Strukturtypen und integrierten Typen wie int, können in und aus dem Typ <xref:System.Object> konvertiert werden.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Gewusst wie: Explizites Anfordern von Boxing](../dotnet/how-to-explicitly-request-boxing.md)  
  
-   [Gewusst wie: Verwenden von gcnew zum Erstellen von Werttypen und für implizites Boxing](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)  
  
-   [Gewusst wie: Unboxing](../dotnet/how-to-unbox.md)  
  
-   [Standardumwandlungen und implizites Boxing](../dotnet/standard-conversions-and-implicit-boxing.md)  
  
### Anforderungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
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
  
 **Ausgabe**  
  
  **1**  
 **xx \= 10**  
 **in A**  
 **Klasse V mit implizitem Boxing übergeben**  
 **Klasse V mit erzwungenem Boxing übergeben**  
 **Schnittstellen\-Funktion**  
 **in func1\(V2^\)**  
 **in func2\(System::ValueType^\)**  
 **in func2\(System::ValueType^\)**   
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)