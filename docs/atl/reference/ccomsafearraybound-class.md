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
ms.openlocfilehash: 0386092ac26e71fcf5e840594a6b07f56cc9badd
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739745"
---
# <a name="ccomsafearraybound-class"></a>CComSafeArrayBound-Klasse

Diese Klasse ist ein Wrapper für eine [SAFEARRAYBOUND](/windows/win32/api/oaidl/ns-oaidl-safearraybound) -Struktur.

## <a name="syntax"></a>Syntax

```
class CComSafeArrayBound : public SAFEARRAYBOUND
```

## <a name="members"></a>Member

### <a name="methods"></a>Methoden

|||
|-|-|
|[CComSafeArrayBound](#ccomsafearraybound)|Der Konstruktor.|
|[GetCount](#getcount)|Mit dieser Methode wird die Anzahl der Elemente zurückgegeben.|
|[GetLowerBound](#getlowerbound)|Ruft diese Methode auf, um die untere Grenze zurückzugeben.|
|[GetUpperBound](#getupperbound)|Ruft diese Methode auf, um die obere Grenze zurückzugeben.|
|[SetCount](#setcount)|Mit dieser Methode wird die Anzahl der Elemente festgelegt.|
|[SetLowerBound](#setlowerbound)|Ruft diese Methode auf, um die untere Grenze festzulegen.|

### <a name="operators"></a>Operatoren

|||
|-|-|
|[operator =](#operator_eq)|Legt den `CComSafeArrayBound` auf einen neuen Wert fest.|

## <a name="remarks"></a>Hinweise

Diese Klasse ist ein Wrapper für die `SAFEARRAYBOUND` von [CComSafeArray](../../atl/reference/ccomsafearray-class.md)verwendete Struktur. Es stellt Methoden zum Abfragen und Festlegen der oberen und unteren Grenzen einer einzelnen Dimension eines `CComSafeArray` -Objekts und der Anzahl der enthaltenen Elemente bereit. Ein mehr `CComSafeArray` dimensionales Objekt verwendet ein Array `CComSafeArrayBound` von-Objekten, eines für jede Dimension. Beachten Sie daher bei der Verwendung von Methoden wie [GetCount](#getcount), dass diese Methode nicht die Gesamtanzahl von Elementen in einem mehrdimensionalen Array zurückgibt.

**Header:** atlsafe.h

## <a name="requirements"></a>Anforderungen

**Header:** atlsafe.h

##  <a name="ccomsafearraybound"></a>CComSafeArrayBound:: CComSafeArrayBound

Der Konstruktor.

```
CComSafeArrayBound(ULONG ulCount = 0, LONG lLowerBound = 0) throw();
```

### <a name="parameters"></a>Parameter

*ulCount*<br/>
Die Anzahl der Elemente im Array.

*lLowerBound*<br/>
Die untere Grenze, von der das Array nummeriert wird.

### <a name="remarks"></a>Hinweise

Wenn von einem C++ Programm aus auf das Array zugegriffen werden soll, wird empfohlen, die untere Grenze als 0 (null) zu definieren. Es ist möglicherweise vorzuziehen, einen anderen niedrigeren Grenzwert zu verwenden, wenn das Array mit anderen Sprachen verwendet werden soll, z. b. Visual Basic.

##  <a name="getcount"></a>CComSafeArrayBound:: GetCount

Mit dieser Methode wird die Anzahl der Elemente zurückgegeben.

```
ULONG GetCount() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Elemente zurück.

### <a name="remarks"></a>Hinweise

Wenn das `CComSafeArray` zugeordnete-Objekt ein mehrdimensionales Array darstellt, gibt diese Methode nur die Gesamtzahl der Elemente in der äußersten rechten Dimension zurück. Verwenden Sie [CComSafeArray:: GetCount](../../atl/reference/ccomsafearray-class.md#getcount) zum Abrufen der Gesamtanzahl von Elementen.

##  <a name="getlowerbound"></a>CComSafeArrayBound:: GetLowerBound

Ruft diese Methode auf, um die untere Grenze zurückzugeben.

```
LONG GetLowerBound() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die untere Grenze des `CComSafeArrayBound` -Objekts zurück.

##  <a name="getupperbound"></a>CComSafeArrayBound:: GetUpperBound

Ruft diese Methode auf, um die obere Grenze zurückzugeben.

```
LONG GetUpperBound() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die obere Grenze des `CComSafeArrayBound` -Objekts zurück.

### <a name="remarks"></a>Hinweise

Die obere Grenze hängt von der Anzahl der Elemente und dem unteren gebundenen Wert ab. Wenn die untere Grenze beispielsweise 0 und die Anzahl der Elemente 10 ist, wird die obere Grenze automatisch auf 9 festgelegt.

##  <a name="operator_eq"></a>CComSafeArrayBound:: Operator =

Legt den `CComSafeArrayBound` auf einen neuen Wert fest.

```
CComSafeArrayBound& operator= (const CComSafeArrayBound& bound) throw();
CComSafeArrayBound& operator= (ULONG ulCount) throw();
```

### <a name="parameters"></a>Parameter

*binden*<br/>
Ein `CComSafeArrayBound`-Objekt.

*ulCount*<br/>
Die Anzahl der Elemente.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf das `CComSafeArrayBound` -Objekt zurück.

### <a name="remarks"></a>Hinweise

Das `CComSafeArrayBound` -Objekt kann mithilfe eines vorhandenen `CComSafeArrayBound`oder durch Angabe der Anzahl von Elementen zugewiesen werden. in diesem Fall wird die untere Grenze standardmäßig auf 0 festgelegt.

##  <a name="setcount"></a>CComSafeArrayBound:: SetCount

Mit dieser Methode wird die Anzahl der Elemente festgelegt.

```
ULONG SetCount(ULONG ulCount) throw();
```

### <a name="parameters"></a>Parameter

*ulCount*<br/>
Die Anzahl der Elemente.

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Elemente im `CComSafeArrayBound` -Objekt zurück.

##  <a name="setlowerbound"></a>CComSafeArrayBound:: setlowerbound

Ruft diese Methode auf, um die untere Grenze festzulegen.

```
LONG SetLowerBound(LONG lLowerBound) throw();
```

### <a name="parameters"></a>Parameter

*lLowerBound*<br/>
Die untere Grenze.

### <a name="return-value"></a>Rückgabewert

Gibt die neue untere Grenze des `CComSafeArrayBound` -Objekts zurück.

### <a name="remarks"></a>Hinweise

Wenn von einem visuellen C++ Programm aus auf das Array zugegriffen werden soll, wird empfohlen, die untere Grenze als 0 (null) zu definieren. Es ist möglicherweise vorzuziehen, einen anderen niedrigeren Grenzwert zu verwenden, wenn das Array mit anderen Sprachen verwendet werden soll, z. b. Visual Basic.

Die obere Grenze hängt von der Anzahl der Elemente und dem unteren gebundenen Wert ab. Wenn die untere Grenze beispielsweise 0 und die Anzahl der Elemente 10 ist, wird die obere Grenze automatisch auf 9 festgelegt.

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
