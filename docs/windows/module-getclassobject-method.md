---
title: 'Module:: GetClassObject-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- GetClassObject method
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e0c8996823de35bbfd85d595556db933f34238a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599221"
---
# <a name="modulegetclassobject-method"></a>Module::GetClassObject-Methode

Ruft einen Cache von Klassenfactorys.

## <a name="syntax"></a>Syntax

```cpp
 HRESULT GetClassObject(
   REFCLSID clsid,
   REFIID riid,
   _Deref_out_ void **ppv,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parameter

*clsid*  
Klassen-ID.

*riid*  
Schnittstellen-ID, die Sie anfordern.

*ppv*  
Zeiger auf das zurückgegebene Objekt.

*ServerName*  
Den Namen des Servers, der entweder angegeben ist die `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx`, oder `ActivatableClass` Makro; oder **"nullptr"** um den Standardnamen für den Server zu erhalten.

## <a name="return-value"></a>Rückgabewert

## <a name="remarks"></a>Hinweise

Verwenden Sie diese Methode nur für COM, nicht die Windows-Runtime. Diese Methode macht nur `IClassFactory` Methoden.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch
[Module-Klasse](../windows/module-class.md)