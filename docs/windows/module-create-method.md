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
ms.openlocfilehash: a8b84bcaec7dbadfb7b735264df12f7e958dcd20
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444696"
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

*T*<br/>
Modultyp.

*Rückruf*<br/>
Wird aufgerufen, wenn das letzte Instanzobjekt des Moduls freigegeben wird.

*object*<br/>
Die *Objekt* und *Methode* Parameter in Kombination verwendet werden. Verweist auf das letzte Instance-Objekt, wenn die letzte Instanzobjekt in das Modul veröffentlicht wird.

*Methode*<br/>
Die *Objekt* und *Methode* Parameter in Kombination verwendet werden. Zeigt auf die Methode des letzten Instance-Objekt, wenn die letzte Instanzobjekt in das Modul veröffentlicht wird.

## <a name="return-value"></a>Rückgabewert

Verweis auf das Modul.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Module-Klasse](../windows/module-class.md)