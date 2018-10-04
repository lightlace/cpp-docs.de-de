---
title: ComPtrRef-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::ComPtrRef
- client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf
- client/Microsoft::WRL::Details::ComPtrRef::operator==
- client/Microsoft::WRL::Details::ComPtrRef::operator!=
- client/Microsoft::WRL::Details::ComPtrRef::operator InterfaceType**
- client/Microsoft::WRL::Details::ComPtrRef::operator*
- client/Microsoft::WRL::Details::ComPtrRef::operator T*
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
- client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::ComPtrRef class
- Microsoft::WRL::Details::ComPtrRef::ComPtrRef, constructor
- Microsoft::WRL::Details::ComPtrRef::GetAddressOf method
- Microsoft::WRL::Details::ComPtrRef::operator== operator
- Microsoft::WRL::Details::ComPtrRef::operator!= operator
- Microsoft::WRL::Details::ComPtrRef::operator InterfaceType** operator
- Microsoft::WRL::Details::ComPtrRef::operator* operator
- Microsoft::WRL::Details::ComPtrRef::operator T* operator
- Microsoft::WRL::Details::ComPtrRef::operator void** operator
- Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf method
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a674d63c52f6f204d0bb69c69cd5814cd6d9761a
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788941"
---
# <a name="comptrref-class"></a>ComPtrRef-Klasse

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <typename T>
class ComPtrRef : public ComPtrRefBase<T>;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein [ComPtr\<T >](../windows/comptr-class.md) Typ oder einem Typ abgeleitet ist, nicht nur die Schnittstelle der `ComPtr`.

## <a name="remarks"></a>Hinweise

Stellt einen Verweis auf ein Objekt des Typs `ComPtr<T>`.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

