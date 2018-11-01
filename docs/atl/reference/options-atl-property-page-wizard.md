---
title: Optionen, ATL-Eigenschaftenseiten-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.codewiz.class.atl.ppg.options
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
ms.openlocfilehash: e891bd9e37bbf2fbedcdd71649305cdc366065fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642008"
---
# <a name="options-atl-property-page-wizard"></a>Optionen, ATL-Eigenschaftenseiten-Assistent

Mithilfe dieser Seite des Assistenten für das threading und die Aggregation auf der Eigenschaftenseite zu definieren, die Sie erstellen.

- **Threading-Modell**

   Gibt das Threadingmodell an, die von der Eigenschaftenseite verwendet.

   Finden Sie unter [angeben des Projekts. Threading-Modell](../../atl/specifying-the-threading-model-for-a-project-atl.md) für Weitere Informationen.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Single**|Die Eigenschaftenseite wird nur im primären COM-Thread ausgeführt.|
   |**Apartment**|Die Eigenschaftenseite kann in jedem Singlethread-Apartment erstellt werden. Der Standardwert.|

- **Aggregation**

   Fügt die Unterstützung für die Eigenschaftenseite, die Sie erstellen. Finden Sie unter [Aggregation](../../atl/aggregation.md) für Weitere Informationen.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Ja**|Erstellen Sie eine Eigenschaftenseite, die aggregiert werden können.|
   |**No**|Erstellen Sie eine Eigenschaftenseite, die nicht aggregiert werden kann.|
   |**Nur**|Erstellen Sie eine Eigenschaftenseite, die durch die Aggregation nur instanziiert werden kann.|

## <a name="see-also"></a>Siehe auch

[ATL-Eigenschaftenseiten-Assistent](../../atl/reference/atl-property-page-wizard.md)<br/>
[Zeichenfolgen, ATL-Eigenschaftenseiten-Assistent](../../atl/reference/strings-atl-property-page-wizard.md)

