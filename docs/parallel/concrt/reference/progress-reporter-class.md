---
title: progress_reporter-Klasse
ms.date: 11/04/2016
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
ms.openlocfilehash: bd8f50a8c9829ff9de3e2412b89aa4de88d90db6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138772"
---
# <a name="progress_reporter-class"></a>progress_reporter-Klasse

Die Status-Reporter-Klasse ermöglicht Benachrichtigungen zum Status der Berichterstellung eines bestimmten Typs. Jedes progress_reporter-Objekt ist an eine bestimmte asynchrone Aktion bzw. einen Vorgang gebunden.

## <a name="syntax"></a>Syntax

```cpp
template<typename _ProgressType>
class progress_reporter;
```

### <a name="parameters"></a>Parameter

*_ProgressType*<br/>
Der Nutzlasttyp jeder Statusbenachrichtigung, die vom Status-Reporter gemeldet wird.

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[progress_reporter](#ctor)||

### <a name="public-methods"></a>Öffentliche Methoden

|Name|BESCHREIBUNG|
|----------|-----------------|
|[Ver](#report)|Sendet einen Statusbericht an die asynchrone Aktion oder den asynchronen Vorgang, an die bzw. an den dieser Status-Reporter gebunden ist.|

## <a name="remarks"></a>Bemerkungen

Dieser Typ ist nur für Windows-Runtime-apps verfügbar.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`progress_reporter`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** ppltasks. h

**Namespace:** Parallelität

## <a name="ctor"></a>progress_reporter

```cpp
progress_reporter();
```

## <a name="report"></a>Ver

Sendet einen Statusbericht an die asynchrone Aktion oder den asynchronen Vorgang, an die bzw. an den dieser Status-Reporter gebunden ist.

```cpp
void report(const _ProgressType& val) const;
```

### <a name="parameters"></a>Parameter

*val*<br/>
Die Nutzlast, über die mit einer Statusbenachrichtigung berichtet werden soll.

## <a name="see-also"></a>Weitere Informationen

[Concurrency-Namespace](concurrency-namespace.md)