Name                               | Beschreibung
---------------------------------- | -------------------------------------------------------------------------------------------------------------
[Comptrref:: Comptrref](#comptrref) | Initialisiert eine neue Instanz der dem `ComPtrRef` Klasse aus dem angegebenen Zeiger auf einen anderen `ComPtrRef` Objekt.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                         | Beschreibung
------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------
[Comptrref:: Getaddressof](#getaddressof)                     | Ruft die Adresse eines Zeigers auf die Schnittstelle, die vom aktuellen `ComPtrRef` Objekt.
[Comptrref:: Releaseandgetaddressof](#releaseandgetaddressof) | Löscht die aktuelle `ComPtrRef` Objekt und gibt einen Zeiger-auf-ein-Zeiger auf die Schnittstelle, die durch dargestellt wurde die `ComPtrRef` Objekt.

### <a name="public-operators"></a>Öffentliche Operatoren

Name                                                                     | Beschreibung
------------------------------------------------------------------------ | -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[Comptrref:: Operator InterfaceType **](#operator-interfacetype-star-star) | Löscht die aktuelle `ComPtrRef` Objekt und gibt einen Zeiger-auf-ein-Zeiger auf die Schnittstelle, die durch dargestellt wurde die `ComPtrRef` Objekt.
[Comptrref:: T *](#operator-t-star)                               | Gibt den Wert des der [Ptr_](../windows/comptrrefbase-ptr-data-member.md) -Datenmember des aktuellen ComPtrRef-Objekts.
[Comptrref:: Operator Void **](#operator-void-star-star)                   | Löscht die aktuelle `ComPtrRef` Objekt, wandelt der Zeiger auf die Schnittstelle, die durch dargestellt wurde die `ComPtrRef` -Objekt als eine Zeiger-auf-Zeiger-auf `void`, und klicken Sie dann die Cast-Zeiger zurückgibt.
[Comptrref:: *](#operator-star)                                   | Ruft ab, der Zeiger auf die Schnittstelle, die vom aktuellen `ComPtrRef` Objekt.
[Comptrref:: ==](#operator-equality)                              | Gibt an, ob zwei `ComPtrRef`-Objekte gleich sind.
[Comptrref::! =](#operator-inequality)                            | Gibt an, ob zwei `ComPtrRef`-Objekte ungleich sind.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="comptrref"></a>Comptrref:: Comptrref

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
ComPtrRef(
   _In_opt_ T* ptr
);
```

### <a name="parameters"></a>Parameter

*ptr*<br/>
Der zugrunde liegenden Wert eines anderen `ComPtrRef` Objekt.

### <a name="remarks"></a>Hinweise

Initialisiert eine neue Instanz der dem `ComPtrRef` Klasse aus dem angegebenen Zeiger auf einen anderen `ComPtrRef` Objekt.

## <a name="getaddressof"></a>Comptrref:: Getaddressof

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
InterfaceType* const * GetAddressOf() const;
```

### <a name="return-value"></a>Rückgabewert

Adresse eines Zeigers auf die Schnittstelle, die vom aktuellen `ComPtrRef` Objekt.

### <a name="remarks"></a>Hinweise

Ruft die Adresse eines Zeigers auf die Schnittstelle, die vom aktuellen `ComPtrRef` Objekt.

## <a name="operator-equality"></a>Comptrref:: ==

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)  
);

bool operator==(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator==(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator==(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Parameter

*a*<br/>
Ein Verweis auf ein `ComPtrRef`-Objekt.

*b*<br/>
Ein Verweis auf einen anderen `ComPtrRef` Objekt oder ein Zeiger auf einen anonymen Typ (`void*`).

### <a name="return-value"></a>Rückgabewert

Der erste Operator ergibt `true` Wenn Objekt *eine* Objekt entspricht *b*ist, andernfalls `false`.

Führen Sie die zweite und dritte Operator `true` Wenn Objekt *eine* gleich `nullptr`ist, andernfalls `false`.

Die vierten und fünften-Operatoren ergeben `true` Wenn Objekt *eine* Objekt entspricht *b*ist, andernfalls `false`.

### <a name="remarks"></a>Hinweise

Gibt an, ob zwei `ComPtrRef`-Objekte gleich sind.

## <a name="operator-inequality"></a>Comptrref::! =

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   const Details::ComPtrRef<ComPtr<U>>& b
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   decltype(__nullptr)  
);

bool operator!=(
   decltype(__nullptr),
   const Details::ComPtrRef<ComPtr<T>>& a
);

bool operator!=(
   const Details::ComPtrRef<ComPtr<T>>& a,
   void* b
);

bool operator!=(
   void* b,
   const Details::ComPtrRef<ComPtr<T>>& a
);
```

### <a name="parameters"></a>Parameter

*a*<br/>
Ein Verweis auf ein `ComPtrRef`-Objekt.

*b*<br/>
Ein Verweis auf einen anderen `ComPtrRef` Objekt oder ein Zeiger auf ein anonymes Objekt (`void*`).

### <a name="return-value"></a>Rückgabewert

Der erste Operator ergibt `true` Wenn Objekt *eine* ist nicht gleich Objekt *b*ist, andernfalls `false`.

Führen Sie die zweite und dritte Operator `true` Wenn Objekt *eine* ist nicht gleich `nullptr`ist, andernfalls `false`.

Die vierten und fünften-Operatoren ergeben `true` Wenn Objekt *eine* ist nicht gleich Objekt *b*ist, andernfalls `false`.

### <a name="remarks"></a>Hinweise

Gibt an, ob zwei `ComPtrRef`-Objekte ungleich sind.

## <a name="operator-interfacetype-star-star"></a>Comptrref:: Operator InterfaceType **

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
operator InterfaceType**();
```

### <a name="remarks"></a>Hinweise

Löscht die aktuelle `ComPtrRef` Objekt und gibt einen Zeiger-auf-ein-Zeiger auf die Schnittstelle, die durch dargestellt wurde die `ComPtrRef` Objekt.

## <a name="operator-star"></a>Comptrref:: *

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
InterfaceType* operator *();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf die Schnittstelle, die vom aktuellen `ComPtrRef` Objekt.

### <a name="remarks"></a>Hinweise

Ruft ab, der Zeiger auf die Schnittstelle, die vom aktuellen `ComPtrRef` Objekt.

## <a name="operator-t-star"></a>Comptrref:: T *

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
operator T*();
```

### <a name="remarks"></a>Hinweise

Gibt den Wert des der [Ptr_](../windows/comptrrefbase-ptr-data-member.md) -Datenmember des aktuellen `ComPtrRef` Objekt.

## <a name="operator-void-star-star"></a>Comptrref:: "void"\*\*

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
operator void**() const;
```

### <a name="remarks"></a>Hinweise

Löscht die aktuelle `ComPtrRef` Objekt, wandelt der Zeiger auf die Schnittstelle, die durch dargestellt wurde die `ComPtrRef` -Objekt als eine Zeiger-auf-Zeiger-auf `void`, und klicken Sie dann die Cast-Zeiger zurückgibt.

## <a name="releaseandgetaddressof"></a>Comptrref:: Releaseandgetaddressof

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf die Schnittstelle, die dargestellt wird, wurde von der gelöschten `ComPtrRef` Objekt.

### <a name="remarks"></a>Hinweise

Löscht die aktuelle `ComPtrRef` Objekt und gibt einen Zeiger-auf-ein-Zeiger auf die Schnittstelle, die durch dargestellt wurde die `ComPtrRef` Objekt.
