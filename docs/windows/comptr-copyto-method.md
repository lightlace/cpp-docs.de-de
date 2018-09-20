---
title: 'Comptr:: CopyTo-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: 8801bc49-6db4-4393-a55f-a701ae3b8718
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c9b84cbcc970183222ed06752dc61b5672615868
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405384"
---
# <a name="comptrcopyto-method"></a>ComPtr::CopyTo-Methode

Kopiert die aktuelle oder angegebene-Schnittstelle, die zugeordneten **ComPtr** an den angegebenen Zeiger.

## <a name="syntax"></a>Syntax

```cpp
HRESULT CopyTo(
   _Deref_out_ InterfaceType** ptr
);

HRESULT CopyTo(
   REFIID riid,
   _Deref_out_ void** ptr
) const;

template<typename U>
HRESULT CopyTo(
   _Deref_out_ U** ptr
) const;
```

### <a name="parameters"></a>Parameter

*U*<br/>
Ein Typname.

*ptr*<br/>
Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf die angeforderte Schnittstelle.

*riid*<br/>
Eine Schnittstellen-ID.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das gibt an, warum das implizite `QueryInterface` Fehler beim Vorgang.

## <a name="remarks"></a>Hinweise

Die erste Funktion gibt eine Kopie eines Zeigers auf die Schnittstelle zugeordneten **ComPtr**. Diese Funktion gibt stets S_OK zurück.

Die zweite Funktion führt eine `QueryInterface` Vorgang für die Schnittstelle zugeordneten **comptr-Objekt** für die angegebene Schnittstelle die *Riid* Parameter.

Die dritte Funktion führt eine `QueryInterface` Vorgang für die Schnittstelle zugeordneten **comptr-Objekt** für die zugrunde liegenden Schnittstelle die *U* Parameter.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ComPtr-Klasse](../windows/comptr-class.md)