---
title: scheduler_ptr Struktur
ms.date: 11/04/2016
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
ms.openlocfilehash: fd044a6255a17882c26183223f71564f98c9f7b2
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142769"
---
# <a name="scheduler_ptr-structure"></a>scheduler_ptr Struktur

Stellt einen Zeiger auf einen Planer dar. Diese Klasse ist vorhanden, um die Angabe einer freigegebenen Lebensdauer mithilfe von shared_ptr oder nur eines einfachen Verweises mithilfe eines unformatierten Zeigers zuzulassen.

## <a name="syntax"></a>Syntax

```cpp
struct scheduler_ptr;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[scheduler_ptr:: scheduler_ptr](#ctor)|Ist überladen. Erstellt einen scheduler-Zeiger von "shared_ptr" auf "scheduler".|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[scheduler_ptr:: Get](#get)|Gibt den Rohzeiger auf den Planer zurück.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[scheduler_ptr:: Operator bool](#operator_bool)|Testet, dass der scheduler-Zeiger nicht NULL ist.|
|[scheduler_ptr:: Operator-&gt;](#operator_ptr)|Verhält sich wie ein Zeiger.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`scheduler_ptr`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** pplinterface. h

**Namespace:** Parallelität

## <a name="get"></a>scheduler_ptr:: Get-Methode

Gibt den Rohdaten Zeiger auf den Scheduler zurück.

```cpp
scheduler_interface* get() const;
```

### <a name="return-value"></a>Rückgabewert

## <a name="operator_bool"></a>scheduler_ptr:: Operator bool

Testet, ob der Scheduler-Zeiger nicht NULL ist.

```cpp
operator bool() const;
```

## <a name="operator_ptr"></a>scheduler_ptr:: Operator-&gt;

Verhält sich wie ein-Zeiger.

```cpp
scheduler_interface* operator->() const;
```

### <a name="return-value"></a>Rückgabewert

## <a name="ctor"></a>scheduler_ptr:: scheduler_ptr-Konstruktor

Erstellt einen Zeit Planungs Modul-Zeiger von shared_ptr bis zum Scheduler.

```cpp
explicit scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler);
explicit scheduler_ptr(_In_opt_ scheduler_interface* pScheduler);
```

### <a name="parameters"></a>Parameter

*Scheduler*<br/>
Der zu konvertierende Scheduler.

*pscheduler*<br/>
Der zu konvertierende Scheduler-Zeiger.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
