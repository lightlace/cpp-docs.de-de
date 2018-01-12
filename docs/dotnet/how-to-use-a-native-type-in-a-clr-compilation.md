---
title: 'Vorgehensweise: Verwenden eines systemeigenen Typs in einer Clr - Kompilierung | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- compilation, native types in /clr
- /clr compiler option [C++], using native types
ms.assetid: 3a505c90-4adb-4942-9cf9-7d1fdcbc01e7
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c0a73d5bd9c165645dbf3c3cdee7a740cc3c16a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-a-native-type-in-a-clr-compilation"></a>Gewusst wie: Verwenden eines systemeigenen Typs in einer /clr-Kompilierung
Sie können in einen systemeigenen Typ definieren eine **"/ CLR"** Kompilierung und jede Verwendung des systemeigenen Typs von innerhalb der Assembly ist ungültig. Systemeigene Typen können allerdings nicht für die Verwendung von Metadaten verwiesen wird, verfügbar sein.  
  
 Jede Assembly muss die Definition aller systemeigenen Typen enthalten, die verwendet werden.  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine Komponente, die definiert und verwendet einen systemeigenen Typ erstellt.  
  
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
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel definiert einen Client, der Komponente verwendet. Beachten Sie, dass es ist ein Fehler auf, den systemeigenen Typ zugreifen, es sei denn, sie in der Kompiliereinheit definiert ist.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)