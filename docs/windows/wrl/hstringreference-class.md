---
title: HStringReference-Klasse
ms.date: 09/25/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::CopyTo
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::Get
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator==
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator!=
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator<
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HStringReference class
- Microsoft::WRL::Wrappers::HStringReference::CopyTo method
- Microsoft::WRL::Wrappers::HStringReference::Get method
- Microsoft::WRL::Wrappers::HStringReference::HStringReference, constructor
- Microsoft::WRL::Wrappers::HStringReference::operator= operator
- Microsoft::WRL::Wrappers::HStringReference::operator== operator
- Microsoft::WRL::Wrappers::HStringReference::operator!= operator
- Microsoft::WRL::Wrappers::HStringReference::operator< operator
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
ms.openlocfilehash: 09bf994a77bb6b7c9c9e97566ae01e02bd5070c0
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336005"
---
# <a name="hstringreference-class"></a>HStringReference-Klasse

Stellt ein HSTRING dar, das aus einer vorhandenen Zeichenfolge erstellt wird.

## <a name="syntax"></a>Syntax

```cpp
class HStringReference;
```

## <a name="remarks"></a>Hinweise

Die Lebensdauer des Hintergrundpuffers im neuen HSTRING wird nicht von der Windows-Runtime verwaltet. Der Aufrufer ordnet eine Quellzeichenfolge auf dem Stapelrahmen zu, um eine Heapzuweisung zu vermeiden und das Risiko eines Speicherverlusts auszuschließen. Außerdem muss der Aufrufer sicherstellen, dass die Quellzeichenfolge während der Lebensdauer des angefügten HSTRING unverändert bleibt. Weitere Informationen finden Sie unter [WindowsCreateStringReference-Funktion](/windows/desktop/api/winstring/nf-winstring-windowscreatestringreference).

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                    | Beschreibung
------------------------------------------------------- | -----------------------------------------------------------
[HStringReference::HStringReference](#hstringreference) | Initialisiert eine neue Instanz der `HStringReference`-Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Member                              | Beschreibung
----------------------------------- | ------------------------------------------------------------------
[HStringReference::CopyTo](#copyto) | Kopiert das aktuelle `HStringReference` Objekt zu einem HSTRING-Objekt.
[HStringReference::Get](#get)       | Ruft den Wert des zugrunde liegenden HSTRING-Handles ab.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                                  | Beschreibung
----------------------------------------------------- | ----------------------------------------------------------------------------------------------
[HStringReference::operator=](#operator-assign)       | Verschiebt den Wert eines anderen `HStringReference` -Objekt mit dem aktuellen `HStringReference` Objekt.
[HStringReference::operator==](#operator-equality)    | Gibt an, ob die zwei Parameter gleich sind.
[HStringReference::operator!=](#operator-inequality)  | Gibt an, ob die zwei Parameter ungleich sind.
[HStringReference::operator&lt;](#operator-less-than) | Gibt an, ob der erste Parameter kleiner als der zweite Parameter.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HStringReference`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="copyto"></a>HStringReference::CopyTo

Kopiert das aktuelle `HStringReference` Objekt zu einem HSTRING-Objekt.

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Parameter

*str*<br/>
Das HSTRING, das die Kopie erhält.

### <a name="remarks"></a>Hinweise

Diese Methode ruft die [WindowsDuplicateString](https://msdn.microsoft.com/library/br224634.aspx) Funktion.

## <a name="get"></a>HStringReference::Get

Ruft den Wert des zugrunde liegenden HSTRING-Handles ab.

```cpp
HSTRING Get() const throw()
```

### <a name="return-value"></a>Rückgabewert

Der Wert des zugrunde liegenden HSTRING-Handles.

## <a name="hstringreference"></a>HStringReference::HStringReference

Initialisiert eine neue Instanz der `HStringReference`-Klasse.

```cpp
template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest]) throw();

template<unsigned int sizeDest>
HStringReference(wchar_t const (&str)[ sizeDest],
                 unsigned int len) throw();

HStringReference(HStringReference&& other) throw();
```

### <a name="parameters"></a>Parameter

*sizeDest*<br/>
Ein Vorlagenparameter, der angibt, die Größe des Ziels `HStringReference` Puffer.

*str*<br/>
Ein Verweis auf eine Zeichenfolge mit Breitzeichen.

*len*<br/>
Die maximale Länge von der *str* Parameterpuffer auf diesen Vorgang verwendet. Wenn die *Len* Parameter nicht angegeben ist, die gesamte *str* Parameter wird verwendet. Wenn *Len* ist größer als *SizeDest*, *Len* nastaven NA hodnotu *SizeDest*-1.

*other*<br/>
Eine andere `HStringReference` Objekt.

### <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert eine neue `HStringReference` -Objekt, das dieselbe, als Parameter Größe *str*.

Der zweite Konstruktor initialisiert eine neue `HStringReference` -Objekt, das Größe Specifeid durch Parameter *Len*.

Der dritte Konstruktor initialisiert eine neue `HStringReference` Objekt, das den Wert des der *andere* Parameter, und dann zerstört die *andere* Parameter.

## <a name="operator-assign"></a>HStringReference::operator=

Verschiebt den Wert eines anderen `HStringReference` -Objekt mit dem aktuellen `HStringReference` Objekt.

```cpp
HStringReference& operator=(HStringReference&& other) throw()
```

### <a name="parameters"></a>Parameter

*other*<br/>
Ein vorhandenes `HStringReference`-Objekt.

### <a name="remarks"></a>Hinweise

Der Wert des vorhandenen *andere* Objekt kopiert wird, mit dem aktuellen `HStringReference` -Objekt, und klicken Sie dann die *andere* -Objekt zerstört wird.

## <a name="operator-equality"></a>HStringReference::operator==

Gibt an, ob die zwei Parameter gleich sind.

```cpp
inline bool operator==(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator==(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Parameter

*lhs*<br/>
Der erste Parameter, verglichen werden soll. *LHS* kann ein `HStringReference` Objekt oder ein HSTRING-Handle.

*rhs*<br/>
Der zweite Parameter, verglichen werden soll.  *RS* kann ein `HStringReference` Objekt oder ein HSTRING-Handle.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die *Lhs* und *RS* Parameter gleich sind; andernfalls, **"false"**.

## <a name="operator-inequality"></a>Hstringreference::! =

Gibt an, ob die zwei Parameter ungleich sind.

```cpp
inline bool operator!=(
               const HStringReference& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HSTRING& lhs,
               const HStringReference& rhs) throw()

inline bool operator!=(
               const HStringReference& lhs,
               const HSTRING& rhs) throw()
```

### <a name="parameters"></a>Parameter

*lhs*<br/>
Der erste Parameter, verglichen werden soll. *LHS* kann ein `HStringReference` Objekt oder ein HSTRING-Handle.

*rhs*<br/>
Der zweite Parameter, verglichen werden soll.  *RS* kann ein `HStringReference` Objekt oder ein HSTRING-Handle.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die *Lhs* und *RS* Parameter sind nicht gleich sind, andernfalls **"false"**.

## <a name="operator-less-than"></a>HStringReference::operator&lt;

Gibt an, ob der erste Parameter kleiner als der zweite Parameter.

```cpp
inline bool operator<(
    const HStringReference& lhs,
    const HStringReference& rhs) throw()
```

### <a name="parameters"></a>Parameter

*lhs*<br/>
Der erste Parameter, verglichen werden soll. *LHS* möglich ein Verweis auf ein `HStringReference`.

*rhs*<br/>
Der zweite Parameter, verglichen werden soll.  *RS* möglich ein Verweis auf ein `HStringReference`.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn die *Lhs* -Parameter ist kleiner als der *RS* Parameter ist, andernfalls **"false"**.
