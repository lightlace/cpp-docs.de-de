---
title: CComSafeArrayBound-Klasse
ms.date: 05/06/2019
f1_keywords:
- CComSafeArrayBound
- ATLSAFE/ATL::CComSafeArrayBound
- ATLSAFE/ATL::GetCount
- ATLSAFE/ATL::GetLowerBound
- ATLSAFE/ATL::GetUpperBound
- ATLSAFE/ATL::SetCount
- ATLSAFE/ATL::SetLowerBound
helpviewer_keywords:
- CComSafeArrayBound class
ms.assetid: dd6299db-5f84-4630-bbf0-f5add5318437
ms.openlocfilehash: 6d4650273661c0ce40558a37ef02bb2a3ff81809
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221148"
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound-Klasse

Diese Klasse ist ein Wrapper für eine [SAFEARRAYBOUND](/windows/desktop/api/oaidl/ns-oaidl-tagsafearraybound) Struktur.

## <a name="syntax"></a>Syntax

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[CComSafeArrayBound](#ccomsafearraybound)|Der Konstruktor.|
|[GetCount](#getcount)|Rufen Sie diese Methode, um die Anzahl der Elemente zurück.|
|[GetLowerBound](#getlowerbound)|Rufen Sie diese Methode, um die untere Grenze zurück.|
|[GetUpperBound](#getupperbound)|Rufen Sie diese Methode, um die obere Grenze zurück.|
|[SetCount](#setcount)|Rufen Sie diese Methode, um die Anzahl der Elemente festlegen.|
|[SetLowerBound](#setlowerbound)|Rufen Sie diese Methode, um die untere Grenze festgelegt.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator =](#operator_eq)|Legt die `CComSafeArrayBound` auf einen neuen Wert.|

## <a name="remarks"></a>Hinweise

Diese Klasse ist ein Wrapper für die `SAFEARRAYBOUND` vom verwendete Struktur ["CComSafeArray"](../../atl/reference/ccomsafearray-class.md). Es bietet Methoden zum Abfragen und Festlegen der oberen und unteren Grenzen einer einzelnen Dimension von einem `CComSafeArray` -Objekt und die Anzahl der enthaltenen Elemente. Ein mehrdimensionales `CComSafeArray` Objekt verwendet ein Array von `CComSafeArrayBound` Objekten, jeweils eines für jede Dimension. Aus diesem Grund bei Verwendung von Methoden wie z. B. [GetCount](#getcount), beachten Sie, dass diese Methode nicht die Gesamtzahl der Elemente in einem mehrdimensionalen Array zurückgibt.

**Header:** atlsafe.h

## <a name="requirements"></a>Anforderungen

**Header:** atlsafe.h

##  <a name="ccomsafearraybound"></a>  CComSafeArrayBound::CComSafeArrayBound

Der Konstruktor.

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>Parameter

*ulCount*<br/>
Die Anzahl der Elemente im Array.

*lLowerBound*<br/>
Die untere Grenze, von dem das Array nummeriert wird.

### <a name="remarks"></a>Hinweise

Wenn das Array ist, über Zugriff auf eine C++ Programm, es wird empfohlen, dass die untere Grenze 0 definiert werden. Es kann vorteilhafter sein, einen andere Untergrenze-Wert verwenden, wenn das Array ist, die mit anderen Sprachen wie Visual Basic verwendet werden.

##  <a name="getcount"></a>  CComSafeArrayBound::GetCount

Rufen Sie diese Methode, um die Anzahl der Elemente zurück.

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Elemente zurück.

### <a name="remarks"></a>Hinweise

Wenn die zugeordnete `CComSafeArray` Objekt darstellt, ein mehrdimensionales Array, das diese Methode gibt nur die Gesamtanzahl der Elemente in die Dimension ganz rechts zurück. Verwendung [CComSafeArray::GetCount](../../atl/reference/ccomsafearray-class.md#getcount) zum Abrufen der Gesamtanzahl der Elemente.

##  <a name="getlowerbound"></a>  CComSafeArrayBound::GetLowerBound

Rufen Sie diese Methode, um die untere Grenze zurück.

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die untere Grenze des der `CComSafeArrayBound` Objekt.

##  <a name="getupperbound"></a>  CComSafeArrayBound::GetUpperBound

Rufen Sie diese Methode, um die obere Grenze zurück.

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die obere Grenze der `CComSafeArrayBound` Objekt.

### <a name="remarks"></a>Hinweise

Die obere Grenze hängt von der Anzahl von Elementen und den Wert für die untere Grenze. Beispielsweise wird, wenn die untere Grenze 0 ist, und die Anzahl der Elemente 10 ist, die obere Grenze automatisch auf 9 festgelegt werden.

##  <a name="operator_eq"></a>  CComSafeArrayBound::operator =

Legt die `CComSafeArrayBound` auf einen neuen Wert.

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>Parameter

*bound*<br/>
Ein `CComSafeArrayBound`-Objekt.

*ulCount*<br/>
Die Anzahl der Elemente.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die `CComSafeArrayBound` Objekt.

### <a name="remarks"></a>Hinweise

Die `CComSafeArrayBound` Objekt kann zugewiesen werden, mithilfe eines vorhandenen `CComSafeArrayBound`, oder durch Angabe der Anzahl von Elementen, in dem Fall die untere Grenze wird standardmäßig auf 0 festgelegt.

##  <a name="setcount"></a>  CComSafeArrayBound::SetCount

Rufen Sie diese Methode, um die Anzahl der Elemente festlegen.

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>Parameter

*ulCount*<br/>
Die Anzahl der Elemente.

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Elemente in der `CComSafeArrayBound` Objekt.

##  <a name="setlowerbound"></a>  CComSafeArrayBound::SetLowerBound

Rufen Sie diese Methode, um die untere Grenze festgelegt.

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>Parameter

*lLowerBound*<br/>
Die untere Grenze.

### <a name="return-value"></a>Rückgabewert

Gibt die neue untere Grenze der `CComSafeArrayBound` Objekt.

### <a name="remarks"></a>Hinweise

Wenn das Array ist aus einem Visual C++-Programm zugegriffen werden, empfiehlt es sich, dass die untere Grenze 0 definiert werden. Es kann vorteilhafter sein, einen andere Untergrenze-Wert verwenden, wenn das Array ist, die mit anderen Sprachen wie Visual Basic verwendet werden.

Die obere Grenze hängt von der Anzahl von Elementen und den Wert für die untere Grenze. Beispielsweise wird, wenn die untere Grenze 0 ist, und die Anzahl der Elemente 10 ist, die obere Grenze automatisch auf 9 festgelegt werden.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
