---
title: Einstufen von Typen und Membern als veraltet (C++/CX)
ms.date: 12/30/2016
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
ms.openlocfilehash: 1e29f2ff73d6fb6fd499052d9f9255f8b1a659c7
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2018
ms.locfileid: "51325847"
---
# <a name="deprecating-types-and-members-ccx"></a>Einstufen von Typen und Membern als veraltet (C++/CX)

In C++ / CX werden veraltete von Windows-Runtime-Typen und Membern für Producer und Consumer durch das [veraltet](/uwp/api/windows.foundation.metadata.deprecatedattribute) -Attribut wird unterstützt. Wenn Sie eine API nutzen, für die dieses Attribut gilt, erhalten Sie zur Kompilierzeit eine Warnmeldung, die angibt, dass die API veraltet ist, und auch eine alternative API zur Verwendung empfiehlt. In Ihren eigenen öffentlichen Typen und Methoden können Sie dieses Attribut anwenden und eine eigene benutzerdefinierte Meldung bereitstellen.

> [!CAUTION]
> Die [veraltet](/uwp/api/windows.foundation.metadata.deprecatedattribute) -Attribut ist nur mit Windows-Runtime-Typen. Verwenden Sie für Standard-C++-Klassen und -Member das Attribut [__declspec(deprecated)](../cpp/deprecated-cpp.md).

### <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie eine eigene öffentliche API – z. B. in einer Windows Runtime-Komponente als veraltet markiert wird. Der zweite Parameter vom Typ [Windows:Foundation::Metadata::DeprecationType](/uwp/api/windows.foundation.metadata.deprecationtype) gibt an, ob die API als veraltet markiert oder entfernt wird. Derzeit wird nur der Wert DeprecationType::Deprecated unterstützt. Der dritte Parameter im Attribut gibt die [Windows::Foundation::Metadata::Platform](/uwp/api/windows.foundation.metadata.platformattribute) an, auf die das Attribut angewendet wird.

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

| |
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