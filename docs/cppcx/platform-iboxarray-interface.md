---
title: Platform::IBoxArray-Schnittstelle
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Value
helpviewer_keywords:
- Platform::IBoxArray
ms.assetid: 6cd82c9e-4230-4147-9edb-7a652875dbf1
ms.openlocfilehash: a35a8b7d9f23bcb624755353e27e52de4b873c5d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50497021"
---
# <a name="platformiboxarray-interface"></a>Platform::IBoxArray-Schnittstelle

,`IBoxArray` ist der Wrapper für Arrays von Werttypen, die über die Anwendungsbinärdateischnittstelle (ABI) übergeben werden oder in Auflistungen von `Platform::Object^` -Elementen, wie die in XAML-Steuerelementen, gespeichert werden.

## <a name="syntax"></a>Syntax

```cpp
template <typename T>
interface class IBoxArray
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des geschachtelten Werts in jedem Arrayelement.

### <a name="remarks"></a>Hinweise

`IBoxArray` ist die C++ / CX-Namen für `Windows::Foundation::IReferenceArray`.

### <a name="members"></a>Member

Die `IBoxArray` -Schnittstelle erbt von der `IValueType` -Schnittstelle. `IBoxArray` umfasst auch folgende Member:

|Methode|Beschreibung|
|------------|-----------------|
|[Wert](#value)|Gibt das nicht geschachtelte Array zurück, das zuvor in dieser `IBoxArray` -Instanz gespeichert wurde.|

## <a name="value"></a> Iboxarray:: Value-Eigenschaft

Gibt den ursprünglich in diesem Objekt gespeicherten Wert zurück.

### <a name="syntax"></a>Syntax

```cpp
property T Value {T get();}
```

### <a name="parameters"></a>Parameter

*T*<br/>
Der Typ des geschachtelten Werts.

### <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert

Gibt den ursprünglich in diesem Objekt gespeicherten Wert zurück.

### <a name="remarks"></a>Hinweise

Ein Beispiel finden Sie unter [Boxing](../cppcx/boxing-c-cx.md).

## <a name="see-also"></a>Siehe auch

[Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)