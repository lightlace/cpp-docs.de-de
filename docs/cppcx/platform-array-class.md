---
title: 'Platform:: Array-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Array Constructors
- VCCORLIB/Namespace not found::Platform::Array::Value
dev_langs:
- C++
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a1a015a0b8b473819d870a0262c96413bf1f9f1
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103761"
---
# <a name="platformarray-class"></a>Platform::Array-Klasse

Stellt ein änderbares, eindimensionales Array dar, das über die Anwendungsbinärdateischnittstelle (ABI) empfangen und übergeben werden kann.

## <a name="syntax"></a>Syntax

```cpp
template <typename T>
private ref class Array<TArg, 1> :
    public WriteOnlyArray<TArg, 1>,
    public IBoxArray<TArg>
```

### <a name="members"></a>Member

Platform:: Array erbt alle Methoden aus [Platform:: writeonlyarray-Klasse](../cppcx/platform-writeonlyarray-class.md) und implementiert die `Value` Eigenschaft der [Platform:: iboxarray-Schnittstelle](../cppcx/platform-iboxarray-interface.md).

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Array-Konstruktoren](#ctor)|Initialisiert ein eindimensionales, änderbares Array von Typen, die gemäß der Klassenvorlagenparameter *T*.|

### <a name="methods"></a>Methoden

Finden Sie unter [Platform:: writeonlyarray-Klasse](../cppcx/platform-writeonlyarray-class.md).

### <a name="properties"></a>Eigenschaften

|||
|-|-|
|[Array::Value](#value)|Ruft ein Handle für das aktuelle Array ab.|

### <a name="remarks"></a>Hinweise

Die Array-Klasse wird versiegelt und kann nicht vererbt werden.

Der Windows-Runtime-Typsystem unterstützt nicht das Konzept von verzweigten Arrays, und Sie können nicht aus diesem Grund übergeben Sie ein IVector < Platform:: Array\<T >> als Rückgabewert oder Methodenparameter. Um ein verzweigtes Array oder eine Sequenz von Sequenzen an die ABI zu übergeben, verwenden Sie `IVector<IVector<T>^>`.

Weitere Informationen zur Verwendung von Platform:: Array finden Sie unter [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

Der Windows-Runtime-Typsystem unterstützt nicht das Konzept von verzweigten Arrays, und Sie können nicht aus diesem Grund übergeben Sie ein IVector < Platform:: Array\<T >> als Rückgabewert oder Methodenparameter. Um ein verzweigtes Array oder eine Sequenz von Sequenzen an die ABI zu übergeben, verwenden Sie `IVector<IVector<T>^>`.

Diese Klasse wird im Header "vccorlib.h" definiert, der automatisch vom Compiler eingeschlossen wird. Es ist in IntelliSense, aber nicht im Objektkatalog angezeigt, da es sich nicht um ein öffentlicher, in platform.winmd definierter Typ ist.

### <a name="requirements"></a>Anforderungen

Compileroption: **/ZW**

## <a name="ctor"></a>  Array-Konstruktoren

Initialisiert ein eindimensionales, änderbares Array von Typen, die gemäß der Klassenvorlagenparameter *T*.

## <a name="syntax"></a>Syntax

```cpp
Array(unsigned int size);
Array(T* data, unsigned int size);
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Klassenvorlagenparameter.

*size*<br/>
Die Anzahl der Elemente im Array.

*data*<br/>
Ein Zeiger auf ein Array von Daten des Typs `T`, der verwendet wird, um dieses Arrayobjekt zu initialisieren.

### <a name="remarks"></a>Hinweise

Weitere Informationen zum Erstellen von Instanzen von Platform:: Array finden Sie unter [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="get"></a>  Array:: Get-Methode

Ruft einen Verweis auf das Arrayelement an der angegebenen Indexposition ab.

## <a name="syntax"></a>Syntax

```cpp
T& get(unsigned int index)  const;
```

#### <a name="parameters"></a>Parameter

*index*<br/>
Ein nullbasierter Index, der ein Element im Array identifiziert. Der minimale Index ist 0 und der maximale Index ist der Wert von der `size` Parameter in der [Arraykonstruktor](#ctor).

### <a name="return-value"></a>Rückgabewert

Das durch den `index`-Parameter spezifizierte Arrayelement.

## <a name="value"></a>  Array:: Value-Eigenschaft

Ruft ein Handle für das aktuelle Array ab.

## <a name="syntax"></a>Syntax

```cpp
property Array^ Value;
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für das aktuelle Array.

## <a name="see-also"></a>Siehe auch

[Platform-namespace](../cppcx/platform-namespace-c-cx.md)<br/>
[Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)