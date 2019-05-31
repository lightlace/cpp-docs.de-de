---
title: Optionen, ATL-Eigenschaftenseiten-Assistent
ms.date: 05/09/2019
f1_keywords:
- vc.codewiz.class.atl.ppg.options
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
ms.openlocfilehash: c883b3e79bd857bb457da0a1bd540a08ddddf017
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2019
ms.locfileid: "65524542"
---
# <a name="options-atl-property-page-wizard"></a>Optionen, ATL-Eigenschaftenseiten-Assistent


::: moniker range="vs-2019"

Der ATL-Eigenschaftenseiten-Assistent ist in Visual Studio 2019 und höher nicht verfügbar.

::: moniker-end

::: moniker range="vs-2017"

Verwenden Sie diese Seite des Assistenten, um das Threadingmodell und die Aggregationsebene der Eigenschaftenseite zu definieren, die Sie erstellen.

- **Threadingmodell**

   Gibt das Threadingmodell an, das von der Eigenschaftenseite verwendet wird.

   Weitere Informationen finden Sie unter [Angeben des Threadingmodells für ein Projekt](../../atl/specifying-the-threading-model-for-a-project-atl.md).

   |Option|Beschreibung|
   |------------|-----------------|
   |**Single**|Die Eigenschaftenseite wird nur im primären COM-Thread ausgeführt.|
   |**Apartment**|Die Eigenschaftenseite kann in jedem Einzelthreadapartment erstellt werden. Der Standardwert.|

- **Aggregation**

   Fügt Aggregationsunterstützung für die Eigenschaftenseite hinzu, die Sie erstellen. Weitere Informationen finden Sie unter [Aggregation](../../atl/aggregation.md).

   |Option|Beschreibung|
   |------------|-----------------|
   |**Ja**|Erstellt eine Eigenschaftenseite, die aggregiert werden kann.|
   |**No**|Erstellt eine Eigenschaftenseite, die nicht aggregiert werden kann.|
   |**Nur**|Erstellt eine Eigenschaftenseite, die nur durch Aggregation instanziiert werden kann.|

::: moniker-end

## <a name="see-also"></a>Siehe auch

[ATL-Eigenschaftenseiten-Assistent](../../atl/reference/atl-property-page-wizard.md)<br/>
[Zeichenfolgen, ATL-Eigenschaftenseiten-Assistent](../../atl/reference/strings-atl-property-page-wizard.md)
