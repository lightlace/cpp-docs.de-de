---
title: Optionen, ATL-Eigenschaftenseiten-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.ppg.options
dev_langs:
- C++
helpviewer_keywords:
- ATL Property Page Wizard, options
ms.assetid: a7107779-b2ea-4f99-b84b-7f3e0c504bc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3f3cf6a9e2c9924ae72624c931a4551736f8956
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45711827"
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

[ATL-Eigenschaftenseiten-Assistent](../../atl/reference/atl-property-page-wizard.md)   
[Zeichenfolgen, ATL-Eigenschaftenseiten-Assistent](../../atl/reference/strings-atl-property-page-wizard.md)

