---
title: Platform::ArrayReference-Klasse
ms.date: 10/16/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ArrayReference::ArrayReference
helpviewer_keywords:
- Platform::ArrayReference Class
ms.assetid: 9ab3b15e-8a60-4600-8fcb-7d6c86284f4b
ms.openlocfilehash: f7e587902f1c99b294ed79255397aeffccee26b5
ms.sourcegitcommit: 8178d22701047d24f69f10d01ba37490e3d67241
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72587924"
---
# <a name="platformarrayreference-class"></a>Platform::ArrayReference-Klasse

`ArrayReference` ist ein Optimierungstyp, den Sie als Ersatz für [Platform::Array^](../cppcx/platform-array-class.md) in den Eingabeparametern verwenden können, wenn Sie ein Array im C-Format mit Eingabedaten füllen möchten.

## <a name="syntax"></a>Syntax

```cpp
class ArrayReference
```

### <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|-Name|Beschreibung|
|----------|-----------------|
|[Arrayreference:: arrayreference](#ctor)|Initialisiert eine neue Instanz der `ArrayReference` -Klasse.|

### <a name="public-operators"></a>Öffentliche Operatoren

|-Name|Beschreibung|
|----------|-----------------|
|[ArrayReference::operator()-Operator](#operator-call)|Konvertiert diesen `ArrayReference` in ein `Platform::Array<T>^*`-Element.|
|[ArrayReference::operator=-Operator](#operator-assign)|Weist dieser Instanz den Inhalt von einem anderen `ArrayReference` zu.|

## <a name="exceptions"></a>Ausnahmen

### <a name="remarks"></a>Hinweise

Mit `ArrayReference` zum Auffüllen eines Arrays im C-Format, vermeiden Sie den zusätzlichen Kopiervorgang, der dadurch aufgerufen würde, zunächst in eine `Platform::Array` -Variable zu kopieren, und dann in einem zweiten Schritt in das Array im C-Format. Bei Verwendung von `ArrayReference`, entsteht nur ein Kopiervorgang. Ein Codebeispiel finden Sie unter [Array und beschreiteonlyarray](../cppcx/array-and-writeonlyarray-c-cx.md).

### <a name="requirements"></a>Anforderungen

**Mindestens unterstützter Client:** Windows 8

**Mindestens unterstützter Server:** Windows Server 2012

**Namespace:** Platform

**Header:** vccorlib.h

## <a name="ctor"></a>Arrayreference:: arrayreference-Konstruktor

Initialisiert eine neue Instanz der [Platform:: arrayreference](../cppcx/platform-arrayreference-class.md) -Klasse.

### <a name="syntax"></a>Syntax

```cpp
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);
ArrayReference(ArrayReference&& otherArg)
```

### <a name="parameters"></a>Parameter

*dataarg*<br/>
Ein Zeiger auf die Arraydaten.

*sizearg*<br/>
Die Anzahl von Elementen im Quellarray.

*otherarg*<br/>
Ein `ArrayReference`-Objekt, dessen Daten zum Initialisieren der neuen Instanz verschoben werden.

### <a name="remarks"></a>Hinweise

## <a name="operator-assign"></a>Arrayreference:: Operator =-Operator

Weist das angegebene Objekt dem aktuellen [Platform:: arrayreference](../cppcx/platform-arrayreference-class.md) -Objekt mithilfe der Move-Semantik zu.

### <a name="syntax"></a>Syntax

```cpp
ArrayReference& operator=(ArrayReference&& otherArg);
```

### <a name="parameters"></a>Parameter

*otherarg*<br/>
Das zum aktuellen `ArrayReference`-Objekt verschobene Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf ein Objekt des Typs `ArrayReference`.

### <a name="remarks"></a>Hinweise

`Platform::ArrayReference` ist eine Standard-C++-Klassenvorlage, keine Verweisklasse.

## <a name="operator-call"></a>Arrayreference:: Operator ()-Operator

Konvertiert das aktuelle [Platform:: arrayreference](../cppcx/platform-arrayreference-class.md) -Objekt zurück in eine [Platform:: Array](../cppcx/platform-array-class.md) -Klasse.

### <a name="syntax"></a>Syntax

```cpp
Array<TArg>^ operator ();
```

### <a name="return-value"></a>Rückgabewert

Ein Handle für das Objekt des Typs `Array<TArg>^`

### <a name="remarks"></a>Hinweise

[Platform:: arrayreference](../cppcx/platform-arrayreference-class.md) ist eine Standard C++ Klassen Vorlage, und [Platform:: Array](../cppcx/platform-array-class.md) ist eine Verweis Klasse.

## <a name="see-also"></a>Siehe auch

[Plattformnamespace](../cppcx/platform-namespace-c-cx.md)
