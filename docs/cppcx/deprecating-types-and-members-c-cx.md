---
title: "Einstufen von Typen und Membern als veraltet (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Einstufen von Typen und Membern als veraltet (C++/CX)
In C\+\+\/CX werden veraltete [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen und \-Members für Producer und Consumer durch das Attribut [Deprecated](http://msdn.microsoft.com/de-de/8b02ad36-3b5f-4361-888b-e6a99040e57c) unterstützt. Wenn Sie eine API nutzen, für die dieses Attribut gilt, erhalten Sie zur Kompilierzeit eine Warnmeldung, die angibt, dass die API veraltet ist, und auch eine alternative API zur Verwendung empfiehlt. In Ihren eigenen öffentlichen Typen und Methoden können Sie dieses Attribut anwenden und eine eigene benutzerdefinierte Meldung bereitstellen.  
  
> [!CAUTION]
>  Das [Deprecated](http://msdn.microsoft.com/de-de/8b02ad36-3b5f-4361-888b-e6a99040e57c)\-Attribut dient nur der Verwendung mit [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen. Verwenden Sie für Standard\-C\+\+\-Klassen und \-Member das Attribut [\_\_declspec\(deprecated\)](http://msdn.microsoft.com/library/044swk7y.aspx).  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine eigene öffentliche API – z. B. in einer Windows Runtime\-Komponente als veraltet markiert wird. Der zweite Parameter vom Typ [Windows:Foundation::Metadata::DeprecationType](http://msdn.microsoft.com/de-de/ee01e63d-37d0-4273-accc-fca174f88bfa) gibt an, ob die API als veraltet markiert oder entfernt wird. Derzeit wird nur der Wert DeprecationType::Deprecated unterstützt. Der dritte Parameter im Attribut gibt die [Windows::Foundation::Metadata::Platform](http://msdn.microsoft.com/de-de/1eae292d-1ab7-4d97-a58c-b0beffd51ef5) an, auf die das Attribut angewendet wird.  
  
```  
  
namespace wfm = Windows::Foundation::Metadata; public ref class Bicycle sealed { public: property double Speed; [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)] double ComputeAngularVelocity(); };  
```  
  
## Unterstützte Ziele  
 In der folgenden Tabelle werden die Konstrukte aufgeführt, auf die das veraltete Attribut angewendet werden kann:  
  
||  
|-|  
|XAML\-Steuerelement|  
|delegate|  
|event|  
|Enumerationsfeld|  
|enum|  
|struct|  
|Methode|  
|Klasse|  
|interface|  
|property|  
|struct field|  
|parameterized constructor|  
  
## Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)