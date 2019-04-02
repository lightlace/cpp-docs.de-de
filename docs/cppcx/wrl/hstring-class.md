---
title: HString-Klasse
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString
- corewrappers/Microsoft::WRL::Wrappers::HString::Attach
- corewrappers/Microsoft::WRL::Wrappers::HString::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HString::Detach
- corewrappers/Microsoft::WRL::Wrappers::HString::Get
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
ms.openlocfilehash: 19ef11a5d33e69bb77049e450df1b386528b7f7b
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58785522"
---
# <a name="hstring-class"></a>HString-Klasse

Eine Hilfsklasse für die Verwaltung der Lebensdauer einer [HSTRING](/windows/desktop/WinRT/hstring) das RAII-Muster verwenden.

## <a name="syntax"></a>Syntax

```cpp
class HString;
```

## <a name="remarks"></a>Hinweise

Die Windows-Runtime ermöglicht den Zugriff auf die Zeichenfolgen durch [HSTRING](/windows/desktop/WinRT/hstring) behandelt. Die `HString` Klasse enthält Hilfsfunktionen und Operatoren zur Vereinfachung der Verwendung von HSTRING-Handles. Diese Klasse kann die Lebensdauer der HSTRING verarbeiten, die sie über ein RAII-Muster besitzt.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                | Beschreibung
----------------------------------- | -----------------------------------------------------
[HString::HString](#hstring)        | Initialisiert eine neue Instanz der `HString`-Klasse.
[HString::~HString](#tilde-hstring) | Zerstört die aktuelle Instanz von der `HString` Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                     | Beschreibung
---------------------------------------- | -------------------------------------------------------------------------------------------------------------
[HString::Attach](#attach)               | Ordnet die angegebene `HString` Objekt mit dem aktuellen `HString` Objekt.
[HString::CopyTo](#copyto)               | Kopiert das aktuelle `HString` Objekt zu einem HSTRING-Objekt.
[HString::Detach](#detach)               | Hebt die Zuordnung der angegebenen `HString` Objekt von seinem zugrunde liegenden Wert.
[HString::Get](#get)                     | Ruft den Wert des zugrunde liegenden HSTRING-Handles ab.
[HString::GetAddressOf](#getaddressof)   | Ruft einen Zeiger auf das zugrunde liegende HSTRING-Handle ab.
[HString::IsValid](#isvalid)             | Gibt an, ob die aktuelle `HString` Objekt gültig ist.
[HString::MakeReference](#makereference) | Erstellt eine `HStringReference` Objekt aus einem angegebenen Zeichenfolgenparameter.
[HString::Release](#release)             | Löscht den zugrunde liegenden Zeichenfolgenwert und initialisiert die aktuelle `HString` Objekt auf einen leeren Wert.
[HString::Set](#set)                     | Legt den Wert des aktuellen `HString` Objekt, das die angegebene Zeichenfolge mit Breitzeichen oder `HString` Parameter.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                         | Beschreibung
-------------------------------------------- | ----------------------------------------------------------------------------
[HString::operator=](#operator-assign)       | Verschiebt den Wert eines anderen `HString` -Objekt mit dem aktuellen `HString` Objekt.
[HString::operator==](#operator-equality)    | Gibt an, ob die zwei Parameter gleich sind.
[HString::operator!=](#operator-inequality)  | Gibt an, ob die zwei Parameter ungleich sind.
[HString::operator&lt;](#operator-less-than) | Gibt an, ob der erste Parameter kleiner als der zweite Parameter.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HString`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="tilde-hstring"></a>HString::~HString

Zerstört die aktuelle Instanz von der `HString` Klasse.

```cpp
~HString() throw()
```

## <a name="attach"></a>HString::Attach

Ordnet die angegebene `HString` Objekt mit dem aktuellen `HString` Objekt.

```cpp
void Attach(
       HSTRING hstr
       ) throw()
```

### <a name="parameters"></a>Parameter

*hstr*<br/>
Ein vorhandenes `HString`-Objekt.

## <a name="copyto"></a>HString::CopyTo

Kopiert das aktuelle `HString` Objekt zu einem HSTRING-Objekt.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Parameter

*str*<br/>
Das HSTRING, das die Kopie erhält.

### <a name="remarks"></a>Hinweise

Diese Methode ruft die [WindowsDuplicateString](/windows/desktop/api/winstring/nf-winstring-windowsduplicatestring) Funktion.

## <a name="detach"></a>HString::Detach

Hebt die Zuordnung der angegebenen `HString` Objekt von seinem zugrunde liegenden Wert.

```cpp
HSTRING Detach() throw()
```

### <a name="return-value"></a>Rückgabewert

Die zugrunde liegende `HString` Wert vor dem Trennvorgang gestartet.

## <a name="get"></a>HString::Get

Ruft den Wert des zugrunde liegenden HSTRING-Handles ab.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Rückgabewert

Der Wert des zugrunde liegenden HSTRING-Handles

## <a name="getaddressof"></a>HString::GetAddressOf

Ruft einen Zeiger auf das zugrunde liegende HSTRING-Handle ab.

```cpp
HSTRING* GetAddressOf() throw()
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das zugrunde liegende HSTRING-Handle.

### <a name="remarks"></a>Hinweise

Nach diesem Vorgang wird der Zeichenfolgenwert, der das zugrunde liegende HSTRING-Handle zerstört.

## <a name="hstring"></a>HString::HString

Initialisiert eine neue Instanz der `HString`-Klasse.

```cpp
HString() throw();
HString(HString&& other) throw();
```

### <a name="parameters"></a>Parameter

*hstr*<br/>
Ein HSTRING-Handle.

*other*<br/>
Ein vorhandenes `HString`-Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert eine neue `HString` -Objekt, das leer ist.

Der zweite Konstruktor initialisiert eine neue `HString` Objekt, das den Wert des vorhandenen *andere* Parameter, und klicken Sie dann zerstört die *andere* Parameter.

## <a name="isvalid"></a>HString::IsValid

Gibt an, ob die aktuelle `HString` Objekt leer ist oder nicht.

```cpp
bool IsValid() const throw()
```

### <a name="parameters"></a>Parameter

**"true"** Wenn die aktuelle `HString` Objekt ist nicht leer ist, andernfalls **"false"**.

## <a name="makereference"></a>HString::MakeReference

Erstellt eine `HStringReference` Objekt aus einem angegebenen Zeichenfolgenparameter.

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
Ein Vorlagenparameter, der angibt, die Größe des Ziels `HStringReference` Puffer.

*str*<br/>
Ein Verweis auf eine Zeichenfolge mit Breitzeichen.

*len*<br/>
Die maximale Länge von der *str* Parameterpuffer auf diesen Vorgang verwendet. Wenn die *Len* Parameter nicht angegeben ist, die gesamte *str* Parameter wird verwendet.

### <a name="return-value"></a>Rückgabewert

Ein `HStringReference` -Objekt, dessen Wert identisch mit dem angegebenen ist *str* Parameter.

## <a name="operator-assign"></a>Hstring:: Operator =-Operator

Verschiebt den Wert eines anderen `HString` -Objekt mit dem aktuellen `HString` Objekt.

```cpp
HString& operator=(HString&& other) throw()
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein vorhandenes `HString`-Objekt.

### <a name="remarks"></a>Hinweise

Der Wert des vorhandenen *andere* Objekt kopiert wird, mit dem aktuellen `HString` -Objekt, und klicken Sie dann die *andere* -Objekt zerstört wird.

## <a name="operator-equality"></a>Hstring:: Operator ==-Operator

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
Der erste Parameter, verglichen werden soll. *LHS* kann ein `HString` oder `HStringReference` Objekt oder ein HSTRING-Handle.

*rhs*<br/>
Der zweite Parameter, verglichen werden soll. *RS* kann ein `HString` oder `HStringReference` Objekt oder ein HSTRING-Handle.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die *Lhs* und *RS* Parameter gleich sind; andernfalls, **"false"**.

## <a name="operator-inequality"></a>Hstring::! =-Operator

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
Der erste Parameter, verglichen werden soll. *LHS* kann ein `HString` oder `HStringReference` Objekt oder ein HSTRING-Handle.

*rhs*<br/>
Der zweite Parameter, verglichen werden soll. *RS* kann ein `HString` oder `HStringReference` Objekt oder ein HSTRING-Handle.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die *Lhs* und *RS* Parameter sind nicht gleich sind, andernfalls **"false"**.

## <a name="operator-less-than"></a>Hstring::&lt; Operator

Gibt an, ob der erste Parameter kleiner als der zweite Parameter.

```cpp
inline bool operator<(
    const HString& lhs,
    const HString& rhs) throw()
```

### <a name="parameters"></a>Parameter

*lhs*<br/>
Der erste Parameter, verglichen werden soll. *LHS* möglich ein Verweis auf ein `HString`.

*rhs*<br/>
Der zweite Parameter, verglichen werden soll. *RS* möglich ein Verweis auf ein `HString`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die *Lhs* -Parameter ist kleiner als der *RS* Parameter ist, andernfalls **"false"**.

## <a name="release"></a>HString::Release

Löscht den zugrunde liegenden Zeichenfolgenwert und initialisiert die aktuelle `HString` Objekt auf einen leeren Wert.

```cpp
void Release() throw()
```

## <a name="set"></a>HString::Set

Legt den Wert des aktuellen `HString` Objekt, das die angegebene Zeichenfolge mit Breitzeichen oder `HString` Parameter.

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
Eine Zeichenfolge mit Breitzeichen.

*len*<br/>
Die maximale Länge von der *str* Parameter, der mit dem aktuellen zugewiesen ist `HString` Objekt.

*hstr*<br/>
Ein vorhandenes `HString`-Objekt.
