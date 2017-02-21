---
title: "Gewusst wie: Verwenden eines systemeigenen Typs in einer /clr-Kompilierung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr-Compileroption [C++], Verwenden von systemeigenen Typen"
  - "Kompilierung, Systemeigene Typen in /clr"
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Gewusst wie: Verwenden eines systemeigenen Typs in einer /clr-Kompilierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können in einer **\/clr**\-Kompilierung einen systemeigenen Typ definieren, dessen Verwendung aus der Assembly heraus dann gültig ist.  Systemeigene Typen können jedoch nicht von Metadaten aus verwendet werden, auf die verwiesen wird.  
  
 Jede Assembly muss die Definition aller systemeigenen Typen enthalten, die sie verwendet.  
  
 Weitere Informationen finden Sie unter [\/clr \(Common Language Runtime\-Kompilierung\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## Beispiel  
 In diesem Beispiel wird eine Komponente erstellt, die einen systemeigenen Typ definiert und verwendet.  
  
```  
// use_native_type_in_clr.cpp  
// compile with: /clr /LD  
public struct NativeClass {  
   static int Test() { return 98; }  
};  
  
public ref struct ManagedClass {  
   static int i = NativeClass::Test();  
   void Test() {  
      System::Console::WriteLine(i);  
   }  
};  
```  
  
## Beispiel  
 In diesem Beispiel wird ein Client definiert, der die Komponente verwendet.  Beachten Sie, dass der Zugriff auf einen systemeigenen Typ einen Fehler verursacht, sofern der Typ nicht in der Kompiliereinheit definiert wurde.  
  
```  
// use_native_type_in_clr_2.cpp  
// compile with: /clr  
#using "use_native_type_in_clr.dll"  
// Uncomment the following 3 lines to resolve.  
// public struct NativeClass {  
//    static int Test() { return 98; }  
// };  
  
int main() {  
   ManagedClass x;  
   x.Test();  
  
   System::Console::WriteLine(NativeClass::Test());   // C2653  
}  
```  
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)