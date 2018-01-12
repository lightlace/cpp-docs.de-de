---
title: CLR-Integration (C + c++ / CX) | Microsoft Docs
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9851a7aa0d1dad84a37504b479c551ffa63bcf9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="clr-integration-ccx"></a>CLR-Integration (C++/CX)
Einige Windows-Runtime-Typen erhalten Sie eine besondere Behandlung in C + c++ / CX und die Sprachen an, die auf die common Language Runtime (CLR) basieren. Dieser Artikel behandelt, wie verschiedene Typen in einer Sprache einer anderen Sprache zugeordnet werden. Beispielsweise ordnet die CLR „Windows.Foundation.IVector“ zu „System.Collections.IList“, „Windows.Foundation.IMap“ zu „System.Collections.IDictionary“ zu usw. Auf ähnliche Weise C + c++ / CX ordnet speziell z. B. Delegate "und" Platform:: String-Typen.  
  
## <a name="mapping-the-windows-runtime-to-ccx"></a>Zuordnen von Windows-Runtime zu C + c++ / CX  
 Wenn C + c++ / CX liest, eine Windows-Metadatendatei (.winmd), ordnet der Compiler automatisch gemeinsame Windows-Runtime-Namespaces und Typen in C + c++ / CX-Namespaces und Typen. Z. B. den numerischen Windows-Runtime-Typ `UInt32` automatisch zugeordnet `default::uint32`.  
  
 C + c++ / CX ordnet verschiedene andere Windows-Runtime-Typen, die **Plattform** Namespace. Z. B. die **Windows:: Foundation** HSTRING-Handle, das eine schreibgeschützte Unicode-Textzeichenfolge darstellt, zugeordnet ist die C + c++ / CX `Platform::String` Klasse. Ein Windows-Runtime-Vorgang einen Fehler HRESULT zurückgibt, zugeordnet, um eine C + c++ / CX `Platform::Exception`. Weitere Informationen finden Sie unter [Built-in Types](http://msdn.microsoft.com/en-us/acc196fd-09da-4882-b554-6c94685ec75f).  
  
 Die C + c++ / CX ordnet auch bestimmte Typen in Windows-Runtime-Namespaces, um die Funktionalität des Typs zu erweitern. Für diese Typen C + c++ / CX bietet hilfskonstruktoren und Methoden, die für C++ spezifisch sind und sind in der standardmäßigen winmd-Datei des Typs nicht verfügbar.  
  
 Die folgende Liste enthält Wertstrukturen, die neue Konstruktoren und Hilfsmethoden unterstützen. Wenn Sie bisher Code erstellt haben, der mit Strukturinitialisierungslisten arbeitet, stellen Sie ihn auf die neu hinzugefügten Konstruktoren um.  
  
 **Windows::Foundation**  
  
-   Punkt  
  
-   Rect  
  
-   Größe  
  
 **Windows::UI**  
  
-   Farbe  
  
 **Windows::UI::Xaml**  
  
-   CornerRadius  
  
-   Dauer  
  
-   GridLength  
  
-   Stärke  
  
 **Windows::UI::Xaml::Interop**  
  
1.  TypeName  
  
 **Windows::UI::Xaml::Media**  
  
-   Matrix  
  
 **Windows::UI::Xaml::Media::Animation**  
  
-   KeyTime  
  
-   RepeatBehavior  
  
 **Windows::UI::Xaml::Media::Media3D**  
  
-   Matrix3D  
  
## <a name="mapping-the-clr-to-ccx"></a>Zuordnen der CLR in C + c++ / CX  
 Wenn die Visual C++- oder C#-Compiler eine winmd-Datei lesen, ordnen sie automatisch bestimmte Typen in der Metadatendatei entsprechenden C + c++ / CX- oder CLR-Typen. Beispielsweise in der CLR, die IVector\<T >-Schnittstelle IList zugeordnet\<T >. Aber in C + c++ / CX, die IVector\<T >-Schnittstelle wird nicht in einen anderen Typ zugeordnet.  
  
 IReference\<T > in Windows-Runtime ordnet Nullable\<T > in .NET.  
  
## <a name="see-also"></a>Siehe auch  
 [Interoperabilität mit anderen Sprachen](../cppcx/interoperating-with-other-languages-c-cx.md)