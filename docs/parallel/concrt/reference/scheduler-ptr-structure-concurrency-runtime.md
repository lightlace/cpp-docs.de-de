---
title: Scheduler_ptr-Struktur
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: 2373fe3bc8cac501d1b6b32ca66996eff47ba6f3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180732"
---
# <a name="schedulerptr-structure"></a>Scheduler_ptr-Struktur

Stellt einen Zeiger auf einen Planer dar. Diese Klasse existiert, um die Spezifikation einer freigegebenen Lebensdauer mithilfe von "shared_ptr" oder nur eines einfachen Verweises mit unformatierten Zeigers zu ermöglichen.

## <a name="syntax"></a>Syntax

```
struct scheduler_ptr;
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[scheduler_ptr::scheduler_ptr](#ctor)|Überladen. Erstellt einen scheduler-Zeiger von "shared_ptr" auf "scheduler".|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[scheduler_ptr::get](#get)|Gibt den Rohzeiger auf den Planer zurück.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[scheduler_ptr::operator bool](#operator_bool)|Testet, dass der scheduler-Zeiger nicht NULL ist.|
|[scheduler_ptr::operator-&gt;](#operator_ptr)|Verhält sich wie ein Zeiger.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`scheduler_ptr`

## <a name="requirements"></a>Anforderungen

**Header:** pplinterface.h

**Namespace:** Parallelität

##  <a name="get"></a>  scheduler_ptr:: Get-Methode

Gibt den rohzeiger auf den Planer zurück.

```
scheduler_interface* get() const;
```

### <a name="return-value"></a>Rückgabewert

##  <a name="operator_bool"></a>  scheduler_ptr:: Operator bool

Testet, ob der Scheduler-Zeiger nicht Null ist.

```
operator bool() const;
```

##  <a name="operator_ptr"></a>  scheduler_ptr:: Operator-&gt;

Verhält sich wie ein Zeiger.

```
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>Rückgabewert

##  <a name="ctor"></a>  scheduler_ptr:: scheduler_ptr-Konstruktor

Erstellt einen Scheduler-Zeiger von "shared_ptr" Scheduler an.

```
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>Parameter

*scheduler*<br/>
Der Planer zu konvertieren.

*pScheduler*<br/>
Der Scheduler-Zeiger konvertiert werden soll.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
