---
title: Eigenschaftenzuordnungen | Microsoft-Dokumentation
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
ms.openlocfilehash: b3fb9c5a5c18925bfcd448bb2349379262b27361
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46080986"
---
# <a name="property-maps"></a>Eigenschaftenzuordnungen

Zusätzlich zu der Sitzung, Rowset und optional Befehlsobjekt unterstützt jeder Anbieter eine oder mehrere Eigenschaften. Diese Eigenschaften werden in der eigenschaftenzuordnungen in den Headerdateien, die vom OLE DB-Anbieter-Assistenten erstellt definiert. Jede Headerdatei enthält eine Zuordnung für die Eigenschaften in der OLE DB-Eigenschaftengruppe, die für das Objekt oder die in dieser Datei definierten Objekte definiert. Die Header-Datei, die das Datenquellenobjekt enthält enthält auch die eigenschaftenzuordnung für die [DataSource-Eigenschaften](https://msdn.microsoft.com/library/ms724188\(v=vs.140\).aspx). Session.h enthält die eigenschaftenzuordnung für die [Sitzungseigenschaften](/previous-versions/windows/desktop/ms714221\(v=vs.85\)). Die Rowset- und Befehlsobjekte befinden sich in einer einzigen Headerdatei, die Namen *Projectname*RS.h. Diese Eigenschaften sind Mitglieder der [Rowseteigenschaften](/previous-versions/windows/desktop/ms711252\(v=vs.85\)) Gruppe.  
  
## <a name="see-also"></a>Siehe auch  

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)