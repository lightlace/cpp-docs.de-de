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
ms.openlocfilehash: 500b93f3a84ecb39706b5c1575887a7339d1fdd4
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102090"
---
# <a name="deprecating-types-and-members-ccx"></a>Einstufen von Typen und Membern als veraltet (C++/CX)

In C++ / CX werden veraltete von Windows-Runtime-Typen und Membern für Producer und Consumer durch das [veraltet](/uwp/api/windows.foundation.metadata.deprecatedattribute) -Attribut wird unterstützt. Wenn Sie eine API nutzen, für die dieses Attribut gilt, erhalten Sie zur Kompilierzeit eine Warnmeldung, die angibt, dass die API veraltet ist, und auch eine alternative API zur Verwendung empfiehlt. In Ihren eigenen öffentlichen Typen und Methoden können Sie dieses Attribut anwenden und eine eigene benutzerdefinierte Meldung bereitstellen.

> [!CAUTION]
> Die [veraltet](/uwp/api/windows.foundation.metadata.deprecatedattribute) -Attribut ist nur mit Windows-Runtime-Typen. Verwenden Sie für Standard-c++-Klassen und Member [__declspec(deprecated)](../cpp/deprecated-cpp.md).

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie eine eigene öffentliche API – z. B. in einer Windows Runtime-Komponente als veraltet markiert wird. Der zweite Parameter vom Typ [Windows: Foundation:: Metadata:: deprecationtype](/uwp/api/windows.foundation.metadata.deprecationtype) gibt an, ob die API als veraltet markiert oder entfernt. Derzeit wird nur der Wert DeprecationType::Deprecated unterstützt. Der dritte Parameter im Attribut gibt die [Windows::Foundation::Metadata::Platform](/uwp/api/windows.foundation.metadata.platformattribute) auf die das Attribut angewendet wird.

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

[Typsystem](../cppcx/type-system-c-cx.md)<br/>
[Sprachreferenz zu Visual C++](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)