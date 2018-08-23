---
title: 'Module:: genericreleasenotifier-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GenericReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- GenericReleaseNotifier class
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: da35e2c257fef72ea75e05768960098111727359
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611624"
---
# <a name="modulegenericreleasenotifier-class"></a>Module::GenericReleaseNotifier-Klasse

Ruft einen Ereignishandler an, wenn das letzte Objekt in das aktuelle Modul veröffentlicht wird. Der Ereignishandler ist durch ein Lambda, Funktionselement oder Zeiger auf Funktion angegeben.

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
class GenericReleaseNotifier : public ReleaseNotifier;
```

### <a name="parameters"></a>Parameter

*T*  
Der Typ des Datenmembers, der den Speicherort des ereignishandlers enthält.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[Module::GenericReleaseNotifier::GenericReleaseNotifier-Konstruktor](../windows/module-genericreleasenotifier-genericreleasenotifier-constructor.md)|Initialisiert eine neue Instanz der dem **genericreleasenotifier** Klasse.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[Module::GenericReleaseNotifier::Invoke-Methode](../windows/module-genericreleasenotifier-invoke-method.md)|Ruft den Ereignishandler verknüpft ist, mit dem aktuellen **genericreleasenotifier** Objekt.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[Module::GenericReleaseNotifier::callback_-Datenmember](../windows/module-genericreleasenotifier-callback-data-member.md)|Enthält den Lambda, Funktionselement oder Zeiger auf Funktion zugeordnete Ereignishandler die aktuelle **genericreleasenotifier** Objekt.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ReleaseNotifier`

`GenericReleaseNotifier`

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch
[Module-Klasse](../windows/module-class.md)