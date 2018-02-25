---
title: Eigenschaftenzuordnungen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 020479236bd86659ee4df783bf2056613cfac753
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="property-maps"></a>Eigenschaftenzuordnungen
Jeder Anbieter unterstützt zusätzlich zum die Sitzung, Rowset und optionale Command-Objekt eine oder mehrere Eigenschaften. Diese Eigenschaften werden in der eigenschaftenzuordnungen, die in den Headerdateien, die vom OLE DB-Anbieter-Assistenten erstellten definiert. Jeder Header-Datei enthält eine Zuordnung für die Eigenschaften in der OLE DB-Eigenschaftengruppe, die für das Objekt oder die in dieser Datei definierten Objekte definiert. Die Header-Datei, die das Datenquellenobjekt enthält auch Übersicht darüber enthält, die Eigenschaft für die [DataSource-Eigenschaften](https://msdn.microsoft.com/en-us/library/ms724188\(v=vs.140\).aspx). Session.h enthält die eigenschaftenzuordnung für die [Sitzungseigenschaften](https://msdn.microsoft.com/en-us/library/ms714221.aspx). Die Rowset- und Befehlsobjekte befinden sich in einer einzelnen Headerdatei aufgerufen *Projektname*RS.h. Diese Eigenschaften sind Mitglieder einer der [Rowseteigenschaften](https://msdn.microsoft.com/en-us/library/ms711252.aspx) Gruppe.  
  
## <a name="see-also"></a>Siehe auch  
 [Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)