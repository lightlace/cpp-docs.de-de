---
title: "Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)"
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
  - "C++ Interop, Plattformaufruf"
  - "Datenmarshalling [C++], Plattformaufruf"
  - "Interop [C++], Plattformaufruf"
  - "Marshaling [C++], Plattformaufruf"
  - "Plattformaufruf [C++], Marshalling in C++"
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.NET Framework verfügt über explizite PInvoke\-Features \(Platform Invoke\) mit dem `Dllimport`\-Attribut, um das Aufrufen von in DLLs verpackten, nicht verwalteten Funktionen durch verwaltete Funktionen zu ermöglichen.  Explizites PInvoke ist in Situationen erforderlich, in denen nicht verwaltete APIs als DLLs verpackt sind und der Quellcode nicht verfügbar ist.  Beispielsweise ist PInvoke beim Aufrufen von Win32\-Funktionen erforderlich.  Verwenden Sie andernfalls implizites P\\{Invoke. Weitere Informationen finden Sie unter [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
 PInvoke funktioniert auf Grundlage des <xref:System.Runtime.InteropServices.DllImportAttribute>.  Dieses Attribut, das den Namen der DLL als erstes Argument behandelt, wird vor die Funktionsdeklaration jedes verwendeten DLL\-Einstiegspunkts gesetzt.  Die Signatur der Funktion muss dem Namen einer von der DLL exportierten Funktion entsprechen \(ein gewisses Maß an Typkonvertierung kann jedoch implizit durch das Definieren der `DllImport`\-Deklarationen als verwaltete Typen erfolgen\).  
  
 So ergibt sich ein verwalteter Einstiegspunkt für jede systemeigene DLL\-Funktion, die den erforderlichen Übergangscode \(oder Thunk\) und einfache Datenkonvertierungen enthält.  Aus verwalteten Funktionen kann dann über diese Einstiegspunkte ein Aufruf in die DLL erfolgen.  Der als Resultat von PInvoke in ein Modul eingefügte Code ist sämtlich verwalteter Code. Explizites PInvoke wird für **\/clr**\-, **\/clr:pure**\- und **\/clr:safe**\-Kompilierungen unterstützt.  Weitere Informationen finden Sie unter [Reiner und überprüfbarer Code](../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## In diesem Abschnitt  
  
-   [Aufrufen systemeigener Funktionen aus verwaltetem Code](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [Gewusst wie: Aufrufen von systemeigenen DLLs in verwaltetem Code mithilfe von PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [Gewusst wie: Marshallen von Zeichenfolgen mit PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [Gewusst wie: Marshallen von Strukturen mit PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [Gewusst wie: Marshallen von Arrays mit PInvoke](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [Gewusst wie: Marshallen von Funktionszeigern mit PInvoke](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [Gewusst wie: Marshallen eingebetteter Zeiger mit PInvoke](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## Siehe auch  
 [Aufrufen systemeigener Funktionen aus verwaltetem Code](../dotnet/calling-native-functions-from-managed-code.md)