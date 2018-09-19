---
title: 'Module:: Create-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Create
dev_langs:
- C++
helpviewer_keywords:
- Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9ae4f50e6d2d614e444766babf8e55f5c9f83932
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609543"
---
# <a name="modulecreate-method"></a>Module::Create-Methode

Erstellt eine Instanz eines Moduls.

## <a name="syntax"></a>Syntax

```cpp
WRL_NOTHROW static Module& Create();
template<typename T>
WRL_NOTHROW static Module& Create(
   T callback
);
template<typename T>
WRL_NOTHROW static Module& Create(
   _In_ T* object,
   _In_ void (T::* method)()  
);
```

### <a name="parameters"></a>Parameter

*T*  
Modultyp.

*Rückruf*  
Wird aufgerufen, wenn das letzte Instanzobjekt des Moduls freigegeben wird.

*object*  
Die *Objekt* und *Methode* Parameter in Kombination verwendet werden. Verweist auf das letzte Instance-Objekt, wenn die letzte Instanzobjekt in das Modul veröffentlicht wird.

*Methode*  
Die *Objekt* und *Methode* Parameter in Kombination verwendet werden. Zeigt auf die Methode des letzten Instance-Objekt, wenn die letzte Instanzobjekt in das Modul veröffentlicht wird.

## <a name="return-value"></a>Rückgabewert

Verweis auf das Modul.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Module-Klasse](../windows/module-class.md)