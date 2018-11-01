---
title: Operator Type^
ms.date: 12/30/2016
ms.assetid: b24ffc83-0780-4f9a-8ee0-f5725db339d1
ms.openlocfilehash: fca53abb9dc17588695591d496b7db2a76e319f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553659"
---
# <a name="operator-type"></a>Operator Type^

Ermöglicht die Konvertierung von [Windows::UI::Xaml::Interop::TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) in `Platform::Type`.

## <a name="syntax"></a>Syntax

```cpp
Operator Type^(Windows::UI::Xaml::Interop::TypeName typeName);
```

### <a name="return-value"></a>Rückgabewert

Gibt einen `Platform::Type` zurück, wenn ein [Windows::UI::Xaml::Interop::TypeName](https://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx)angegeben wurde.

### <a name="remarks"></a>Hinweise

`TypeName` ist die sprachenneutrale Windows Runtime-Struktur für die Darstellung von Typinformationen. [Platform::Type](../cppcx/platform-type-class.md) ist C++-spezifisch und kann nicht über die Anwendungsbinärdateischnittstelle (ABI) übergeben werden. Hier eine Verwendung von `TypeName`in der [Navigate](https://msdn.microsoft.com/library/windows/apps/hh702394.aspx) -Funktion:

```
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt die Umwandlung zwischen `TypeName` und `Type`.

```

// Convert from Type to TypeName
TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>Entsprechung in .NET Framework

.NET Framework-Programm-Projekts `TypeName` als <xref:System.Type>

### <a name="requirements"></a>Anforderungen

## <a name="see-also"></a>Siehe auch

[Operator Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform::Type-Klasse](../cppcx/platform-type-class.md)