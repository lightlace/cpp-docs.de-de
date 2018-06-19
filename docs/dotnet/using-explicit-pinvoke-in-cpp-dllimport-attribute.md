---
title: Verwenden von explizitem PInvoke in C++ (DllImport-Attribut) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling [C++], platform invoke
- C++ Interop, platform invoke
- interop [C++], platform invoke
- platform invoke [C++], marshaling in C++
- data marshaling [C++], platform invoke
ms.assetid: 18e5218c-6916-48a1-a127-f66e22ef15fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 82215e4815d25dd116cf930be9cc0f40da761bf8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169503"
---
# <a name="using-explicit-pinvoke-in-c-dllimport-attribute"></a>Verwenden von explizitem PInvoke in C++ (DllImport-Attribut)
.NET Framework verfügt über explizite PInvoke-Features (Platform Invoke) mit dem `Dllimport`-Attribut, um das Aufrufen von in DLLs verpackten, nicht verwalteten Funktionen durch verwaltete Funktionen zu ermöglichen. Explizites PInvoke ist in Situationen erforderlich, in denen nicht verwaltete APIs als DLLs verpackt sind und der Quellcode nicht verfügbar ist. Beispielsweise ist PInvoke beim Aufrufen von Win32-Funktionen erforderlich. Verwenden Sie andernfalls die implizite P {aufrufen; Siehe [mithilfe von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md) für Weitere Informationen.  
  
 PInvoke funktioniert auf Grundlage des <xref:System.Runtime.InteropServices.DllImportAttribute>. Dieses Attribut, das den Namen der DLL als erstes Argument behandelt, wird vor die Funktionsdeklaration jedes verwendeten DLL-Einstiegspunkts gesetzt. Die Signatur der Funktion muss dem Namen einer von der DLL exportierten Funktion entsprechen (ein gewisses Maß an Typkonvertierung kann jedoch implizit durch das Definieren der `DllImport`-Deklarationen als verwaltete Typen erfolgen).  
  
 So ergibt sich ein verwalteter Einstiegspunkt für jede systemeigene DLL-Funktion, die den erforderlichen Übergangscode (oder Thunk) und einfache Datenkonvertierungen enthält. Aus verwalteten Funktionen kann dann über diese Einstiegspunkte ein Aufruf in die DLL erfolgen. Der als Resultat von PInvoke in ein Modul eingefügte Code ist sämtlich verwalteter.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
-   [Aufrufen nativer Funktionen aus verwaltetem Code](../dotnet/calling-native-functions-from-managed-code.md)  
  
-   [Vorgehensweise: Aufrufen von nativen DLLs in verwaltetem Code mithilfe von PInvoke](../dotnet/how-to-call-native-dlls-from-managed-code-using-pinvoke.md)  
  
-   [Vorgehensweise: Marshallen von Zeichenfolgen mit PInvoke](../dotnet/how-to-marshal-strings-using-pinvoke.md)  
  
-   [Vorgehensweise: Marshallen von Strukturen mit PInvoke](../dotnet/how-to-marshal-structures-using-pinvoke.md)  
  
-   [Vorgehensweise: Marshallen von Arrays mit PInvoke](../dotnet/how-to-marshal-arrays-using-pinvoke.md)  
  
-   [Vorgehensweise: Marshallen von Funktionszeigern mit PInvoke](../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)  
  
-   [Vorgehensweise: Marshallen eingebetteter Zeiger mit PInvoke](../dotnet/how-to-marshal-embedded-pointers-using-pinvoke.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufen nativer Funktionen aus verwaltetem Code](../dotnet/calling-native-functions-from-managed-code.md)