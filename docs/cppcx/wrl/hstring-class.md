---
title: HString-Klasse
ms.date: 07/15/2019
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
- corewrappers/Microsoft::WRL::Wrappers::HString::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HString::Detach
- corewrappers/Microsoft::WRL::Wrappers::HString::Get
- corewrappers/Microsoft::WRL::Wrappers::HString::GetRawBuffer
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator==
- corewrappers/Microsoft::WRL::Wrappers::HString::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HString::operator<
- corewrappers/Microsoft::WRL::Wrappers::HString::Release
- corewrappers/Microsoft::WRL::Wrappers::HString::Set
- corewrappers/Microsoft::WRL::Wrappers::HString::~HString
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HString class
- Microsoft::WRL::Wrappers::HString::Attach method
- Microsoft::WRL::Wrappers::HString::CopyTo method
- Microsoft::WRL::Wrappers::HString::Detach method
- Microsoft::WRL::Wrappers::HString::Get method
- Microsoft::WRL::Wrappers::HString::GetAddressOf method
- Microsoft::WRL::Wrappers::HString::HString, constructor
- Microsoft::WRL::Wrappers::HString::IsValid method
- Microsoft::WRL::Wrappers::HString::MakeReference method
- Microsoft::WRL::Wrappers::HString::operator= operator
- Microsoft::WRL::Wrappers::HString::operator== operator
- Microsoft::WRL::Wrappers::HString::operator!= operator
- Microsoft::WRL::Wrappers::HString::operator< operator
- Microsoft::WRL::Wrappers::HString::Release method
- Microsoft::WRL::Wrappers::HString::Set method
- Microsoft::WRL::Wrappers::HString::~HString, destructor
ms.assetid: 6709dd2e-8d72-4675-8ec7-1baa7d71854d
ms.openlocfilehash: 71ebc02dc56b45e8790bfac7b7d4bac80d5f7729
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500495"
---
# <a name="hstring-class"></a>HString-Klasse

Eine Hilfsklasse zum Verwalten der Lebensdauer einer [hstring](/windows/win32/WinRT/hstring) mit dem RAII-Muster.

## <a name="syntax"></a>Syntax

```cpp
class HString;
```

## <a name="remarks"></a>Hinweise

