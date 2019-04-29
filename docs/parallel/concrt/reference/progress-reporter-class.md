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
ms.openlocfilehash: dac74085278418153ddec502f6257ce13885704d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394376"
---
# <a name="progressreporter-class"></a>progress_reporter-Klasse

Die Status-Reporter-Klasse ermöglicht Benachrichtigungen zum Status der Berichterstellung eines bestimmten Typs. Jedes progress_reporter-Objekt ist an eine bestimmte asynchrone Aktion bzw. einen Vorgang gebunden.

## <a name="syntax"></a>Syntax

```
template<typename _ProgressType>
class progress_reporter;
```

#### <a name="parameters"></a>Parameter

*_ProgressType*<br/>
Der Nutzlasttyp jeder Statusbenachrichtigung, die vom Status-Reporter gemeldet wird.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[progress_reporter](#ctor)||

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[report](#report)|Sendet einen Statusbericht an die asynchrone Aktion oder den asynchronen Vorgang, an die bzw. an den dieser Status-Reporter gebunden ist.|

## <a name="remarks"></a>Hinweise

Dieser Typ ist nur für Windows-Runtime-apps verfügbar.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`progress_reporter`

## <a name="requirements"></a>Anforderungen

**Header:** ppltasks.h

**Namespace:** Parallelität

##  <a name="ctor"></a> "progress_reporter"

```
progress_reporter();
```

##  <a name="report"></a> Bericht

Sendet einen Statusbericht an die asynchrone Aktion oder den asynchronen Vorgang, an die bzw. an den dieser Status-Reporter gebunden ist.

```
void report(const _ProgressType& val) const;
```

### <a name="parameters"></a>Parameter

*val*<br/>
Die Nutzlast, über die mit einer Statusbenachrichtigung berichtet werden soll.

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace](concurrency-namespace.md)
