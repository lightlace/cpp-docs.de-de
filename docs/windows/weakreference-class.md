---
title: WeakReference-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference
- implements/Microsoft::WRL::Details::WeakReference::DecrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::IncrementStrongReference
- implements/Microsoft::WRL::Details::WeakReference::Resolve
- implements/Microsoft::WRL::Details::WeakReference::SetUnknown
- implements/Microsoft::WRL::Details::WeakReference::~WeakReference
- implements/Microsoft::WRL::Details::WeakReference::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::WeakReference class
- Microsoft::WRL::Details::WeakReference::DecrementStrongReference method
- Microsoft::WRL::Details::WeakReference::IncrementStrongReference method
- Microsoft::WRL::Details::WeakReference::Resolve method
- Microsoft::WRL::Details::WeakReference::SetUnknown method
- Microsoft::WRL::Details::WeakReference::~WeakReference, destructor
- Microsoft::WRL::Details::WeakReference::WeakReference, constructor
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7ff2f2b0e329e30ef73b82a8f1fea969eb7c31f1
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2018
ms.locfileid: "48239831"
---
# <a name="weakreference-class"></a>WeakReference-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
class WeakReference;
```

## <a name="remarks"></a>Hinweise

Stellt eine *schwachen Verweis* , die verwendet werden kann, mit der Windows-Runtime oder ein klassisches COM verwenden. Ein schwacher Verweis repräsentiert ein Objekt, auf das möglicherweise zugegriffen werden kann.

Ein `WeakReference` -Objekt verwaltet eine *starken Verweis*, dies ist ein Zeiger auf ein Objekt, und ein *starken Verweiszähler*, dies entspricht der Anzahl von Kopien der starke Verweis, die von verteilt wurden die `Resolve()` Methode. Obwohl die Anzahl der starken Verweis ungleich NULL ist, der starke Verweis gültig ist und das Objekt zugegriffen werden kann. Wird die Anzahl der starken Verweis auf 0 (null), wird der starke Verweis ungültig ist, und das Objekt kann nicht zugegriffen werden.

Ein `WeakReference` Objekt wird normalerweise verwendet, um ein Objekt darstellt, dessen Vorhandensein durch einen externen Thread oder Anwendung gesteuert wird. Erstellen Sie z. B. eine `WeakReference` Objekt aus einem Verweis auf ein Dateiobjekt. Solange die Datei geöffnet ist, ist der starke Verweis gültig. Wenn die Datei aber geschlossen wird, wird der starke Verweis ungültig.

Die `WeakReference` Methoden sind threadsicher.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                                                  | Beschreibung
----------------------------------------------------- | ---------------------------------------------------------------------------
[WeakReference::WeakReference](#weakreference)        | Initialisiert eine neue Instanz der `WeakReference`-Klasse.
[WeakReference:: ~ WeakReference](#tilde-weakreference) | Hebt die Initialisierung (löscht) der aktuellen Instanz von der `WeakReference` Klasse.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                                 | Beschreibung
-------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[WeakReference:: Decrementstrongreference](#decrementstrongreference) | Dekrementiert den starken Verweiszähler des aktuellen `WeakReference` Objekt.
[WeakReference:: Incrementstrongreference](#incrementstrongreference) | Inkrementiert die Anzahl der starken Verweis des aktuellen `WeakReference` Objekt.
[WeakReference:: Resolve](#resolve)                                   | Legt den angegebenen Zeiger auf den aktuellen Wert der starken Verweis fest, wenn die Anzahl der starken Verweis ungleich NULL ist.
[WeakReference:: Setunknown](#setunknown)                             | Den starken Verweis des aktuellen legt `WeakReference` Objekt, das den angegebenen Schnittstellenzeiger auf.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`WeakReference`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="tilde-weakreference"></a>WeakReference:: ~ WeakReference

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
virtual ~WeakReference();
```

### <a name="return-value"></a>Rückgabewert

### <a name="remarks"></a>Hinweise

Hebt die Initialisierung der aktuellen Instanz von der `WeakReference` Klasse.

## <a name="decrementstrongreference"></a>WeakReference:: Decrementstrongreference

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
ULONG DecrementStrongReference();
```

### <a name="remarks"></a>Hinweise

Dekrementiert den starken Verweiszähler des aktuellen `WeakReference` Objekt.

Die Anzahl der starken Verweis auf 0 (null) ist, wird der starke Verweis als festgelegt `nullptr`.

### <a name="return-value"></a>Rückgabewert

Die Anzahl verringert starken Verweis.

## <a name="incrementstrongreference"></a>WeakReference:: Incrementstrongreference

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
ULONG IncrementStrongReference();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl inkrementiert starken Verweis.

### <a name="remarks"></a>Hinweise

Inkrementiert die Anzahl der starken Verweis des aktuellen `WeakReference` Objekt.

## <a name="resolve"></a>WeakReference:: Resolve

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
STDMETHOD(Resolve)  
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Eine Schnittstellen-ID.

*ppvObject*<br/>
Wenn dieser Vorgang abgeschlossen ist, eine Kopie der aktuellen starken Verweis, wenn die Anzahl der starken Verweis ungleich NULL ist.

### <a name="return-value"></a>Rückgabewert

- S_OK, wenn dieser Vorgang erfolgreich ist und die Anzahl der starken Verweis ist 0 (null). Die *PpvObject* Parametersatz zu `nullptr`.

- S_OK, wenn dieser Vorgang erfolgreich ist und die Anzahl der starken Verweis ist ungleich NULL. Die *PpvObject* Parameter auf der starke Verweis festgelegt ist.

- Andernfalls Fehler ein HRESULT, das den Grund angibt, diesen Vorgang.

### <a name="remarks"></a>Hinweise

Legt den angegebenen Zeiger auf den aktuellen Wert der starken Verweis fest, wenn die Anzahl der starken Verweis ungleich NULL ist.

## <a name="setunknown"></a>WeakReference:: Setunknown

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
void SetUnknown(
   _In_ IUnknown* unk
);
```

### <a name="parameters"></a>Parameter

*UNK*<br/>
Ein Zeiger auf die `IUnknown` -Schnittstelle eines Objekts.

### <a name="remarks"></a>Hinweise

Den starken Verweis des aktuellen legt `WeakReference` Objekt, das den angegebenen Schnittstellenzeiger auf.

## <a name="weakreference"></a>WeakReference:: WeakReference

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
WeakReference();
```

### <a name="remarks"></a>Hinweise

Initialisiert eine neue Instanz der `WeakReference`-Klasse.

Der starke Verweiszeiger für die `WeakReference` Objekt wird initialisiert, um `nullptr`, und die Anzahl der starken Verweis auf 1 initialisiert wird.
