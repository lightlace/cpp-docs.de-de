---
title: "CLR-Integration (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# CLR-Integration (C++/CX)
Einige [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen erhalten in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] und den Sprachen, die auf der CLR \(Common Language Runtime\) basieren, eine Sonderbehandlung. Dieser Artikel behandelt, wie verschiedene Typen in einer Sprache einer anderen Sprache zugeordnet werden. Beispielsweise ordnet die CLR „Windows.Foundation.IVector“ zu „System.Collections.IList“, „Windows.Foundation.IMap“ zu „System.Collections.IDictionary“ zu usw. In ähnlicher Weise ordnet [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] Typen wie „Platform::Delegate“ und „Platform::String“ in besonderer Weise zu.  
  
## Zuordnung von [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] zu [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 Wenn [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] eine Windows\-Metadatendatei \(WINMD\) liest, ordnet der Compiler automatisch gemeinsame [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Namespaces und Typen zu [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Namespaces und Typen zu. Beispielsweise wird der numerische [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typ `UInt32` automatisch zu `default::uint32` zugeordnet.  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] ordnet verschiedene weitere [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen dem **Platform**\-Namespace zu. Beispielsweise wird das **Windows::Foundation**\-HSTRING\-Handle, das eine schreibgeschützte Unicode\-Textzeichenfolge darstellt, der [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] `Platform::String`\-Klasse zugeordnet. Wenn ein [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Vorgang ein HRESULT für einen Fehler zurückgibt, wird dieses einer [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] `Platform::Exception` zugeordnet. Weitere Informationen finden Sie unter [Built\-in Types](http://msdn.microsoft.com/de-de/acc196fd-09da-4882-b554-6c94685ec75f).  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] ordnet darüber hinaus bestimmte Typen in [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Namespaces zu, um die Funktionalität des Typs zu steigern. Für diese Typen stellt [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] Hilfskonstruktoren und Methoden bereit, die für C\+\+ spezifisch sind und in der standardmäßigen WINMD\-Datei des Typs nicht zur Verfügung stehen.  
  
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
  
## Zuordnen der CLR zu [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]  
 Wenn die Visual C\+\+\- oder C\#\-Compiler eine WINMD\-Datei lesen, ordnen sie automatisch bestimmte Typen in der Metadatendatei entsprechenden [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\- oder CLR\-Typen zu. Beispielweise ist in der CLR die Schnittstelle „IVector\<T\>“ „IList\<T\>“ zugeordnet. In [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] ist die Schnittstelle „IVector\<T\>“ jedoch keinem anderen Typ zugeordnet.  
  
 „IReference\<T\>“ in der [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] wird „Nullable\<T\>“ in .NET zugeordnet.  
  
## Siehe auch  
 [Interoperabilität mit anderen Sprachen](../cppcx/interoperating-with-other-languages-c-cx.md)