---
title: Concurrency-Namespace-Enumerationen (AMP) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58d70b995642eaca3dbefd75383e6d6bf06f2c62
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082431"
---
# <a name="concurrency-namespace-enums-amp"></a>Concurrency-Namespace-Enumerationen (AMP)

|||
|-|-|
|[Access_type-Enumeration](#access_type)|[Queuing_mode-Enumeration](#queuing_mode)|

##  <a name="access_type"></a>  Access_type-Enumeration

Enumerationstyp wurde verwendet, um die verschiedenen Datenzugriffstypen anzugeben.

```
enum access_type;
```

### <a name="values"></a>Werte

|Name|Beschreibung|
|----------|-----------------|
|`access_type_auto`|Wählen Sie automatisch das beste `access_type`-Objekt für die Zugriffstaste aus.|
|`access_type_none`|Dediziert. Auf die Speicherbelegung kann nur auf der Zugriffstaste und nicht auf der CPU zugegriffen werden.|
|`access_type_read`|Freigegeben. Auf die Speicherbelegung kann auf der Zugriffstaste zugegriffen werden und sie ist auf der CPU lesbar.|
|`access_type_read_write`|Freigegeben. Auf die Speicherbelegung kann auf der Zugriffstaste zugegriffen werden und sie ist auf der CPU schreibbar.|
|`access_type_write`|Freigegeben. Auf die Speicherbelegung kann auf der Zugriffstaste zugegriffen werden und sie ist auf der CPU les- und schreibbar.|

##  <a name="queuing_mode"></a>  Queuing_mode-Enumeration

Gibt die Modi für das Hinzufügen zur Warteschlange an, die auf dem Beschleuniger unterstützt werden.

```
enum queuing_mode;
```

### <a name="values"></a>Werte

|Name|Beschreibung|
|----------|-----------------|
|`queuing_mode_immediate`|Ein queuingmodus, der angibt, dass Befehle, z. B. [Parallel_for_each-Funktion (C++-AMP)](concurrency-namespace-functions-amp.md#parallel_for_each), werden an das entsprechende zugriffstastengerät gesendet, sobald sie sich an den Aufrufer zurückgeben.|
|`queuing_mode_automatic`|Ein queuingmodus, der angibt, dass Befehle in einer Befehlswarteschlange in die Warteschlange werden, die entspricht, der ["accelerator_view"](accelerator-view-class.md) Objekt. Befehle werden an das Gerät gesendet. wenn [accelerator_view:: Flush](accelerator-view-class.md#flush) aufgerufen wird.|

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
