---
title: Concurrency-Namespace-Enumerationen (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
ms.openlocfilehash: adfc1743d887f2a670111eff31cf4653d2df1bee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180452"
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
|`queuing_mode_immediate`|Ein queuingmodus, der angibt, dass Befehle, z. B. [Parallel_for_each-Funktion (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each), werden an das entsprechende zugriffstastengerät gesendet, sobald sie sich an den Aufrufer zurückgeben.|
|`queuing_mode_automatic`|Ein queuingmodus, der angibt, dass Befehle in einer Befehlswarteschlange in die Warteschlange werden, die entspricht, der ["accelerator_view"](accelerator-view-class.md) Objekt. Befehle werden an das Gerät gesendet. wenn [accelerator_view:: Flush](accelerator-view-class.md#flush) aufgerufen wird.|

## <a name="see-also"></a>Siehe auch

[Concurrency-Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
