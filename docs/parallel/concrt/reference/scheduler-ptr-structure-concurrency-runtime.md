---
title: Scheduler_ptr-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
dev_langs:
- C++
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea128a6122bf69735d118045eef2e8d8e323f8de
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393413"
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

Gibt den Rohzeiger auf den Planer zurück.

```
scheduler_interface* get() const;
```

### <a name="return-value"></a>Rückgabewert

##  <a name="operator_bool"></a>  scheduler_ptr:: Operator bool

Testet, dass der scheduler-Zeiger nicht NULL ist.

```operator bool() const;
```

##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;

Behave like a pointer

```
Scheduler_interface-*-Operator (const) ->;
```

### Return Value

##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor

Creates a scheduler pointer from shared_ptr to scheduler

```
explizite Scheduler_ptr (Std:: shared_ptr < Scheduler_interface > Zeitplanungsmodul);

explizite Scheduler_ptr (_In_opt_ pScheduler Scheduler_interface *);
```

### Parameters

*scheduler*<br/>
The scheduler to convert.

*pScheduler*<br/>
The scheduler pointer to convert.

## See Also

[concurrency Namespace](concurrency-namespace.md)
