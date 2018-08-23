---
title: CLR-Integration (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 527ce8beaf5fb08d0642026336be193e3b39d73b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42581123"
---
# <a name="clr-integration-ccx"></a>CLR-Integration (C++/CX)
Einige Windows-Runtime-Typen erhalten Sie spezielle Behandlung in C++ / CX und die Sprachen an, die auf die common Language Runtime (CLR) basieren. Dieser Artikel behandelt, wie verschiedene Typen in einer Sprache einer anderen Sprache zugeordnet werden. Beispielsweise ordnet die CLR „Windows.Foundation.IVector“ zu „System.Collections.IList“, „Windows.Foundation.IMap“ zu „System.Collections.IDictionary“ zu usw. Auf ähnliche Weise C + c++ / CX ordnet Typen wie z. B. Delegate "und" Platform:: String.  
  
## <a name="mapping-the-windows-runtime-to-ccx"></a>Zuordnen von der Windows-Runtime für C++ / CX  
 Wenn C++ / CX liest eine Windows-Metadatendatei (.winmd), ordnet der Compiler automatisch gemeinsame Windows-Runtime-Namespaces und Typen für C++ / CX-Namespaces und Typen. Z. B. den numerischen Typ Windows-Runtime `UInt32` automatisch zugeordnet ist `default::uint32`.  
  
 C++ / CX ordnet mehrere andere Windows-Runtime-Typen an die **Plattform** Namespace. Z. B. die **Windows:: Foundation** HSTRING-Handle, das eine schreibgeschützte Unicode-Textzeichenfolge darstellt, zugeordnet ist C++ / CX `Platform::String` Klasse. Ein Windows-Runtime-Vorgang einen Fehler HRESULT zurückgibt, zugeordnet, um C++ / CX `Platform::Exception`. Weitere Informationen finden Sie unter [Built-in Types](http://msdn.microsoft.com/en-us/acc196fd-09da-4882-b554-6c94685ec75f).  
  
 C++ / CX ordnet darüber hinaus bestimmte Typen in Windows-Runtime-Namespaces, um die Funktionalität des Typs zu verbessern. Für diese Typen stellt C++ / CX stellt hilfskonstruktoren und Methoden, die für C++ spezifisch sind, und sind in den Typ der standardmäßigen winmd-Datei nicht verfügbar.  
  
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
  
## <a name="mapping-the-clr-to-ccx"></a>Zuordnen der CLR für C++ / CX  
 Wenn die Visual C++ oder c#-Compiler eine winmd-Datei lesen, ordnen sie automatisch bestimmte Typen in der Metadatendatei für entsprechende C++ / CX- oder CLR-Datentypen. Z. B. in der CLR, die IVector\<T >-Schnittstelle IList zugeordnet ist\<T >. Aber in C++ / CX, die IVector\<T >-Schnittstelle ist nicht in einen anderen Typ zugeordnet.  
  
 "IReference"\<T > in der Windows-Runtime ordnet Nullable\<T > in .NET.  
  
## <a name="see-also"></a>Siehe auch  
 [Interoperabilität mit anderen Sprachen](../cppcx/interoperating-with-other-languages-c-cx.md)