Der Windows-Runtime ermöglicht den Zugriff auf Zeichen folgen über [hstring](/windows/win32/WinRT/hstring) -Handles. Die `HString` -Klasse stellt Hilfsfunktionen und Operatoren zur Vereinfachung der Verwendung von hstring-Handles bereit. Diese Klasse kann die Lebensdauer der hstring, die Sie besitzt, über ein RAII-Muster verarbeiten.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                | Beschreibung
----------------------------------- | -----------------------------------------------------
[HString::HString](#hstring)        | Initialisiert eine neue Instanz der `HString`-Klasse.
[Hstring:: ~ hstring](#tilde-hstring) | Zerstört die aktuelle Instanz der `HString` -Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                     | Beschreibung
---------------------------------------- | -------------------------------------------------------------------------------------------------------------
[HString::Attach](#attach)               | Ordnet das angegebene `HString` -Objekt dem aktuellen `HString` -Objekt zu.
[HString::CopyTo](#copyto)               | Kopiert das aktuelle `HString` -Objekt in ein hstring-Objekt.
[HString::Detach](#detach)               | Trennt das angegebene `HString` Objekt vom zugrunde liegenden Wert.
[HString::Get](#get)                     | Ruft den Wert des zugrunde liegenden HSTRING-Handles ab.
[HString::GetAddressOf](#getaddressof)   | Ruft einen Zeiger auf das zugrunde liegende HSTRING-Handle ab.
[HString::GetRawBuffer](#getrawbuffer)   | Ruft einen Zeiger auf die zugrunde liegenden Zeichen folgen Daten ab.
[HString::IsValid](#isvalid)             | Gibt an, ob `HString` das aktuelle-Objekt gültig ist.
[HString::MakeReference](#makereference) | Erstellt ein `HStringReference` -Objekt aus einem angegebenen Zeichen folgen Parameter.
[HString::Release](#release)             | Löscht den zugrunde liegenden Zeichen folgen Wert und initialisiert `HString` das aktuelle-Objekt in einen leeren Wert.
[HString::Set](#set)                     | Legt den Wert des aktuellen `HString` -Objekts auf die angegebene breit Zeichen-Zeichenfolge oder `HString` den angegebenen Parameter fest.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                         | Beschreibung
-------------------------------------------- | ----------------------------------------------------------------------------
[HString::operator=](#operator-assign)       | Verschiebt den Wert eines anderen `HString` -Objekts in das `HString` aktuelle-Objekt.
[HString::operator==](#operator-equality)    | Gibt an, ob die zwei Parameter gleich sind.
[Hstring:: Operator! =](#operator-inequality)  | Gibt an, ob die zwei Parameter ungleich sind.
[HString::operator&lt;](#operator-less-than) | Gibt an, ob der erste Parameter kleiner als der zweite Parameter ist.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HString`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers. h

**Namespace:** Microsoft:: WRL:: Wrapper

## <a name="tilde-hstring"></a>Hstring:: ~ hstring

Zerstört die aktuelle Instanz der `HString` -Klasse.

```cpp
~HString() throw()
```

## <a name="attach"></a>Hstring:: Attach

Ordnet das angegebene `HString` -Objekt dem aktuellen `HString` -Objekt zu.

```cpp
void Attach(
       HSTRING hstr
       ) throw()
```

### <a name="parameters"></a>Parameter

*hstr*<br/>
Ein vorhandenes `HString`-Objekt.

## <a name="copyto"></a>HString::CopyTo

Kopiert das aktuelle `HString` -Objekt in ein hstring-Objekt.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Parameter

*str*<br/>
Das HSTRING, das die Kopie erhält.

### <a name="remarks"></a>Hinweise

Diese Methode ruft die [windowsduplicatestring](/windows/win32/api/winstring/nf-winstring-windowsduplicatestring) -Funktion auf.

## <a name="detach"></a>HString::Detach

Trennt das angegebene `HString` Objekt vom zugrunde liegenden Wert.

```cpp
HSTRING Detach() throw()
```

### <a name="return-value"></a>Rückgabewert

Der zugrunde `HString` liegende Wert, bevor der Trennvorgang gestartet wurde.

## <a name="get"></a>HString::Get

Ruft den Wert des zugrunde liegenden HSTRING-Handles ab.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Rückgabewert

Der Wert des zugrunde liegenden hstring-Handles.

## <a name="getaddressof"></a>HString::GetAddressOf

Ruft einen Zeiger auf das zugrunde liegende HSTRING-Handle ab.

```cpp
HSTRING* GetAddressOf() throw()
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das zugrunde liegende hstring-handle.

### <a name="remarks"></a>Hinweise

Nach diesem Vorgang wird der Zeichen folgen Wert des zugrunde liegenden hstring-Handles zerstört.

## <a name="getrawbuffer"></a>HString::GetRawBuffer

Ruft einen Zeiger auf die zugrunde liegenden Zeichen folgen Daten ab.

```cpp
const wchar_t* GetRawBuffer(unsigned int* length) const;
```
### <a name="parameters"></a>Parameter

*Länge* Zeiger auf eine **int** -Variable, die die Länge der Daten empfängt.

### <a name="return-value"></a>Rückgabewert

Ein konstanter Zeiger auf die zugrunde liegenden Zeichen folgen Daten.


## <a name="hstring"></a>Hstring:: hstring

Initialisiert eine neue Instanz der `HString`-Klasse.

```cpp
HString() throw();
HString(HString&& other) throw();
```

### <a name="parameters"></a>Parameter

*hstr*<br/>
Ein hstring-handle.

*other*<br/>
Ein vorhandenes `HString`-Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert ein neues `HString` -Objekt, das leer ist.

Der zweite Konstruktor initialisiert ein neues `HString` -Objekt mit dem Wert des vorhandenen *anderen* Parameters und zerstört dann den *anderen* Parameter.

## <a name="isvalid"></a>HString::IsValid

Gibt an, ob `HString` das aktuelle-Objekt leer ist.

```cpp
bool IsValid() const throw()
```

### <a name="parameters"></a>Parameter

**true** , wenn das `HString` aktuelle-Objekt nicht leer ist, andernfalls **false**.

## <a name="makereference"></a>HString::MakeReference

Erstellt ein `HStringReference` -Objekt aus einem angegebenen Zeichen folgen Parameter.

```cpp
template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[ sizeDest]);

    template<unsigned int sizeDest>
    static HStringReference MakeReference(
              wchar_t const (&str)[sizeDest],
              unsigned int len);
```

### <a name="parameters"></a>Parameter

*sizeDest*<br/>
Ein Vorlagen Parameter, der die Größe des Ziel `HStringReference` Puffers angibt.

*str*<br/>
Ein Verweis auf eine Zeichenfolge mit breit Zeichen.

*Nest*<br/>
Die maximale Länge des *Str* -Parameter Puffers, der in diesem Vorgang verwendet werden soll. Wenn der *len* -Parameter nicht angegeben wird, wird der gesamte *Str* -Parameter verwendet.

### <a name="return-value"></a>Rückgabewert

Ein `HStringReference` Objekt, dessen Wert mit dem angegebenen *Str* -Parameter übereinstimmt.

## <a name="operator-assign"></a>Hstring:: Operator =-Operator

Verschiebt den Wert eines anderen `HString` -Objekts in das `HString` aktuelle-Objekt.

```cpp
HString& operator=(HString&& other) throw()
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein vorhandenes `HString`-Objekt.

### <a name="remarks"></a>Hinweise

Der Wert des vorhandenen *anderen* Objekts wird in das aktuelle `HString` Objekt kopiert, und dann wird das *andere* Objekt zerstört.

## <a name="operator-equality"></a>Hstring:: Operator = =-Operator

Gibt an, ob die zwei Parameter gleich sind.

```cpp
inline bool operator==(
               const HString& lhs,
               const HString& rhs) throw()

inline bool operator==(
                const HString& lhs,
                const HStringReference& rhs) throw()

inline bool operator==(
                const HStringReference& lhs,
                const HString& rhs) throw()

inline bool operator==(
                 const HSTRING& lhs,
                 const HString& rhs) throw()

inline bool operator==(
                 const HString& lhs,
                 const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Parameter

*lhs*<br/>
Der erste zu vergleichende Parameter. *LHS* können ein `HString` -oder `HStringReference` -Objekt oder ein hstring-Handle sein.

*rhs*<br/>
Der zweite Parameter, der verglichen werden soll. *RHS* kann ein `HString` -oder `HStringReference` -Objekt oder ein hstring-Handle sein.

### <a name="return-value"></a>Rückgabewert

**true** , wenn die Parameter *LHS* und *RHS* gleich sind. andernfalls **false**.

## <a name="operator-inequality"></a>Hstring:: Operator! =-Operator

Gibt an, ob die zwei Parameter ungleich sind.

```cpp
inline bool operator!=( const HString& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HStringReference& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HStringReference& rhs) throw()

inline bool operator!=( const HSTRING& lhs,
                        const HString& rhs) throw()

inline bool operator!=( const HString& lhs,
                        const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Parameter

*lhs*<br/>
Der erste zu vergleichende Parameter. *LHS* können ein `HString` -oder `HStringReference` -Objekt oder ein hstring-Handle sein.

*rhs*<br/>
Der zweite Parameter, der verglichen werden soll. *RHS* kann ein `HString` -oder `HStringReference` -Objekt oder ein hstring-Handle sein.

### <a name="return-value"></a>Rückgabewert

**true** , wenn die Parameter *LHS* und *RHS* nicht gleich sind. andernfalls **false**.

## <a name="operator-less-than"></a>Hstring:: Operator&lt; -Operator

Gibt an, ob der erste Parameter kleiner als der zweite Parameter ist.

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()
```

### <a name="parameters"></a>Parameter

*lhs*<br/>
Der erste zu vergleichende Parameter. *LHS* können ein Verweis auf einen `HString`sein.

*rhs*<br/>
Der zweite Parameter, der verglichen werden soll. bei *RHS* kann es sich um einen `HString`Verweis auf einen handeln.

### <a name="return-value"></a>Rückgabewert

**true** , wenn der *LHS* -Parameter kleiner als der *RHS* -Parameter ist. andernfalls **false**.

## <a name="release"></a>HString::Release

Löscht den zugrunde liegenden Zeichen folgen Wert und initialisiert `HString` das aktuelle-Objekt in einen leeren Wert.

```cpp
void Release() throw()
```

## <a name="set"></a>Hstring:: Set

Legt den Wert des aktuellen `HString` -Objekts auf die angegebene breit Zeichen-Zeichenfolge oder `HString` den angegebenen Parameter fest.

```cpp
HRESULT Set(
          const wchar_t* str) throw();
HRESULT Set(
          const wchar_t* str,
          unsigned int len
           ) throw();
HRESULT Set(
          const HSTRING& hstr
           ) throw();
```

### <a name="parameters"></a>Parameter

*str*<br/>
Eine Zeichenfolge mit breit Zeichen.

*Nest*<br/>
Die maximale Länge des *Str* -Parameters, der dem aktuellen `HString` -Objekt zugewiesen ist.

*hstr*<br/>
Ein vorhandenes `HString`-Objekt.
