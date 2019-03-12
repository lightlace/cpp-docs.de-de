---
title: Operator Windows::UI::Xaml::Interop::TypeName
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: 5acf17b7c87a71259dba6579d8ee69e0eea86fa5
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738428"
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
