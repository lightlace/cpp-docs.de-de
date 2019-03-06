---
title: Operator Windows::UI::Xaml::Interop::TypeName
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: 7480df474086d78e28d235cc89b05094c648d28b
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57415174"
---
# <a name="operator-windowsuixamlinteroptypename"></a>Operator Windows::UI::Xaml::Interop::TypeName

Ermöglicht die Konvertierung von `Platform::Type` in [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename).

## <a name="syntax"></a>Syntax

```cpp
Operator TypeName(Platform::Type^ type);
```

### <a name="return-value"></a>Rückgabewert

Gibt ein [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename) zurück, wenn ein `Platform::Type^`angegeben wurde.

### <a name="remarks"></a>Hinweise

`TypeName` ist die sprachenneutrale Windows Runtime-Struktur für die Darstellung von Typinformationen. [Platform::Type](../cppcx/platform-type-class.md) ist C++-spezifisch und kann nicht über die Anwendungsbinärdateischnittstelle (ABI) übergeben werden. Hier eine Verwendung von `TypeName`in der [Navigate](/uwp/api/windows.ui.xaml.controls.frame.navigate) -Funktion:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Umwandlung zwischen `TypeName` und `Type`.

```

// Convert from Type to TypeName
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework

.NET Framework-Programm-Projekts `TypeName` als [System.Type](assetId:///System.Type?qualifyHint=False&autoUpgrade=True).

### <a name="requirements"></a>Anforderungen

## <a name="see-also"></a>Siehe auch

[Operator Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform::Type-Klasse](../cppcx/platform-type-class.md)