---
title: Operator TypeName | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0cf5041e6e3faa8c495d52c31d86ff25c903a174
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600719"
---
# <a name="operator-windowsuixamlinteroptypename"></a>Operator Windows::UI::Xaml::Interop::TypeName
Ermöglicht die Konvertierung von `Platform::Type` in [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
Operator TypeName(Platform::Type^ type)  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein [Windows::UI::Xaml::Interop::TypeName](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.interop.typename.aspx) zurück, wenn ein `Platform::Type^`angegeben wurde.  
  
### <a name="remarks"></a>Hinweise  
 `TypeName` ist die sprachenneutrale Windows Runtime-Struktur für die Darstellung von Typinformationen. [Platform::Type](../cppcx/platform-type-class.md) ist C++-spezifisch und kann nicht über die Anwendungsbinärdateischnittstelle (ABI) übergeben werden. Hier eine Verwendung von `TypeName`in der [Navigate](http://msdn.microsoft.com/library/windows/apps/hh702394.aspx) -Funktion:  
  
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
 [TypeName-Operator](../cppcx/operator-windows-ui-xaml-interop-typename.md)   
 [Platform::Type-Klasse](../cppcx/platform-type-class.md)