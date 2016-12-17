---
title: "new (new slot in vtable)  (C++ Component Extensions)"
ms.custom: na
ms.date: "12/16/2016"
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
  - "new keyword [C++]"
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
caps.latest.revision: 20
caps.handback.revision: "18"
ms.author: "mblome"
manager: "ghogen"
---
# new (new slot in vtable)  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Schlüsselwort `new` gibt an, dass ein virtuelles Member einen neuen Platz im vtable erhält.  
  
> [!NOTE]
>  Das Schlüsselwort `new` hat viele Verwendungszwecke und Bedeutungen.  Weitere Informationen finden Sie im Thema zur Erläuterung der Mehrdeutigkeit von [neu](../misc/new.md).  
  
## Alle Laufzeiten  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die für alle Laufzeiten gültig sind.\)  
  
## Windows\-Runtime  
 Nicht unterstützt in [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Hinweise**  
  
 In einer **\/clr**\-Kompilierung gibt `new` an, dass ein virtuelles Member einen neuen PLatz im vtable erhält und dass die Funktion keine Basisklassenmethode überschreibt.  
  
 `new` veranlasst, dass der newslot\-Modifizierer dem IL für die Funktion hinzugefügt wird.  Weitere Informationen zu "newslot" finden Sie unter:  
  
-   [\<caps:sentence id\="tgt11" sentenceid\="e9bb59a12f97840a5c3173bb77c6b5b1" class\="tgtSentence"\>MethodInfo.GetBaseDefinition\-Methode\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.reflection.methodinfo.getbasedefinition.aspx)  
  
-   [\<caps:sentence id\="tgt12" sentenceid\="f6ceddd85a425f38e7ed06e94a9808a9" class\="tgtSentence"\>MethodAttributes\-Enumeration\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.reflection.methodattributes.aspx)  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel werden die Auswirkungen von `new` gezeigt.  
  
```  
// newslot.cpp  
// compile with: /clr  
ref class C {  
public:  
   virtual void f() {  
      System::Console::WriteLine("C::f() called");  
   }  
  
   virtual void g() {  
      System::Console::WriteLine("C::g() called");  
   }  
};  
  
ref class D : public C {  
public:  
   virtual void f() new {  
      System::Console::WriteLine("D::f() called");  
   }  
  
   virtual void g() override {  
      System::Console::WriteLine("D::g() called");  
   }  
};  
  
ref class E : public D {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("E::f() called");  
   }  
};  
  
int main() {  
   D^ d = gcnew D;  
   C^ c = gcnew D;  
  
   c->f();   // calls C::f  
   d->f();   // calls D::f  
  
   c->g();   // calls D::g  
   d->g();   // calls D::g  
  
   D ^ e = gcnew E;  
   e->f();   // calls E::f  
}  
```  
  
 **Ausgabe**  
  
  **C::f\(\) aufgerufen**  
 **D::f\(\) aufgerufen**  
 **D::g\(\) aufgerufen**  
 **D::g\(\) aufgerufen**  
 **E::f\(\) aufgerufen**   
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Überschreibungsspezifizierer](../windows/override-specifiers-cpp-component-extensions.md)