---
title: runtime_exception-Klasse
ms.date: 03/27/2019
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
ms.openlocfilehash: 024ede0f05dfd646bcebe7acd2cfb86b5c54f6d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352727"
---
# <a name="runtimeexception-class"></a>runtime_exception-Klasse

Der Basistyp für Ausnahmen in der C++ Accelerated Massive Parallelism (AMP)-Bibliothek.

### <a name="syntax"></a>Syntax

```
class runtime_exception : public std::exception;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Runtime_exception-Konstruktor](#ctor)|Initialisiert eine neue Instanz der `runtime_exception`-Klasse.|
|[~ Runtime_exception-Destruktor](#dtor)|Zerstört das `runtime_exception`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[get_error_code](#get_error_code)|Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[operator=](#operator_eq)|Kopiert den Inhalt des angegebenen `runtime_exception`-Objekts in dieses Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`exception`

`runtime_exception`

## <a name="requirements"></a>Anforderungen

**Header:** amprt.h

**Namespace:** Parallelität

## <a name="ctor"></a>  Runtime_exception-Konstruktor

Initialisiert eine neue Instanz der Klasse.

### <a name="syntax"></a>Syntax

```
runtime_exception(
    const char * _Message,
    HRESULT _Hresult ) throw();

explicit runtime_exception(
    HRESULT _Hresult ) throw();

runtime_exception(
    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Parameter

*_Message*<br/>
Eine Beschreibung des Fehlers, das diese Ausnahme verursacht hat.

*_Hresult*<br/>
Der HRESULT-Wert des Fehlers, der diese Ausnahme verursacht hat.

*_Other*<br/>
Das zu kopierende `runtime_exception`-Objekt.

### <a name="return-value"></a>Rückgabewert

Das `runtime_exception`-Objekt.

## <a name="dtor"></a>  ~ Runtime_exception-Destruktor

Zerstört das Objekt.

### <a name="syntax"></a>Syntax

```
virtual ~runtime_exception() throw();
```

## <a name="geterrorcode"></a>get_error_code

Gibt den Fehlercode zurück, der die Ausnahme verursacht hat.

### <a name="syntax"></a>Syntax

```
HRESULT get_error_code() const throw();
```

### <a name="return-value"></a>Rückgabewert

Der HRESULT-Wert des Fehlers, der diese Ausnahme verursacht hat.

## <a name="operator_eq"></a> operator=
  Kopiert den Inhalt des angegebenen `runtime_exception`-Objekts in dieses Objekt.

### <a name="syntax"></a>Syntax

```
runtime_exception & operator= (    const runtime_exception & _Other ) throw();
```

### <a name="parameters"></a>Parameter

*_Other*<br/>
Das zu kopierende `runtime_exception`-Objekt.

### <a name="return-value"></a>Rückgabewert

Ein Verweis auf das `runtime_exception`-Objekt.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
