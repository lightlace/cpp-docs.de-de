---
title: Platform::Box-Klasse
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Box
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
ms.openlocfilehash: ca8c9229d0ef5fa654f462282f257b1684984102
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742943"
---
# <a name="platformbox-class"></a>Platform::Box-Klasse

Aktiviert einen Werttyp wie `Windows::Foundation::DateTime` oder einen skalaren Typ wie `int` , der in einem `Platform::Object` -Typ gespeichert wird. Es ist normalerweise nicht erforderlich, `Box` explizit zu verwenden, da das Boxing implizit geschieht, wenn Sie einen Werttyp in `Object^`umwandeln.

### <a name="syntax"></a>Syntax

```cpp
ref class Box abstract;
```

### <a name="requirements"></a>Anforderungen

**Header:** vccorlib.h

**Namespace:** Plattform

### <a name="members"></a>Member

|Member|Beschreibung|
|------------|-----------------|
|[Box](#ctor) | Erstellt eine `Box`, die einen Wert vom angegebenen Typ kapseln kann. |
|[Operator Box&lt;const T&gt;^](#box-const-t) | Ermöglicht Boxingkonvertierungen von einer `const`-Wertklasse `T` oder `enum`-Klasse `T` in `Box<T>`. |
|[Operator Box&lt;const volatile T&gt;^](#box-const-volatile-t) | Ermöglicht Boxingkonvertierungen von einer `const volatile`-Wertklasse `T` oder einem `enum`-Typ `T` in `Box<T>`. |
|[Operator Box&lt;T&gt;^](#box-t) | Ermöglicht Boxingkonvertierungen von einer `T`-Wertklasse in `Box<T>`. |
|[Operator Box&lt;volatile T&gt;^](#box-volatile-t) | Ermöglicht Boxingkonvertierungen von einer `volatile`-Wertklasse `T` oder einem `enum`-Typ `T` in `Box<T>`. |
|[Box:: T](#t) | Ermöglicht Boxingkonvertierungen von einer `T`-Wertklasse oder `enum`-Klasse `T` in `Box<T>`. |
|[Value-Eigenschaft](#value) | Gibt den im `Box`-Objekt gekapselten Wert zurück. |

## <a name="ctor"></a> Box:: Box-Konstruktor

Erstellt eine `Box`, die einen Wert vom angegebenen Typ kapseln kann.

### <a name="syntax"></a>Syntax

```cpp
Box(T valueArg);
```

### <a name="parameters"></a>Parameter

*valueArg*<br/>
Der Typ des Werts, für den eine Boxingkonvertierung ausgeführt werden soll – beispielsweise `int`, `bool`, `float64`, `DateTime`.

## <a name="box-const-t"></a> Box:: Box&lt;const T&gt;^-Operator

Ermöglicht Boxingkonvertierungen von einer `const`-Wertklasse `T` oder `enum`-Klasse `T` in `Box<T>`.

### <a name="syntax"></a>Syntax

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Eine Wertklasse, eine Wertstruktur oder ein Enumerationstyp. Schließt die integrierten Typen in der [Standardnamespace](../cppcx/default-namespace.md).

### <a name="return-value"></a>Rückgabewert

Ein `Platform::Box<T>^` Instanz, die den ursprünglichen Wert steht in einer Verweisklasse geschachtelt.

## <a name="box-const-volatile-t"></a> Box:: Box&lt;const volatile T&gt;^-Operator

Ermöglicht Boxingkonvertierungen von einer `const volatile`-Wertklasse `T` oder einem `enum`-Typ `T` in `Box<T>`.

### <a name="syntax"></a>Syntax

```cpp
operator Box<const volatile T>^(const volatile T valueType);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Enumerationstyp, eine Wertklasse oder eine Wertstruktur. Schließt die integrierten Typen in der [Standardnamespace](../cppcx/default-namespace.md).

### <a name="return-value"></a>Rückgabewert

Ein `Platform::Box<T>^` Instanz, die den ursprünglichen Wert steht in einer Verweisklasse geschachtelt.

## <a name="box-t"></a> Box:: Box&lt;T&gt;^-Operator

Ermöglicht Boxingkonvertierungen von einer `T`-Wertklasse in `Box<T>`.

### <a name="syntax"></a>Syntax

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Enumerationstyp, eine Wertklasse oder eine Wertstruktur. Schließt die integrierten Typen in der [Standardnamespace](../cppcx/default-namespace.md).

### <a name="return-value"></a>Rückgabewert

Ein `Platform::Box<T>^` Instanz, die den ursprünglichen Wert steht in einer Verweisklasse geschachtelt.

## <a name="box-volatile-t"></a> Box:: Box&lt;volatile T&gt;^-Operator

Ermöglicht Boxingkonvertierungen von einer `volatile`-Wertklasse `T` oder einem `enum`-Typ `T` in `Box<T>`.

### <a name="syntax"></a>Syntax

```cpp
operator Box<volatile T>^(volatile T valueType);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Enumerationstyp, eine Wertklasse oder eine Wertstruktur. Schließt die integrierten Typen in der [Standardnamespace](../cppcx/default-namespace.md).

### <a name="return-value"></a>Rückgabewert

Ein `Platform::Box<T>^` Instanz, die den ursprünglichen Wert steht in einer Verweisklasse geschachtelt.

## <a name="t"></a>  Box:: T-Operator

Ermöglicht Boxingkonvertierungen von einer `T`-Wertklasse oder `enum`-Klasse `T` in `Box<T>`.

### <a name="syntax"></a>Syntax

```cpp
operator Box<T>^(T valueType);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Enumerationstyp, eine Wertklasse oder eine Wertstruktur. Schließt die integrierten Typen in der [Standardnamespace](../cppcx/default-namespace.md).

### <a name="return-value"></a>Rückgabewert

Ein `Platform::Box<T>^` Instanz, die den ursprünglichen Wert steht in einer Verweisklasse geschachtelt.

## <a name="value"></a> Box:: Value-Eigenschaft

Gibt den im `Box`-Objekt gekapselten Wert zurück.

### <a name="syntax"></a>Syntax

```cpp
virtual property T Value{
   T get();
}
```

### <a name="return-value"></a>Rückgabewert

Gibt den durch Boxing konvertierten Wert in dem Typ zurück, den er vor dem Boxing besaß.

## <a name="see-also"></a>Siehe auch

[Platform-namespace](../cppcx/platform-namespace-c-cx.md)<br/>
[Boxing](../cppcx/boxing-c-cx.md)
