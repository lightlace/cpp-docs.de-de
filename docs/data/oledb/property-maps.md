---
title: Eigenschaftenzuordnungen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d7664562ff31f1f5871fab4ce74c1652370a540d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103215"
---
# <a name="property-maps"></a>Eigenschaftenzuordnungen
Jeder Anbieter unterstützt zusätzlich zum die Sitzung, Rowset und optionale Command-Objekt eine oder mehrere Eigenschaften. Diese Eigenschaften werden in der eigenschaftenzuordnungen, die in den Headerdateien, die vom OLE DB-Anbieter-Assistenten erstellten definiert. Jeder Header-Datei enthält eine Zuordnung für die Eigenschaften in der OLE DB-Eigenschaftengruppe, die für das Objekt oder die in dieser Datei definierten Objekte definiert. Die Header-Datei, die das Datenquellenobjekt enthält auch Übersicht darüber enthält, die Eigenschaft für die [DataSource-Eigenschaften](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx). Session.h enthält die eigenschaftenzuordnung für die [Sitzungseigenschaften](https://msdn.microsoft.com/en-us/library/ms714221.aspx). Die Rowset- und Befehlsobjekte befinden sich in einer einzelnen Headerdatei aufgerufen *Projektname*RS.h. Diese Eigenschaften sind Mitglieder einer der [Rowseteigenschaften](https://msdn.microsoft.com/en-us/library/ms711252.aspx) Gruppe.  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)