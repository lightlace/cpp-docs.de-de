---
title: Einstufen von Typen und Membern als veraltet (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8aecb47db6e9d620ff49fac337454242a1bdb72a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42605700"
---
# <a name="deprecating-types-and-members-ccx"></a>Einstufen von Typen und Membern als veraltet (C++/CX)
In C++ / CX werden veraltete von Windows-Runtime-Typen und Membern für Producer und Consumer durch das [veraltet](http://msdn.microsoft.com/en-us/8b02ad36-3b5f-4361-888b-e6a99040e57c) -Attribut wird unterstützt. Wenn Sie eine API nutzen, für die dieses Attribut gilt, erhalten Sie zur Kompilierzeit eine Warnmeldung, die angibt, dass die API veraltet ist, und auch eine alternative API zur Verwendung empfiehlt. In Ihren eigenen öffentlichen Typen und Methoden können Sie dieses Attribut anwenden und eine eigene benutzerdefinierte Meldung bereitstellen.  
  
> [!CAUTION]
>  Die [veraltet](http://msdn.microsoft.com/en-us/8b02ad36-3b5f-4361-888b-e6a99040e57c) -Attribut ist nur mit Windows-Runtime-Typen. Verwenden Sie für Standard-C++-Klassen und -Member das Attribut [__declspec(deprecated)](http://msdn.microsoft.com/library/044swk7y.aspx).  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine eigene öffentliche API – z. B. in einer Windows Runtime-Komponente als veraltet markiert wird. Der zweite Parameter vom Typ [Windows:Foundation::Metadata::DeprecationType](http://msdn.microsoft.com/en-us/ee01e63d-37d0-4273-accc-fca174f88bfa) gibt an, ob die API als veraltet markiert oder entfernt wird. Derzeit wird nur der Wert DeprecationType::Deprecated unterstützt. Der dritte Parameter im Attribut gibt die [Windows::Foundation::Metadata::Platform](http://msdn.microsoft.com/en-us/1eae292d-1ab7-4d97-a58c-b0beffd51ef5) an, auf die das Attribut angewendet wird.  
  
```  
  
namespace wfm = Windows::Foundation::Metadata;  
  
public ref class Bicycle sealed  
{  
  
public:  
    property double Speed;  
  
    [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)]  
    double ComputeAngularVelocity();  
};  
```  
  
## <a name="supported-targets"></a>Unterstützte Ziele  
 In der folgenden Tabelle werden die Konstrukte aufgeführt, auf die das veraltete Attribut angewendet werden kann:  
  
||  
|-|  
|XAML-Steuerelement|  
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
  
## <a name="see-also"></a>Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)   
 [Sprachreferenz zu Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)